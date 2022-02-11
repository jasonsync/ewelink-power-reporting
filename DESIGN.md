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
 - **id** = (int 11)
 - **name** (varchar 100)
 - **group** (varchar 100) _NULL_
 - **ewelink_name** (varchar 100) _NULL_
 - **ewelink_group** (varchar 100) _NULL_
 - **ewelink_device_id** (int 11)
 - **ewelink_account_id** (int 11)
 - **site_id** (int 11) _NULL_
 - **last_successful_data_retrieval** (timestamp) _NULL_
 - **created_timestamp** (timestamp) _current_timestamp()_
 - **created_by_user_id** (int 11) _NULL_
 - **created_timestamp** current_timestamp() (timestamp)
 - **created_by_user_id** int _NULL_


#### sites = specific site
 - id = int
 - name = varchar
 - address = varchar
 - longitude = varchar
 - latitude = varchar
 - site_group_id = NULL
 - kwh_cost_cents = varchar
 - created_timestamp = current_timestamp() (time this row was inserted)

#### site_groups = group of sites
 - id = int
 - name = varchar
 - description = varchar
 - created_timestamp = current_timestamp() (time this row was inserted)

#### ewelink_accounts
- id
- name
- description
- ewelink_email
- ewelink_password
- ewelink_region
 - created_timestamp = current_timestamp() (time this row was inserted)

#### power_consumption_log
 - id = int
 - device_id = int
 - date = datetime (there should be one record per day)
 - created_timestamp = current_timestamp() (time this row was inserted)

#### monthly_reports
 - id = int
 - device_id = int
 - month = int
 - year = int
 - consumption_wh = varchar
 - total_cost_cents = varchar
 - created_timestamp = current_timestamp() (time this row was inserted)
