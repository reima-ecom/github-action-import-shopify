# Reima GitHub Actions

## import-shopify

Import products and collections from Shopify in a way expected by `reima-ecom/reima-theme`c

Requires Deno and Hugo. Example:

```yml
name: Refresh Shopify products

on:
  repository_dispatch:
    types: refresh-products

jobs:
  refresh-products:
    runs-on: ubuntu-latest
    name: Refresh Shopify products
    steps:
    - uses: actions/checkout@v2
    - uses: denolib/setup-deno@v2
    - uses: peaceiris/actions-hugo@v2
```