# Bunniecode Checkout Logger for WooCommerce

See why checkouts fail. Checkout Logger records each step of the WooCommerce checkout and every error along the way, so you can answer "why didn't this order go through?".

A commercial plugin by [Bunniecode](https://github.com/bunnie-code), sold through [bunniecode.eu](https://bunniecode.eu).

## What it records

| Area | Events |
|---|---|
| Cart | Add to cart, add to cart blocked, item removed, cart emptied, cart hash mismatch |
| Checkout | Checkout started, empty cart at checkout, validation errors, checkout submitted, expired nonce, payment attempt |
| Orders | Payment failure, order completed, every status change, thank-you page reached |
| Coupons | Applied, removed |
| Shipping | Shipping method chosen |
| Accounts | Failed login at checkout, customer created |
| Browser (optional) | Shipping method changed, Place order clicked, JavaScript errors, unhandled promise rejections |

## Features

- Log viewer under **WooCommerce → BunnieCode Logger**, filtered by event, payment gateway, date or search text and grouped by session. Bot traffic is dimmed.
- CSV export, plus an anonymised CSV that masks emails, IP addresses, card details and phone numbers before you share it.
- Retention from 7 to 180 days, with automatic cleanup.
- Works with the classic checkout and the Checkout block.
- Compatible with High-Performance Order Storage (HPOS).
- Its own database table: nothing is added to `wp_options` or post meta.
- Light on the store: one database insert per event. The optional browser script sends with `navigator.sendBeacon()` and never holds up the checkout.

Checkout Logger is a diagnostic tool. It does not do funnel analytics, cart recovery emails or A/B tests.

## For developers

Everything that differs between stores is a filter, so a theme or plugin can extend it without editing the plugin:

| Filter | Use |
|---|---|
| `wcl_event_registry` | Register or override events |
| `wcl_tracked_cookies` | Record custom cookie values with every log row |
| `wcl_tracked_session_keys` | Record WooCommerce session keys and log when they are cleared |
| `wcl_beacon_listeners` | Add browser listeners for clicks, changes or elements shown |
| `wcl_event_context` | Add data to an event's context |
| `wcl_bot_signatures` | Adjust the bot user-agent list |

## Privacy

Logs can include the customer's email address and other checkout details. They stay in your site's database and are deleted after the retention period you set. The plugin makes no calls to outside services.

## Requirements

| | |
|---|---|
| Current version | 2.1.2 |
| WordPress | 6.0 or later |
| WooCommerce | 7.0 or later, tested up to 9.6 |
| PHP | 7.4 or later |

## Support

Licensed customers get updates and support through [bunniecode.eu](https://bunniecode.eu).

## License

GPL v2 or later. A licence key gives access to updates and support.
