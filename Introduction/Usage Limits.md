# Usage Limits 
Map views and endpoints are rate limited on a per second basis. That means that once your application has hit the limit, you'll receive an HTTP 429 error response until the limit resets the following second.

Monthly API Requests are divided into 30 equally sized daily request limits and enforced at the daily rate.
[block:parameters]
{
  "data": {
    "h-0": "Limits",
    "0-0": "API Requests",
    "1-0": "Map View Requests",
    "2-0": "Enterprise Tier - above 200,000 Users",
    "0-1": "2 requests / second",
    "h-1": "Community",
    "1-1": "4 requests / second",
    "2-1": "40 requests / second",
    "h-2": "Growth",
    "h-3": "Scale",
    "0-2": "10 requests / second",
    "0-3": "100 requests / second",
    "1-2": "12 requests / second",
    "1-3": "1,000 requests / second"
  },
  "cols": 4,
  "rows": 2
}
[/block]

#### Traffic Surge Protection for Growth and Scale plans",
2X surge protection included for Growth and Scale tiers: 2X daily API Request limits is forgiven for up to 2 days per month.
Free Tier is capped at stated daily and monthly limits
## Increase your limits
Rate limits are global and are enforced on a per-client ID basis. If you would like an increase for your application, please contact us at [team@mapfit.com](mailto:team@mapfit.com).