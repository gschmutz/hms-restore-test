# Langflow

Langflow is a dynamic graph where each node is an executable unit. Its modular and interactive design fosters rapid experimentation and prototyping, pushing hard on the limits of creativity. 

**[Website](https://www.langflow.org/)** | **[Documentation](https://docs.langflow.org/)** | **[GitHub](https://github.com/langflow-ai/langflow)**

## How to enable?

```
platys init --enable-services LANGFLOW,POSTGRESQL
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:7860>.
=======
Navigate to <http://10.156.72.251:7860>.
>>>>>>> Stashed changes

### Load flows on startup

Place flow JSON files to be loaded on startup into `./init/langflow/` folder. Note that this feature only works if `LANGFLOW_auth_enable` is disabled.

### Provide custom components

Place custom components into `./plugins/langflow` and set `LANGFLOW_volume_map_components` to `true`.