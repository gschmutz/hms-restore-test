# Streamlit

Streamlit turns data scripts into shareable web apps in minutes.
All in pure Python. No front‑end experience required.

**[Website](https://streamlit.io/)** | **[Documentation](https://docs.streamlit.io/)** | **[GitHub](https://github.com/streamlit/streamlit)**

## How to enable?

```
platys init --enable-services STREAMLIT
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:28340>. 
=======
Navigate to <http://10.156.72.251:28340>. 
>>>>>>> Stashed changes

By default the `HelloWorld` Streamlit application is used which is available in `./scripts/streamlit/apps/hello-world/hello-world.py`. Just create your application by adding a new folder to the `./scripts/streamlit/apps` and place the python code there. 

Then configure platys to pick it up my changing the `config.yml` file to

```yaml
      STREAMLIT_enable: true
      STREAMLIT_image: 'python'
      STREAMLIT_artefacts_folder: './scripts/streamlit/apps'
      STREAMLIT_apps: 'my-app/my-app.py'
      STREAMLIT_apps_description: 'My Streamlit App'
```

