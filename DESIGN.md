https://github.com/jasonsync/ewelink-power-reporting

logging service:
node.js logging service to retrieve data from each device and save to database
Dependencies: https://github.com/jasonsync/ewelink-api-fixed

email reporting service:
node.js reporting service to send email report once a day / week / month

  ```sql
  SELECT * FROM your_table WHERE month(create_date) = 5
  ```



### DATABASE:

#### devices:
 - id = int
 - name
 - group
 - ewelink_name
 - ewelink_group
 - ewelink_device_id = int
 - account_id = int
 - site_id = int
 - last_successful_data_retrieval = datetime


#### sites = specific site
 - id = int
 - name = varchar
 - address = varchar
 - longitude = varchar
 - latitude = varchar
 - site_group_id = NULL
 - kwh_cost_cents = varchar

#### site_groups = group of sites
 - id = int
 - name = varchar
 - description = varchar

#### accounts
- id
- name
- description
- ewelink_email
- ewelink_password
- ewelink_region

#### power_consumption_log
 - id = int
 - device_id = int
 - date = datetime (there should be one record per day)
 - datetime_logged = datetime (time this row was inserted)

#### monthly_reports
 - id = int
 - device_id = int
 - month = int
 - year = int
 - consumption_wh = varchar
 - total_cost_cents = varchar
