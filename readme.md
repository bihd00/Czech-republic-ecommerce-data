# Czech republic e-commerce data

This repository contains a dataset of more than 10 million product records from 5 of the largest e-commerce companies in Czech republic, collected during Q3 and Q4 2021. <br>
- In particular, the dataset focuses on products from consumer electronics industry (phones, laptops, PCs, freezers, smart gadgets etc.).
- The data as such has been scraped via custom python scraper - built using [pyppeteer](https://github.com/pyppeteer/pyppeteer) (may be shared in future). 
- The frequency of the data is daily, meaning in ideal case, for any distinct product, there would be more than 100 records. Such is not the case, however, for many products there is more than 50 records. On average, there is 30 records per product, of which there are more than 300 000.

## Main Table structure
The main tables used to construct the "final" dataset are listed below.

| Table         | Description                                           |
|---------------|-------------------------------------------------------|
| eshops        | IDs and names                                         |
| categories    | IDs and names, linked to eshops                       |
| subcategories | IDS and names, linked to categories                   |
| products      | IDs and names, linked to categories and subcategories |
| prod_specs    | The actual scraped data, linked to products           |

In order as listed, joining the table produces the final dataset. Variables /features contained in the dataset are listed below. Columns starting "alza" up to "okay" (e-shop names) indicate weather such data is present on a given e-shop's websites (was being scraped).

| Variable      | Description                                                  | alza | mall | czc | datart | okay |
|---------------|--------------------------------------------------------------|------|------|-----|--------|------|
| e_id          | eshop ID                                                     | x    | x    | x   | x      | x    |
| e_name        | eshop name                                                   | x    | x    | x   | x      | x    |
| c_id          | category ID                                                  | x    | x    | x   | x      | x    |
| c_name        | category name                                                | x    | x    | x   | x      | x    |
| s_id          | subcategory ID                                               | x    | x    | x   | x      | x    |
| s_name        | subcategory name                                             | x    | x    | x   | x      | x    |
| p_id          | product ID                                                   | x    | x    | x   | x      | x    |
| p_name        | product name                                                 | x    | x    | x   | x      | x    |
| dt_added      | datetime of product record                                   | x    | x    | x   | x      | x    |
| price_bef     | price before discount (if any)                               | x    | x    | x   | x      | x    |
| price_aft     | price after discount (if any).  Always stores original price | x    | x    | x   | x      | x    |
| price_exvat   | price without VAT                                            | x    |      |     |        | x    |
| discount      | discount (0-1)                                               | x    | x    | x   | x      | x    |
| review_amount | review amount                                                |      | x    | x   |        |      |
| review_score  | review score (0-5)                                           | x    | x    | x   |        | x    |
| stock_amount  | stock amount                                                 | x    |      | x   |        | x    |
| stock_more    | is there more on stock ? (0 \|\| 1)                          | x    | x    | x   | x      | x    |
| delivery_dt   | delivery date                                                | x    | x    |     | x      |      |

## Other tables included

| Table             | Description                                                                   |
|-------------------|-------------------------------------------------------------------------------|
| bad_prod_ids      | IDS of products found to have flawed or no data                               |
| lp_store          | scraper inputs - contains urls of given (sub)categories                       |
| same_products     | IDs of products sharing the same name (could be within the same e-shop)       |
| similiar_products | IDs of products having almost the same name (could be within the same s-shop) |


--- 
## Download instructions
The dataset is currently available to download as an SQL dump via [Google Drive](https://drive.google.com/drive/folders/17u-0lQ4dgCDCw0cNRxTIdgjwnPUkBMM6?usp=sharing)
<br>


### Have fun ![](https://cdn.discordapp.com/emojis/769486756977967114.gif?v=1&size=32)
