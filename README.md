# Marketplace Cleanup (uBlock Origin)

Direct filter lists to remove Facebook Marketplace item blocks, eBay-sourced listings, and “Delivered to you” / “Shipped” modules. 

## Subscribe
1. Open uBlock Origin dashboard  
2. Go to **Filter lists → Custom → Import… / Add a list**  
3. Paste this URL:  
   ```
   https://raw.githubusercontent.com/137137137/ublock-facebook-marketplace-filters/main/filters/facebook-marketplace.txt
   ```
4. Apply changes → Update now  

## Files
- `filters/facebook-marketplace.txt` — Facebook rules  

## Rules Included
```
! Facebook Marketplace item tiles (icon fingerprint)
facebook.com##a[href^="/marketplace/item/"]:has(svg path[transform*="translate(-444 -156)"]):upward(8)

! Marketplace tiles with generic 16×16 icon (fallback)
facebook.com##div[data-virtualized="false"]:has(svg[width="16"][height="16"] path[transform]):upward(2)

! Card blocks with specific SVG path fingerprint
facebook.com##div[style*="max-width:381px"]:has(svg path[d^="M99.75 20.5"]):upward(2)

! Hide “Delivered to you” modules
facebook.com##div[style*="max-width:381px"]:has(span:has-text(/Delivered to you/i)):upward(2)

! Hide “Shipped” listings/modules
facebook.com##div[style*="max-width:381px"]:has(span:has-text(/Shipped/i)):upward(2)

! Hide Marketplace cards that link out to eBay
facebook.com##div[style*="max-width:381px"]:has(a[href*="ebay.com"]):upward(2)
```

## Requirements
- uBlock Origin  
- Cosmetic filtering enabled   

## License
MIT License  
