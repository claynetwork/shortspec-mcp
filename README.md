# ShortSpec barcode facts (API and MCP)

Status: served at https://api.shortspec.com.

Free, no key, no account. Send a barcode and get the facts we hold on that product, each with its source link and check date, plus our page for it. We hold facts for a small, hand-reviewed set of products; most barcodes return "no facts held".

## Tools

| Tool | What it does | Example call |
|---|---|---|
| `barcode_facts` | Sourced facts for one barcode: product name, brand, sourced statements with source and check date, recall records naming the code, and our page link. No prices or stock. | `{"name":"barcode_facts","arguments":{"barcode":"8596202003892"}}` |

## Connect

    https://api.shortspec.com/mcp   (Streamable HTTP, stateless, no key)
    GET https://api.shortspec.com/v1/barcode/{code}
    GET https://api.shortspec.com/v1/catalog


## Client config (copy and paste)

    {"mcpServers": {"shortspec": {"type": "http", "url": "https://api.shortspec.com/mcp"}}}

## What it does not do

- No prices, stock, reviews or seller data.
- "No facts" does not mean a product is safe or recall-free.
- A recall record may cover only some lots or dates.

## Data licence

Each fact names its source and licence. Sources in use: Wikipedia text (CC BY-SA 4.0, credited "Wikipedia contributors", with the article revision), Wikidata (CC0), Open Products Facts barcodes (ODbL), Wikimedia Commons photos (each with its own author and licence, shown on the page), EU Safety Gate (European Commission, CC BY 4.0). No Amazon content is stored or returned.

## Changelog

- 0.1.0: one tool `barcode_facts`, read-only and idempotent; barcode pattern with an example; structured output with source, licence and check date per fact.
