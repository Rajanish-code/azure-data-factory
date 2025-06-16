# azure-data-factory

🚀 ADF Pipelines - Country & DB Data Copy
✅ 1. Fetch 5 Country Data from REST API
Use FetchCountriesPipeline to loop over 5 countries (India, US, UK, China, Russia)

Calls CountryRestSourceDs to fetch and save each as {country}.json in ADLS

🕒 2. Trigger
Schedule Trigger1 at 12:00 AM & 12:00 PM IST

📊 3. Copy Customer Data Conditionally
MainPipeline
 ├── LookupCustomerCount
 ├── If (count > 500)
 │    ├── CopyCustomerData
 │    └── If (count > 600)
 │         └── Execute ChildPipeline (with customerCount param)
 
ChildPipeline (Parameter: customerCount)
 └── If (customerCount > 600)
      └── CopyProductData

📁 Output Folder in ADLS
/p2/, /customer/, /products/
