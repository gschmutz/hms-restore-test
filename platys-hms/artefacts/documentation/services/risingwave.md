# RisingWave

The streaming database: redefining stream processing. PostgreSQL-compatible, highly performant, scalable, elastic, and reliable.

**[Website](https://risingwave.com/)** | **[Documentation](https://docs.risingwave.com/docs/current/intro/)** | **[GitHub](https://github.com/risingwavelabs/risingwave)**

## How to enable?

```bash
platys init --enable-services RISINGWAVE, ETSD, MINIO
```

Make sure that the bucket `risingwave-bucket` is created by adding it to the setting in `config.yml`

```
      MINIO_buckets: 'risingwave-bucket'
```      

and then generate the platform

```
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:5691>
=======
Navigate to <http://10.156.72.251:5691>
>>>>>>> Stashed changes
