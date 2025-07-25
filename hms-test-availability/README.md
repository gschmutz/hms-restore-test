# Test Availability of Hive Metastore Service

Tests if Hive Metastore Service (HMS) is up and running and can be used over the Thrift API.

Currently only list operations (for catalogs, databases and tables) are used, only testing read-only operations on Hive Metastore. 
The create, alter and drop of a table needs to be implemented as well, to also test write operations on the Hive Metastore.

## Prepare environment

```bash
python3.11 -m venv venv
source venv/bin/activate

pip install -r requirements.txt
```

## Generate Thrift objects (optional)

Perform this step, if you don't want to use the generated version of the code available in `gen-py` folder.

```bash
thrift --gen py thrift_defs/share/fb303/if/fb303.thrift
thrift --gen py thrift_defs/hive_metastore.thrift
```

## Run the tests

Set environment variables

```bash
export HMS_HOST=localhost
export HMS_PORT=9083
```

### Run it in verbose mode

```bash
pytest hms-test-availability.py --verbose
```

### Run it with html result

```bash
pytest hms-test-availability.py --html ./report/db-compare.html
```

### Run it with junit result

```bash
pytest hms-test-availability.py --junitxml=./junitresult/db-compare.xml
```

format it to an HTML page
```bash
docker run --rm -v ./junitresult:/results maxmiorim/junit-viewer > ./report/junit-hms-availability.html
```
