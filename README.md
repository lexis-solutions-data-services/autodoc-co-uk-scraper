# Autodoc.co.uk Scraper

Scrape product data from Autodoc UK. Extracts names, prices, brand, identifiers (SKU/MPN), availability, images, and rich specifications.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-wfwUDYeoKiAz3bFfE-MHMXzQso6K-58e3cfb50000ff00059fd652-198x149-2x.jpeg" alt="Autodoc.co.uk Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/autodoc-co-uk-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


![banner](https://i.ibb.co/qF9b9R0d/Screenshot-2025-10-04-at-4-56-19-PM.png)

---

## 📦 What you get

## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.0.1` |
| **Last Update** | Nov 30, 2025 |

---



Field
---
`name`
`brand`
`articleNumber`
`sku`
`mpn`
`description`
`category`
`image`
`price`
`priceCurrency`
`inStock`
`rating`
`reviewsCount`
`offers.price`
`offers.priceCurrency`
`offers.availability`
`offers.url`
`additionalProperties`
`url`
`loadedUrl`

---


## 📥 Input Schema

The actor accepts:

```json
{
  "startUrls": [
    {
      "url": "https://www.autodoc.co.uk/car-parts/engine-oil-12094/bmw/1er-reihe/1-convertible-e88/25443-118-i?page=1"
    },
    {
      "url": "https://www.autodoc.co.uk/car-parts/turbocharger-10972/vauxhall/agila/agila-mk-ii-b/27595-1-0-12v"
    },
    { "url": "https://www.autodoc.co.uk/mapco/2039778" }
  ],
  "maxItems": 50,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": ["RESIDENTIAL"],
    "apifyProxyCountry": "GB"
  }
}
```

Notes:

- **startUrls**: Search/category pages are auto‑labeled as `search`; product pages as `detail`.
- **maxItems**: Global cap across search and detail handlers.
- **proxyConfiguration**: Recommend Apify Residential proxy in GB.

---

## 📤 Output Schema

Each scraped item conforms to the structure below. Search pages yield summarized items (with `source: "search"`), while detail pages provide full items (with `source: "detail"`).

```json
{
  "source": "detail",
  "url": "https://www.autodoc.co.uk/mapco/2039778",
  "loadedUrl": "https://www.autodoc.co.uk/mapco/2039778",
  "name": "MAPCO 6835 Brake pad set",
  "brand": "MAPCO",
  "articleNumber": "6835",
  "sku": "6835",
  "mpn": "6835",
  "description": "…",
  "category": "Brake pad set",
  "image": "https://cdn.autodoc.de/thumb?id=2039778&m=0&n=0&lng=en&rev=94077937",
  "price": 20.99,
  "priceCurrency": "GBP",
  "inStock": true,
  "rating": 10,
  "reviewsCount": 1,
  "offers": {
    "price": 20.99,
    "priceCurrency": "GBP",
    "availability": "https://schema.org/InStock",
    "url": "https://www.autodoc.co.uk/mapco/2039778"
  },
  "additionalProperties": {
    "Fitting Position": "Front Axle",
    "Brake System": "Lucas / TRW",
    "Thickness [mm]": "17,4"
  }
}
```

---

## Need to scrape other automotive websites

Check out our other automotive scrapers:

- [CARFAX Scraper](https://apify.com/lexis-solutions/carfax-com) - Extract vehicle listings and history reports from America's leading vehicle history platform
- [Cargurus Scraper](https://apify.com/lexis-solutions/cargurus-com) - Scrape car listings from CarGurus - including makes, models, prices, mileage, dealer info, and reviews.

Contact us over [Email](mailto:scraping@lexis.solutions) or [LinkedIn](https://www.linkedin.com/company/lexis-solutions)

## Support Our Work 💝

If you're happy with our work and scrapers, you're welcome to leave us a company review [here](https://apify.com/partners/find/lexis-solutions/review) and leave a review for the scrapers you're subscribed to. It will take you less than a minute but it will mean a lot to us!
