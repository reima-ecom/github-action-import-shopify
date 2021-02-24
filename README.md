# github-action-import-shopify

Import products and collections from Shopify in a way expected by `reima-ecom/reima-theme`.

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
    - uses: reima-ecom/github-action-import-shopify@1
      with:
        shop: reima-jp
        storefront-token: e0370fdfeed9aeac00130441c6e2cf76
      env:
        SHOPIFY_BASIC_AUTH: ${{ secrets.SHOPIFY_BASIC_AUTH }}
```