# ci
[![Build Status](https://drone.finthe.com/api/badges/gelove/demo/status.svg)](https://drone.finthe.com/gelove/demo)
### drone gogs 实现持续集成
### Application
#### Most of settings are obvious and easy to understand, but there are some settings can be confusing by running Gogs inside Docker:
- Repository Root Path: keep it as default value /home/git/gogs-repositories because start.sh already made a symbolic link for you.
- Run User: keep it as default value git because build.sh already setup a user with name git.
- Domain: fill in with Docker container IP (e.g. 192.168.99.100). But if you want to access your Gogs instance from a different physical machine, please fill in with the hostname or IP address of the Docker host machine.
- SSH Port: Use the exposed port from Docker container. For example, your SSH server listens on 22 inside Docker, but you expose it by 10022:22, then use 10022 for this value. Builtin SSH server is not recommended inside Docker Container
- HTTP Port: Use port you want Gogs to listen on inside Docker container. For example, your Gogs listens on 3000 inside Docker, and you expose it by 10080:3000, but you still use 3000 for this value.
- Application URL: Use combination of Domain and exposed HTTP Port values (e.g. http://192.168.99.100:10080/).
#### Full documentation of application settings can be found [here](https://gogs.io/docs/advanced/configuration_cheat_sheet.html).