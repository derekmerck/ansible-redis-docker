Ansible Role for Redis in Docker
================================

Derek Merck  
<derek_merck@brown.edu>  
Rhode Island Hospital and Brown University  
Providence, RI  

Configure and run a [Redis](https://redis.io) kv-store in a Docker container.


Dependencies
------------

### Galaxy Roles

- [geerlingguy.docker](https://github.com/geerlingguy/ansible-role-docker) to setup the docker environment
- [geerlingguy.pip](https://github.com/geerlingguy/ansible-role-pip) to install Python reqs


### Remote Node

- [Docker][]
- [docker-py][]

[Docker]: https://www.docker.com
[docker-py]: https://docker-py.readthedocs.io


Role Variables
--------------

Always uses the official [Redis][] image.

[redis]: https://hub.docker.com/_/redis/

Set the Redis version tag.

```yaml
redis_docker_image_tag:   "latest"
```


### Docker Container Configuration

```yaml
redis_container_name:     "redis"
redis_port:               6379
```

### Service Configuration

```yaml
redis_password:            "passw0rd!"
```


Example Playbook
----------------

```yaml
- hosts: redis_server
  roles:
     - derekmerck.redis_docker
```


License
-------

MIT