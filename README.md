*FIELDS*

* Invoice
  * Mandatory
    1. Invoice number
    1. VAT / TAX ID
    1. Invoice Date
    1. Due Date
    1. Currency
    1. Total
    1. Tax Rate
    1. Tax Value
    1. Purchase Order
      - Other Names:
        - PO Number
    1. Order Id
      - e.g. ZT-TUO89A, DE-PM11DI, GB-KK12LN, US-CV90JP. The Order Ids starting with ZT does not exist anymore.
      - Other Names:
        - Release number
        - Purchase Order Number
    1. Additional Cost (e.g. Fuel Surcharge)
    1. Shipping Charges
    1. Handling Charges
      * Other Names:
        - Freight Charges

  * Optional
    1. Notes
      - e.g. 2% discount for payment within 10 days
    1. Rebate
    1. Shipment Via / Shipper
      - e.g. UPS, FEDEX
    1. Shipping Date
    1. Shipment Number
    1. Tracking Number
    1. DUNS
    1. Customer Number


* Line Item
  * Mandatory
    1. Item name / Description
    1. Price
    1. Currency
    1. Quantity (Shipped)
    1. Total
    1. Tax Rate
    1. Tax Value
    1. SKU
      - Other Names:
        - Article Number
        - Catalog Number

  * Optional

    1. Batch Number
    1. Notes
    1. List Price
    1. Rebate

*Notes*
  - Mandatory Fields:
    - These fields are must haves and should be implemented first.
    - In case the parser failed to find the respective value the csv output can have `null` value and will be handled in our side.

  - Optional Fields:
    - These fields are nice to haves and can be implemented next.
    - In case the parser failed to find the respective value the csv output can have `null` value and will be handled in our side.

  - Line Items:
    - We have items in the database that the customer has ordered and we have columns for additional costs and shipping & handling fee. In invoices there will be line items like `dry/wet ice`, `kuhlversand`, `shipping and handling cost`. These generally don't have SKU/article number (sometimes they do e.g. `ship2`). Can we get these items as an additional cost and shipping&handling cost? To make life easier it is possible for us to provide a set of SKUs which are to be searched for in the line items.
