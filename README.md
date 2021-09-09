# optimise-gtm-conversion-tag
Optimise Conversion Tag GTM Template

# Overview
This tag will attempt to read from the Google Analytics Enhanched Ecommerce dataLayer [Google Analytics Enhanced Ecommerce](https://developers.google.com/tag-manager/enhanced-ecommerce) if available. 

If the Google Analytics Enhanced Ecommerce dataLayer is not available then the user should manually populate the Fields when adding the tag.

MID & PID must always be populated. All other Fields are only required if **not** using Google Analytics Enhanced Ecommerce dataLayer.

Further reading on implementing Google Analytics Enhanced Ecommerce for Conversions: https://developers.google.com/tag-manager/enhanced-ecommerce#purchases.

# Google Analytics Enhanced Ecommerce dataLayer Example

``` javascript
<script>
// Send transaction data with a pageview if available
// when the page loads. Otherwise, use an event when the transaction
// data becomes available.
dataLayer.push({
  'ecommerce': {
    'purchase': {
      'actionField': {
        'id': 'T12345',                         // Transaction ID. Required for purchases and refunds.
        'affiliation': 'Online Store',
        'revenue': '35.43',                     // Total transaction value (incl. tax and shipping)
        'tax':'4.90',
        'shipping': '5.99',
        'coupon': 'SUMMER_SALE'
      },
      'products': [{                            // List of productFieldObjects.
        'name': 'Triblend Android T-Shirt',     // Name or ID is required.
        'id': '12345',
        'price': '15.25',
        'brand': 'Google',
        'category': 'Apparel',
        'variant': 'Gray',
        'quantity': 1,
        'coupon': ''                            // Optional fields may be omitted or set to empty string.
       },
       {
        'name': 'Donut Friday Scented T-Shirt',
        'id': '67890',
        'price': '33.75',
        'brand': 'Google',
        'category': 'Apparel',
        'variant': 'Black',
        'quantity': 1
       }]
    }
  }
});
</script>
```