[Flippa Scraper](https://apify.com/solidcode/flippa-scraper?fpr=data)

# Flippa Listings Scraper

Extract detailed listing data from Flippa.com — the world's largest marketplace for buying and selling websites, SaaS businesses, apps, domains, and eCommerce stores. Get financial metrics, traffic data, verification badges, sale status, and **50+ data fields** for every listing.

## Why This Scraper?

- **50+ structured fields per listing** — financials, traffic, verification badges, sale details, and more
- **Built-in filters** — Filter by property type (SaaS, eCommerce, App, Domain, AI Tools, and more) and listing status without constructing complex URLs
- **Price drop detection** — Identify reduced listings with original price, current price, and drop percentage
- **Verified data flags** — Know which listings have verified revenue, verified traffic, and Super Seller badges
- **Clean, deduplicated output** — One consistent field per data point, no legacy duplicates or empty fields
- **Flexible input** — Use search URLs from your browser, direct listing URLs, or the built-in filters — or combine all three
- **Low cost** — Runs on datacenter proxies by default, keeping your costs down

## Use Cases

**Investment Research & Due Diligence**

- Screen thousands of digital assets by revenue, profit margin, and valuation multiples
- Compare asking prices across similar property types and categories
- Track price drops to find motivated sellers and negotiation opportunities

**Market Intelligence**

- Analyze SaaS, eCommerce, and content site valuations over time
- Benchmark revenue multiples and profit multiples by industry and property type
- Monitor listing volume and pricing trends across asset categories

**Deal Sourcing & Brokerage**

- Build a pipeline of listings matching specific investment criteria
- Identify verified, high-quality listings with strong financials
- Track auction activity, bid counts, and time-to-sale patterns

**Competitive Analysis**

- Discover what types of digital businesses are selling and at what prices
- Analyze monetization methods, platforms, and site ages across listings
- Study which categories attract the most bids and watchers

## Getting Started

### Browse All Active Listings

The simplest way to start — no URLs needed. Just set how many results you want:

```
{
    "maxResults": 100
}
```

### Filter by Property Type

Find specific types of digital assets:

```
{
    "propertyType": "saas",
    "status": "open",
    "maxResults": 200
}
```

### Use a Flippa Search URL

Apply filters on Flippa.com in your browser, then paste the URL:

```
{
    "searchUrls": [
        "https://flippa.com/search?filter[property_type]=established&filter[status]=open&filter[revenue]=revenue_generating"
    ],
    "maxResults": 500
}
```

### Scrape Specific Listings

Provide direct listing URLs to get full data for specific assets:

```
{
    "listingUrls": [
        "https://flippa.com/12345678",
        "https://flippa.com/87654321"
    ]
}
```

### Combine Everything

Mix search URLs, listing URLs, and filters in a single run:

```
{
    "searchUrls": ["https://flippa.com/buy/sitetype/saas"],
    "listingUrls": ["https://flippa.com/12345678"],
    "propertyType": "ecommerce",
    "status": "won",
    "maxResults": 1000
}
```

## Input Reference

### What to Scrape

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `searchUrls` | string[] | `[]` | Flippa search or category page URLs. Apply filters on Flippa.com first, then copy the URL from your browser |
| `listingUrls` | string[] | `[]` | Direct URLs to specific Flippa listings (e.g., `https://flippa.com/12345678`) |

### Filters & Options

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `maxResults` | integer | `100` | Maximum number of listings to extract. Set to 0 for no limit |
| `propertyType` | string | All Types | Filter by asset type: Website, SaaS, eCommerce, App, Domain Only, AI Apps & Tools, Content Site, Marketplace, or Service Business |
| `status` | string | Active Listings | Choose Active Listings, Sold Listings, or All Listings |

### Advanced

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `proxyConfiguration` | object | Apify Proxy | Proxy settings for reliable data collection. The defaults work for most cases |

## Output

Each listing contains up to 50+ structured fields. Here's an example:

```
{
    "id": "12345678",
    "url": "https://flippa.com/12345678",
    "title": "Profitable SaaS Platform - Project Management Tool",
    "summary": "Established SaaS with 500+ paying customers and 85% gross margin",
    "propertyType": "SaaS",
    "category": "Internet",
    "primaryPlatform": "Custom Built",
    "propertyName": "projecttool.io",
    "monetization": "Subscription",
    "siteAge": "3 years",
    "businessLocation": "United States",
    "price": 150000,
    "priceFormatted": "USD $150,000",
    "originalPrice": 175000,
    "priceDrop": true,
    "priceDropPercent": 14,
    "currency": "USD $",
    "monthlyRevenue": 12500,
    "annualRevenue": 150000,
    "ttmRevenue": 145000,
    "monthlyProfit": 9400,
    "annualProfit": 112800,
    "profitMargin": 75.2,
    "monthlyExpenses": 3100,
    "revenueMultiple": 1.0,
    "profitMultiple": 1.33,
    "uniqueVisitorsPerMonth": 45000,
    "annualOrganicTraffic": 380000,
    "authorityScore": 32,
    "saleMethod": "classified",
    "saleMethodTitle": "Asking Price",
    "status": "open",
    "bidCount": 5,
    "endDate": "2026-05-15T00:00:00Z",
    "underOffer": false,
    "openToOffer": true,
    "isVerified": true,
    "hasVerifiedTraffic": true,
    "hasVerifiedRevenue": true,
    "isSuperSeller": false,
    "isBrokerSeller": false,
    "isEditorsChoice": true,
    "isSponsored": false,
    "isConfidential": false,
    "isManagedByFlippa": false,
    "isReadyMade": false,
    "isDomainOnly": false,
    "equitySalePercent": "100",
    "verifications": [
        {"provider": "google_analytics", "description": "Traffic verified via Google Analytics"}
    ],
    "integrations": ["google_analytics", "stripe"],
    "searchUrl": "https://flippa.com/buy/sitetype/saas",
    "scrapedAt": "2026-04-12T10:30:00.000Z"
}
```

### All Available Fields

| Field | Type | Description |
| --- | --- | --- |
| `id` | string | Unique listing identifier |
| `url` | string | Direct URL to the listing page |
| `title` | string | Listing headline |
| `summary` | string | Short description of the listing |
| `propertyType` | string | Asset type (SaaS, eCommerce, Website, App, etc.) |
| `category` | string | Industry category (Internet, Business, etc.) |
| `primaryPlatform` | string | Platform the asset is built on (WordPress, Shopify, Custom Built, etc.) |
| `propertyName` | string | Name or domain of the property |
| `monetization` | string | Revenue method (Subscription, Ads, Affiliate, eCommerce, etc.) |
| `siteAge` | string | How long the site has existed (e.g., "3 years") |
| `businessLocation` | string | Business location (e.g., "United States") |
| `price` | number | Current asking or sale price |
| `priceFormatted` | string | Formatted price with currency (e.g., "USD $150,000") |
| `originalPrice` | number | Original price before any reduction |
| `priceDrop` | boolean | Whether the price has been reduced |
| `priceDropPercent` | number | Percentage of price reduction |
| `currency` | string | Currency label (e.g., "USD $") |
| `monthlyRevenue` | number | Average monthly revenue |
| `annualRevenue` | number | Annual revenue (monthly x 12) |
| `ttmRevenue` | number | Trailing twelve months revenue |
| `monthlyProfit` | number | Average monthly net profit |
| `annualProfit` | number | Annual net profit (monthly x 12) |
| `profitMargin` | number | Profit margin as a percentage |
| `monthlyExpenses` | number | Average monthly expenses |
| `revenueMultiple` | number | Valuation multiple based on revenue |
| `profitMultiple` | number | Valuation multiple based on profit |
| `uniqueVisitorsPerMonth` | number | Monthly unique visitors |
| `annualOrganicTraffic` | number | Annual organic search traffic |
| `authorityScore` | number | SEO authority score |
| `saleMethod` | string | Sale method ("auction" or "classified") |
| `saleMethodTitle` | string | Human-readable sale method (e.g., "Asking Price") |
| `status` | string | Listing status ("open" or "won") |
| `bidCount` | number | Number of bids placed |
| `endDate` | string | Listing end date (ISO 8601) |
| `underOffer` | boolean | Whether an offer is pending |
| `openToOffer` | boolean | Whether the seller accepts offers |
| `isVerified` | boolean | Listing verified by Flippa |
| `hasVerifiedTraffic` | boolean | Traffic stats are independently verified |
| `hasVerifiedRevenue` | boolean | Financial stats are independently verified |
| `isSuperSeller` | boolean | Seller has Super Seller badge |
| `isBrokerSeller` | boolean | Listed by a broker |
| `isEditorsChoice` | boolean | Editor's Choice pick |
| `isSponsored` | boolean | Sponsored or promoted listing |
| `isConfidential` | boolean | Confidential listing (requires NDA) |
| `isManagedByFlippa` | boolean | Managed by Flippa team |
| `isReadyMade` | boolean | Turnkey/starter site |
| `isDomainOnly` | boolean | Domain-only sale |
| `equitySalePercent` | string | Percentage of equity being sold |
| `verifications` | array | Verification badges with provider and description |
| `integrations` | array | Connected services (e.g., "google_analytics", "stripe") |
| `searchUrl` | string | The search URL that found this listing |
| `scrapedAt` | string | Timestamp of when data was collected (ISO 8601) |

## Tips for Best Results

- **Start with filters** — Use the Property Type and Listing Status dropdowns instead of manually constructing URL query strings
- **Use search URLs for complex filters** — Apply advanced filters on Flippa.com (revenue range, price range, site age, etc.) then paste the URL
- **Combine inputs** — Mix search URLs for broad discovery with direct listing URLs for specific assets you're tracking
- **Check verification flags** — Filter your results by `isVerified`, `hasVerifiedRevenue`, and `hasVerifiedTraffic` to focus on higher-quality listings
- **Monitor price drops** — Use the `priceDrop` and `priceDropPercent` fields to find motivated sellers

## Pricing

**~$0.50 per 1,000 listings** — among the lowest prices on Apify for marketplace data.

| Results | Estimated Cost |
| --- | --- |
| 100 | ~$0.05 |
| 1,000 | ~$0.50 |
| 10,000 | ~$5.00 |

Platform fees (compute, proxy, storage) are additional and depend on your Apify plan.

## Integrations

Export data in JSON, CSV, Excel, XML, or RSS. Connect to 1,500+ apps via:

- **Zapier** / **Make** / **n8n** — Workflow automation
- **Google Sheets** — Direct spreadsheet export
- **Slack** / **Email** — Notifications on new results
- **Webhooks** — Custom API integrations
- **Apify API** — Full programmatic access

## Legal & Ethical Use

This actor is designed for legitimate investment research, market intelligence, and business analysis. Users are responsible for complying with applicable laws and Flippa's Terms of Service. Do not use extracted data for spam, harassment, or any illegal purpose.