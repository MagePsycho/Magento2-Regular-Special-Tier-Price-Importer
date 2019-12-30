## Overview:
[Magento 2 Regular, Special & Tier Price Importer](https://www.magepsycho.com/extensions/magento-2/magento2-mass-regular-special-tier-group-price-importer.html) is the fastest import tool for bulk updating different prices like regular, cost, MSRP/MAP, special, tier & customer group price.

![Magento 2 Regular, Special & Tier Price Importer Extension Backend Demo](http://g.recordit.co/9t1Dt1srQD.gif)

Magento 2 has built-in data transfer for importing products and advanced pricing. But it lacks the functionality of updating all types of prices whether it's regular or advanced pricing in a single go.
Also, the native import has very limited options for pricing.

With this extension, store admin can achieve the simplest & fastest way to import all types of pricing with just a single CSV file(more import sources will be added soon).
And with the export pricing option, store admin can easily prepare the import file.

## Key Features
* Provides bulk update for all types of price with just a single CSV file - *more import sources will be added soon*
* Option to preview the uploaded file which gives the glance view of the file data
* The detailed error message provided during import validation helps to fix the price data faster
* Support for different types of price rounding (whole number to the psychological pricing)
* Price values can be increased(+), decreased(-) by a fixed amount value or percentage
* Price values can also be set as a certain percentage of some reference attribute value
* Option to export the different prices which makes import file preparation much easier

## Feature Highlights

### Import Regular, Special, Tier, Customer Group Price, etc.
With this extension, store admin can bulk update(add/update or delete) any type of prices with just a single CSV file.  
Supported price types by the extension:  

* Regular Price
* Special Price with From and To Dates
* Cost
* Manufacturer's Suggested Retail Price (MSRP) / Minimum Advertised Price (MAP)
* Tier Price / Customer Group Price
* Custom Decimal Price Attributes - *coming soon*
Note: 'Group Price' in Magento 2 is the special case of Tier Price (with tier qty equals to 1).

### In-Depth Import Data Validation
All pricing data must pass validation before it can be imported into the system, to ensure that the values are consistent with the system database.  
If validation fails, the extension describes each error. This helps the store owner to quickly find and correct the problem in the CSV file.  

Validation is done on the header(column) level and data(row) level.  
Some of the validation messages looks like:
![MIP Price Importer Validation Sample](https://www.magepsycho.com/media/catalog/product/7/-/7-3-magento2-mip-price-importer-validation-sample.png)

### Fancy Uploader with CSV File Preview
This extension comes with a fancy uploader for drag and drop uploading with an option to preview the imported CSV file.  
This option is super helpful in checking the CSV data structure(For Ex: if rows & columns are properly formatted or not).  

![CSV Uploader with File Preview](https://www.magepsycho.com/media/catalog/product/6/-/6-2-magento2-mip-price-importer-csv-file-previewer.png)

### Relative Price Updates
With this extension, any price can be updated by increasing(+) or decreasing(-) by fixed amount or percentage.  
Also, the price value can be specified as a percentage of some reference attribute value.  
*(The reference attribute for markup pricing can be configured from the extension settings)*

Supported example of values for relative price updates are described below:  

|Value|Description|
|--- |--- |
|+10|Increase the current value by 10|
|-10|Decrease the current value by 10|
|10%|10% of the reference price value *(note that there is no sign in the prefix)*  Reference based pricing applies only for price types: *msrp*, *special_price*. But for *tier_price* & *group_price*, X% represents the discount|
|+10%|Increase the current value by 10%|
|-10%|Decrease the current value by 10%|


### Price Rounding Options
Price values will likely have complex decimal values.  
Rounding them off to the nearest whole number or the nearest 0.99 (for psychological or strategic pricing) is practical and recommended.  
With this in mind, this import extension provides three types of options for price rounding:  

| Rounding Type    | Description                                                                                                                                                                       |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| No Rounding      | No action with the price                                                                                                                                                          |
| Round Normally   | Uses PHP's round() function.Examples:  9.43 -> 9.00  9.63 -> 10.00                                                                                                                |
| Round to Nearest | Used for psychological or strategic pricing(like *.99, *.50, etc.). Examples:  9.43 -> 9.00 + (If Rounding Value = 0.99) = 9.99  9.43 -> 9.00 + (If Rounding Value = 0.50) = 9.50 |

### Export Pricing
Updating Regular Price & Special Price might be comparatively easier. But updating tier price can be time-consuming because of the multiple level price it owns.  
With this extension, you can filter the products and select the price types you wanted for the export.  

Once the required price data is exported, the store admin can easily prepare the price data and perform the bulk update.

![Magento 2 Pricing Export/Download](https://www.magepsycho.com/media/catalog/product/9/-/9-3-magento2-mip-price-importer-export-pricing-download.png)

## Installation
1. Download the extension .zip file and extract the files.
1. Copy the extension files from src/ folder to the {magento2-root-dir}/
1. Run the following series of command from SSH console of your server:
```
php bin/magento module:enable MagePsycho_MassImporterPro MagePsycho_MipPricing --clear-static-content
php bin/magento setup:upgrade
```
1. Flush the store cache
```
php bin/magento cache:flush
```
1. Go to Admin > SYSTEM > Mass Importer Pro > Here you can import, export & configure settings

## Live Demo:
*Coming Soon*

## Changelog
**Version 1.0.0 (2019-12-25)**
    
* Initial Release.
