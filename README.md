# Reproducing loading failure on Odoo 13.0


## Through the "import" button on UI

1. Open a runbot in 13.0
2. Go to Inventory > Configuration > Settings. Activate Warehouse Locations
3. Go to Inventory > Configuration >  Locations. Click on Import
4. Select the file `stock.location.csv` present in this directory
5. Confirm the import


## Using the module

1. Create a new database
2. Install the module stock
3. Install the module `location_data`


## Expected behavior

We have new locations "Test 1" and a location "Test 2" under "STOCK".

## Current behavior:

All locations below "Stock" have been renamed and updated with the same values as the last record of the file that updates "Stock".

## Note
It seems to happen only if the XML for `stock.stock_location_stock`
contains the "active" field.
