# Web Protégé

WebProtégé is a free, open source collaborative ontology development environment.

**[Website](https://protege.stanford.edu/software.php#web-protege)** | **[Documentation](https://protegewiki.stanford.edu/wiki/WebProtegeUsersGuide)** | **[GitHub](https://github.com/protegeproject/webprotege)**

## How to enable?

```
platys init --enable-services WEB_PROTEGE
platys gen
```

## How to use it?

Before you use the UI for the first time, you need to create the admin user, using the following command:

```bash
docker exec -it web-protege java -jar /webprotege-cli.jar create-admin-account
```

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:28368>.
=======
Navigate to <http://10.156.72.251:28368>.
>>>>>>> Stashed changes
