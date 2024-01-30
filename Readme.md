This is a test project to build a basic Rest API using the following stack:

* Python
* Docker, docker-compose
* Postgres
* Django

## Run it locally
docker-compose up -d --build

## Run migrations

docker-compose exec web python manage.py migrate


## Verify migrations

Connect to the local postgres db with

psql -h localhost -U post_user -d socialmedia
Password for user post_user:

same password used in docker_compose.yaml to setup the database
```yaml
      - POSTGRES_USER=post_user
      - POSTGRES_PASSWORD=testA123B
      - POSTGRES_DB=socialmedia
```

```sql
socialmedia=# \dt
                    List of relations
 Schema |            Name            | Type  |   Owner   
--------+----------------------------+-------+-----------
 public | auth_group                 | table | post_user
 public | auth_group_permissions     | table | post_user
 public | auth_permission            | table | post_user
 public | auth_user                  | table | post_user
 public | auth_user_groups           | table | post_user
 public | auth_user_user_permissions | table | post_user
 public | django_admin_log           | table | post_user
 public | django_content_type        | table | post_user
 public | django_migrations          | table | post_user
 public | django_session             | table | post_user
 public | posts_post                 | table | post_user
```