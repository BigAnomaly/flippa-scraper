[Flippa Scraper](https://apify.com/epicscrapers/flippa-scraper?fpr=data)

**Extract detailed listing data** from [Flippa.com](https://flippa.com/) — the world's largest marketplace for buying and selling online businesses, websites, SaaS products, and digital assets.

Try it with a single click on the Apify platform — no coding required. Use the API to integrate Flippa data into your own tools, schedule recurring crawls, or export to CSV/Excel.

## Why scrape Flippa.com listings?

Whether you're a **digital asset investor**, **M&A broker**, or **market researcher**, Flippa holds a wealth of data on thousands of online businesses for sale. This scraper helps you:

- **Identify acquisition opportunities** — monitor new listings across SaaS, content sites, e-commerce stores, and mobile apps
- **Perform market analysis** — collect pricing trends, revenue multiples, and sale method patterns by property type
- **Build deal-flow pipelines** — feed structured Flippa data into your CRM, spreadsheet, or analytical model
- **Track sold listings** — review historical sales data (won/sold status) to benchmark valuations

Because the scraper uses **pure HTTP requests** (no headless browser), it's resource-efficient and cost-effective even at scale.

## How to scrape Flippa.com data

1. **Open the Actor** on Apify Console
2. **Configure your search** — paste a Flippa search URL or use the filter fields for status, property type, and sale method
3. **Set limits** — optionally cap results with `maxItems` (0 = scrape all available)
4. **Run the Actor** — click "Start" and watch listings stream into the dataset
5. **Export your data** — download results as JSON, CSV, Excel, or HTML from the Output tab

That's it. No browser, no heavy infrastructure, no complex setup.

## Input

Configure the scraper through the Apify Console Input tab or via the API. All fields are optional — sensible defaults are provided.

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| `url` | string | Flippa open SaaS listings | Base search URL to scrape. Supports any Flippa search page. |
| `status` | string | — | Filter by listing status: `open`, `won`, `sold` |
| `propertyType` | string | — | Filter by property type: `website`, `saas`, `ios_app`, `android_app`, `amazon_dca` |
| `saleMethod` | string | — | Filter by sale method: `auction`, `classified` |
| `maxItems` | integer | `0` (all) | Maximum listings to scrape. Set to `0` for unlimited. |
| `delay` | number | `1.0` | Seconds between page requests. Increase if you hit rate limits. |
| `useProxy` | boolean | `false` | Enable Apify proxy rotation to bypass IP-based blocking. |

### Filter presets

You have two ways to filter results:

- **Use the dedicated fields** — `status`, `propertyType`, and `saleMethod` are appended as query parameters to the base URL
- **Use a fully custom URL** — paste any Flippa search URL with your desired filters pre-applied. This is recommended for complex filter combinations.

> **Tip:** First visit Flippa in your browser, apply all the filters you want, then copy the URL and paste it into the `url` field. When filter fields are provided, they override any existing `filter[...]` params in the URL.

## Output

The Actor pushes each Flippa listing as a structured dataset item. You can download the dataset in **JSON, HTML, CSV, or Excel** from the Apify Console.

### Sample output

```
{
  "id": "12821301",
  "listing_url": "https://flippa.com/12821301",
  "title": "TaperFlow.app is a SaaS tool for taper plans, progress tracking, savings insights, and behavior-change support with subscription growth potential.",
  "summary": "TaperFlow.app is a SaaS tool for taper plans, progress tracking, savings insights, and behavior-change support with subscription growth potential.",
  "has_verified_traffic": false,
  "has_verified_revenue": false,
  "price": 250,
  "bid_count": 0,
  "sale_method": "auction",
  "status": "open",
  "category": "Health and Beauty",
  "monetization": "Services & Subscriptions",
  "profit_average": null,
  "end_at": "2026-05-30T04:42:27+00:00",
  "super_seller": false,
  "broker_seller": false,
  "sponsored": false,
  "editors_choice": false,
  "multiple": 0.0,
  "has_multiple?": false,
  "revenue_multiple": 0.0,
  "target_raise_amount": null,
  "ttm_revenue": null,
  "confidential": false,
  "primary_platform": null,
  "property_name": "TaperFlow",
  "established_at": 0,
  "country_name": "FL, United States",
  "ready_made": false,
  "thumbnail_url": "https://static2.flippa.com/webp_1a3b00e7-fca0-4c2e-9ce8-db29d8f6c9d9.webp",
  "default_image": "https://static.flippa.com/assets/search/placeholders/saas-0488f8c6251392f231d0d07ca10bf17ae3cd138d72e690cf724f0b3e74fded21.svg",
  "default_image_url": "https://static.flippa.com/assets/search/placeholders/saas-0488f8c6251392f231d0d07ca10bf17ae3cd138d72e690cf724f0b3e74fded21.svg",
  "blurred_image_url": "https://static2.flippa.com/blurred_thumbnail_f8380a6d-5860-c8e5-29db-3a6bbb3d19f6.png",
  "blurred_or_thumbnail_url": "https://static2.flippa.com/webp_1a3b00e7-fca0-4c2e-9ce8-db29d8f6c9d9.webp",
  "property_type": "SaaS",
  "watched": false,
  "scores": null,
  "beta_scores": null,
  "uniques_per_month": null,
  "age_label": "Site Age",
  "formatted_age_in_years": "<1 year",
  "sale_method_title": "Starting Price",
  "integrations": [],
  "integration_icons": [],
  "currency_label": "USD $",
  "protect_listing": false,
  "display_verification_badge": false,
  "all_verifications": [],
  "manually_vetted": false,
  "early_access_listing": false,
  "early_access_percentage": "100%",
  "early_access_days_remaining": 0,
  "early_access_overlay_title_suffix": "in 0 Days",
  "early_access_open_at": null,
  "viewer_has_early_access": null,
  "special_tags": false,
  "hover_image_url": "https://static2.flippa.com/blurred_thumbnail_f8380a6d-5860-c8e5-29db-3a6bbb3d19f6.png",
  "basic_info": {
    "name": "TaperFlow",
    "hover_image": "https://static2.flippa.com/thumbnail_1a3b00e7-fca0-4c2e-9ce8-db29d8f6c9d9.png",
    "padlocked": false
  },
  "open_listing": true,
  "confidential_thumbnail_url": "",
  "confidential_overlay_class": "",
  "display_confidential_label": "",
  "annual_organic_traffic": null,
  "revenue_average": 0,
  "authority_score": 0,
  "app_rating": null,
  "managed_by_flippa": false,
  "original_price": null,
  "price_dropped": false,
  "price_dropped_percent": null,
  "under_offer": false,
  "badges": [],
  "listing_watchable": true,
  "show_multiple": false,
  "invest": false,
  "action_class": "primary",
  "key_data": [
    {
      "label": "Type",
      "value": "SaaS"
    },
    {
      "label": "Industry",
      "value": "Health and Beauty"
    },
    {
      "label": "Monetization",
      "value": "Services & Subscriptions"
    },
    {
      "label": "Site Age",
      "value": "<1 year"
    },
    {
      "label": "Net Profit",
      "value": "USD $0 p/mo"
    }
  ],
  "open_to_offer": false,
  "partial_sale": false,
  "equity_sale_percentage": "100",
  "hide_profit": false,
  "domain_only?": false,
  "action_button_text": "View Listing",
  "original_price_text": null,
  "price_text": "USD $250",
  "target_raise_amount_text": null
}
```

## Data fields

Every listing includes all fields provided by Flippa's search API. Below are the most commonly used fields:

| Field | Description |
| --- | --- |
| `title` | Listing title |
| `url` | Direct URL to the Flippa listing |
| `price` | Current asking price or auction price |
| `propertyType` | Asset category: `website`, `saas`, `ios_app`, `amazon_dca`, etc. |
| `status` | Listing lifecycle status: `open`, `won`, `sold` |
| `saleMethod` | How the asset is sold: `auction` or `classified` |
| `revenue` | Monthly or annual revenue disclosed by the seller |
| `profit` | Monthly or annual profit disclosed by the seller |
| `listingId` | Unique Flippa identifier for the listing |
| `createdAt` | Date and time the listing was published |
| `description` | Full listing description |
| `category` | Broader category classification |
| `metrics` | Additional metrics (traffic, growth rate, churn, etc.) |

Additional fields (images, seller info, tags, etc.) are included when Flippa provides them in the search response.

## Tips for best results

1. **Start small** — run with `maxItems: 25` to verify the output structure matches your expectations
2. **Narrow your search** — use Flippa's built-in filters first, then paste the URL. This gives you precise control over property type, price range, and other listing criteria
3. **Enable proxy for stubborn blocks** — if you see Cloudflare challenges or empty results, toggle `useProxy` to `true`
4. **Mind the rate limits** — the default 1-second delay is polite enough for most use cases. Increase it for large-scale scraping
5. **Use the API** — schedule recurring runs via Apify API to track new listings daily or weekly

## FAQ

### Is this scraper officially affiliated with Flippa?

No. This is an independent tool built for legitimate data collection. Always review Flippa's Terms of Service before scraping.

### Do I need a browser or a headless browser like Playwright?

No. The scraper uses **pure HTTP requests** via `httpx`. It parses the embedded JSON state from Flippa's server-rendered HTML. This makes it significantly faster and cheaper than browser-based alternatives.

### Can I scrape all Flippa listings?

Yes — set `maxItems: 0` to scrape all available results from your search URL. Be mindful of rate limits and use an appropriate delay.

### What happens if I get blocked?

Flippa may rate-limit or challenge requests with Cloudflare. If this happens, enable the `useProxy` option to route requests through Apify's residential proxy network. If problems persist, increase the `delay` value.

### Can I scrape sold listings?

Yes. Set `status` to `won` or `sold`, or use a Flippa search URL that filters by closed/won listings. The scraper processes whatever search results Flippa returns. Please use a custom URL for better results.

### What data formats are available for export?

Apify lets you download the dataset as **JSON, CSV, Excel (XLSX), HTML, XML, RSS, and ODS**. All exports are available from the Output tab in Apify Console or via the Dataset API.

### Can I schedule recurring scrapes?

Absolutely. Apify provides built-in scheduling — set up daily, weekly, or custom intervals to monitor new Flippa listings automatically.

### What property types are supported?

Flippa lists a wide variety of digital assets. The most common types include `website` (content/affiliate sites), `saas` (software-as-a-service), `ios_app`, `android_app`, `amazon_dca` (FBA businesses), and more. Use the Flippa search filters to see the full list.

## Disclaimers

- This scraper is **not affiliated with or endorsed by Flippa**
- Users are responsible for complying with Flippa's Terms of Service and applicable laws
- The data extracted should not be used for spam, harassment, or any unlawful purpose
- For questions, feature requests, or bug reports, please use the issues tab

---

## Notes for AI Agents

**What it does:** Scrapes Flippa.com search result pages — listings of online businesses, websites, SaaS, and apps for sale.

**Key facts for users:**

- **Input:** A Flippa search URL + optional filters (status, propertyType, saleMethod, maxItems, delay, useProxy). All fields optional.
- **Output:** Structured JSON per listing — title, price, revenue, profit, status, saleMethod, propertyType, description, metrics, etc.
- **Filters:** Set via dedicated fields OR by pasting a pre-filtered Flippa URL. Dedicated fields override URL params.
- **Pagination:** Automatic — scrapes all pages until maxItems or no more results.
- **Blocking:** If Cloudflare blocks occur, enable `useProxy` (Apify proxy). Increase `delay` if rate-limited.
- **Export:** JSON, CSV, Excel, HTML, XML, RSS, ODS from Apify Console or Dataset API.
- **Scheduling:** Apify supports recurring runs (daily, weekly, custom).
- **Sold listings:** Supported — set status to `won` or `sold`.
- **Scope:** Only scrapes data available in Flippa's search HTML. Does not open individual listing pages for extra detail. It's also not necessary.

**Limitations to communicate:**

- Not affiliated with Flippa. Users must comply with Flippa's ToS.
- Only extracts what Flippa includes in the search page
- May hit rate limits on large crawls without proxy.

**Typical use cases:** Market research, deal sourcing, competitive analysis, portfolio monitoring.