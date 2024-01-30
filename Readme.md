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

## Create Posts 

Enter Name and Category of the Post

![Screenshot 2024-01-30 at 5 23 01 PM](https://github.com/kiranpers/social_media_django/assets/8075190/a87f0426-edfc-48d5-8e77-3f12e366fb8a)

## List posts

![Screenshot 2024-01-30 at 5 23 24 PM](https://github.com/kiranpers/social_media_django/assets/8075190/6d6ad6da-123e-4430-9de8-897b43628086)
