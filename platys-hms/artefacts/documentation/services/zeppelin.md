# Apache Zeppelin

Web-based notebook that enables data-driven, interactive data analytics and collaborative documents with SQL, Scala and more. 

**[Website](https://zeppelin.apache.org/)** | **[Documentation](https://zeppelin.apache.org/)** | **[GitHub](https://github.com/apache/zeppelin)**

## How to enable?

```
platys init --enable-services ZEPPELIN
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:28080>
=======
Navigate to <http://10.156.72.251:28080>
>>>>>>> Stashed changes

## Install `s3cmd`

install `s3cmd`

```bash
pip install s3cmd
```

and configure it

```bash
s3cmd --no-ssl --access_key=$AWS_ACCESS_KEY_ID --secret_key=$AWS_SECRET_ACCESS_KEY --host-bucket=$AWS_ENDPOINT --host=$AWS_ENDPOINT  --bucket-location=$AWS_DEFAULT_REGION  --dump-config 2>&1 | tee .s3cfg
```
