# Jupyter

Open-source software, open standards, and services for interactive computing across dozens of programming languages.

**[Website](https://jupyter.org/)** | **[Documentation](https://jupyter.org/documentation)** | **[GitHub](https://github.com/jupyter/notebook)**

## How to enable?

```
platys init --enable-services JUPYTER
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:28888>. The token for the login has either be specified in the `config.yml` (`JUPYTER_token`) or if not set, the generated token can be retrieved from the log (`docker logs -f jupyter`). 

If you enable the `all-spark` edition and run spark, then the Spark UI will be available at <http://192.168.1.112:28376> or any other port until `28380`.
=======
Navigate to <http://10.156.72.251:28888>. The token for the login has either be specified in the `config.yml` (`JUPYTER_token`) or if not set, the generated token can be retrieved from the log (`docker logs -f jupyter`). 

If you enable the `all-spark` edition and run spark, then the Spark UI will be available at <http://10.156.72.251:28376> or any other port until `28380`.
>>>>>>> Stashed changes
