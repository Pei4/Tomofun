# Tomofun Project Wiki
## Stakeholders
### Managers
- CFO: Ken
- Finance, ERP project manager: Eric
- Business Process: Tina
- Operation: Dennis
### Staffs
- Finance: Mia
- Business Process: Justin
- Operation: Liane, Wendy, Serena
- IT: Roy

## Important Change in 2023R1
- Activate "Disable Automatic Tax Calculation" for Order Type "FA" and "SP"
  - Be aware
    - Tax Calculation Mode in **Customer**, **Customer Location** and **Taxes** need to be "Tax Setting" or "Exclusive"
    - For those Marketplaces whose tax should be calculated automatically by the system, the "Tax Calculation" in **Marketplace Preference - Amazon / Shopify** should be checked
      - The system will uncheck the "Disable Automatic Tax Calculation" in Finance tab for those specific orders

## Customizations
### 1. EC Transactions & Payments  
- Roy calls Amazon / Shopify API (JSON) into **Amazon / Shopify API Interface**
- Automation Schedule translate JSON into table in **Amazon / Shopify Transactions**
  - [Translation Spec](https://1drv.ms/x/s!AhdB9H8nvN7jhpMdhlkuydLqJOqQ5Q?e=ThoZri)
- Automation Schedule process table into SO and Invoice
  - Process Amazon Order [Spec](https://1drv.ms/w/s!AhdB9H8nvN7jhot78hBqW1mIf27jpQ?e=MYtYSy)
  - Process Shopify Order [Spec](https://1drv.ms/w/s!AhdB9H8nvN7jhot62Tu9tJJiy5caIw?e=PZcsw8)
- Eric manually upload Payment into **Amazon / Shopify Payment Upload**
  - Process Amazon Payment [Spec](https://1drv.ms/w/s!AhdB9H8nvN7jhpJQ9h4UAiWxF3N6aA?e=9gLJes)
  - Process Shopify Payment [Spec](https://1drv.ms/w/s!AhdB9H8nvN7jhop5MaOmAI1S0UbbGw?e=Urkpcw) (Include ShopifyPay, AmazonPay, PayPal, JP-NP, JP-Docomo)
### 2. Inventory Reconciliation
- PSI Report
- Daily Inventory & Reconciliation
- FBA IN Report
  - MWS Setup: [Amazon API Connection Key](https://1drv.ms/t/s!AhdB9H8nvN7jhodNGu724H7wiFf4Cw?e=7ThuEP)
  - Automation Schedule call API to get inventory data in 14 days
- 3PL IN Report
  - 3PL Preference: API Keys (Topest, Return Helper, FEDEX, Google Sheet)
  - Be aware: **Should only process in TW tenant**
