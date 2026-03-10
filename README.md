## DB Setup:
- Deploy RDS Mysql DB
- Take a ssh to EC2 run below commands

```
docker run -it --rm mysql:8.0 bash

kubectl run temp-mysql \
  --rm -it \
  --image=mysql:8.0 \
  --restart=Never \
  --command -- bash

mysql -h database-1.chwk0ee0ig63.ap-south-1.rds.amazonaws.com -P 3306 -u admin -p
CREATE DATABASE webappdb;
SHOW DATABASES;
USE webappdb;

CREATE TABLE IF NOT EXISTS transactions(id INT NOT NULL
AUTO_INCREMENT, amount DECIMAL(10,2), description
VARCHAR(100), PRIMARY KEY(id));

SHOW TABLES;
INSERT INTO transactions (amount,description) VALUES ('400','groceries');
SELECT * FROM transactions;
```
<img width="1363" height="501" alt="image" src="https://github.com/user-attachments/assets/1cbc31a8-52c0-4b93-b007-65f79d9d4d67" />
