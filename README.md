# Perforce Server for Unreal in a Docker container

This is a fork of [`snipe3000/Perforce-Server-On-Docker-For-Unreal`](https://github.com/Snipe3000/Perforce-Server-On-Docker-For-Unreal). Updated to use the latest version of perforce server and switched over to ubuntu. CentOS is no longer being maintained. Additional work is being done to get this to work with Unraid's built-in container manager.

P4 code review (Swarm) and redis have also been added.

Swarm requires two p4 accounts to work, the super account (p4admin) that is made from the script and a regular user account. I made one called "Van" that you can change throught the files if you'd like.

Feel free to add a custom networking setup to the docker-compose.yml. Keep in mind, the p4d server, swarm, and redis work with less trouble if they are all on the same network, otherwise you'll have to do some host name ninjutsu.

I have confirmed that this will work within Docker Compose Manager through Unraid.

- Original project: https://github.com/HaberkornJonas/Perforce-Server-On-Docker-For-Unreal
- Other P4-Docker setup that works: https://github.com/projects-land/p4d-docker

Remember to connect your p4v to your swarm server, for example:
```
p4 -p "ssl:192.168.1.238:1666" property -a -n P4.Swarm.URL -v "http://192.168.1.238:8089/"
```
[Help through Perforce's official docs](https://help.perforce.com/helix-core/server-apps/p4sag/current/Content/P4SAG/superuser.configure_p4v.swarm.html?tocpath=Configuring%20the%20Server%7CConfiguring%20P4V%20settings%7C_____3)
