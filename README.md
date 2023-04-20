# v0.0.3

## Instructions

1. Upload nominees.csv and villages.csv as server datasets called "nominees" and "villages". nominees.csv has a "dummy nominee" for each village, which the form uses to enable creation of new nominees.
1. Upload form definition nominations.xlsx. Attach server datasets: YES, select nominees and villages.
1. In the nominees server dataset, click "Publish into", click "Add a form", select nominations, and enter the following:
    
    Form field to identify unique records (optional): nominee_key*
    
    Include form submissions whenever this field is 1 (optional): *(none)*
    
    Treatment of fields inside repeat groups: Publish to long format (one row per repeat instance)
    
    Mapping from form fields to dataset columns:
    
    | Field name | Update action | Column name |
    | --- | --- | --- |
    | district_id | Replace | district_id |
    | district_name | Replace | district_name |
    | village_id | Replace | village_id |
    | village_name | Replace | village_name |
    | zero | Replace | nominee_new |
    | nominee_key* | Replace | nominee_key |
    | nominee_name* | Replace | nominee_name |
    | nominee_phone* | Replace | nominee_phone |
    | nominee_label* | Replace | nominee_label |
    | one | Add | n_nominations |
1. Go to the Collect page, and fill out the nominations form. If you select "Create a new nominee" in one form submission, that nominee should be visible in the next form submission. In some cases, the updating may take a few minutes, or the first round of nominees may not immediately be visible on the second form submission. You may be able to force an update of the nominees server dataset on the Design page.
1. If you download the nominees server dataset, you should see a column n_nominations that keeps a running count of the number of nominations per nominee.
