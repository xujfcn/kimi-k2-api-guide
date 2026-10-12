# Kimi API access through Crazyrouter

Updated 2026-10-12. The old example ID `kimi-k2` returned `404 model_not_found` during this review. Use an exact model currently available to your key; do not infer an API ID from a product display name.

## Discover available models

```bash
curl "https://crazyrouter.com/v1/models" \
  -H "Authorization: Bearer $CRAZYROUTER_API_KEY"
```

The current public catalogue includes `kimi-k3`. Verify it is available to your account before calling it.

```python
import os
from openai import OpenAI

client = OpenAI(api_key=os.environ["CRAZYROUTER_API_KEY"], base_url="https://crazyrouter.com/v1")
response = client.chat.completions.create(
    model="kimi-k3",
    messages=[{"role": "user", "content": "Explain API gateways in one paragraph."}],
)
print(response.choices[0].message.content)
```

The earlier February 2026 RMB price table is retired. Check [current USD pricing and billing units](https://crazyrouter.com/en/pricing), including input, output and cache charges. Account discounts and long-context tiers may differ.

[Model catalogue](https://crazyrouter.com/en/models) · [API documentation](https://docs.crazyrouter.com) · [Create a key](https://crazyrouter.com/console/token)
