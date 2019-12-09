# BigQueryLoadingANDQuery
# bq show bq_load_codelab.customer_transactions
 
bq query --nouse_legacy_sql '                
SELECT SUM(c.amount) AS amount_total, z.state_code AS state_code
FROM `bq_load_codelab.customer_transactions` c
JOIN `bigquery-public-data.utility_us.zipcode_area` z
ON c.zip = z.zipcode
GROUP BY state_code
'
