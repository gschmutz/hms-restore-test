# Oracle Autonomous Database Free

Oracle Autonomous Database is a cloud-based database service that uses machine learning to automate database management tasks like patching, tuning, backups, and scaling, eliminating the need for manual intervention. It comes in two main flavors: Autonomous Data Warehouse (ADW) for analytics and Autonomous Transaction Processing (ATP) for transactional and mixed workloads.

**[Website](https://www.oracle.com/autonomous-database/)** | **[Documentation](https://www.oracle.com/autonomous-database/get-started/)** | **[Github](https://github.com/oracle/adb-free)**

## How to enable?

```
platys init --enable-services ORACLE_ADB_FREE
platys gen
```

## How to use it?

### Connect through SQL Plus

```
alias adb-cli="docker exec oarcle-adb adb-cli"
```

### Connect through JDBC

<<<<<<< Updated upstream
* **JDBC Url:**  	`jdbc:oracle:thin:@192.168.1.112:1525/ATP`
=======
* **JDBC Url:**  	`jdbc:oracle:thin:@10.156.72.251:1525/ATP`
>>>>>>> Stashed changes
* **JDBC Driver Class Name:** 	`oracle.jdbc.driver.OracleDriver`
