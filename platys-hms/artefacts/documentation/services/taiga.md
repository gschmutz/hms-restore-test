# Taiga 

Taiga is a free and open-source project management for cross-functional agile teams. 

**[Website](https://taiga.io/)** | **[Documentation](https://community.taiga.io/c/learn-taiga-basic)** | **[GitHub](https://github.com/taigaio/taiga)**

## How to enable?

```
platys init --enable-services TAIGA
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:28323>.
=======
Navigate to <http://10.156.72.251:28323>.
>>>>>>> Stashed changes

### Creating an admin user

To create an admin user, perform 

```bash
docker exec -ti taiga-back python manage.py createsuperuser
```

and you are prompted for username, email address and password. 