[![Docker](https://github.com/BenjiTrapp/ssrf-playground/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/BenjiTrapp/ssrf-playground/actions/workflows/docker-publish.yml)

![](www/static/tag.png)

<br><br>
<img height="200" align="left" src="www/static/evilmonkey.png" > <br>Use this tiny playground to get more intouch with SSRF and some common ways what to do with such a vulnerability after you found one. This Challenge is thought to be part of a CTF Event and works fine in combination with CTFd or Facebooks CTF Framework. During your campaign this [SSRF Cheatsheet](https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html) might help you. This Challenge contains of three hidden flags. 
<br><br>
<br><br>
<br><br>

### Let's discuss your Mission
Docker containers have a lot of pitfalls, depending on the environment the container runs. This Image is build as a jack of all trades so you have multiple opportunities to learn from common mistakes.

**You will learn how to**:
1. Retrieve valueable which is stored in a file
2. Access kubernetes ServiceAccountToken (startingpoint to takeover a running Pod in k8s)
3. Hijack an AWS Account by raiding the EC2 metadata. The admin moved the regular IP `http://169.254.169.254` to `localhost:1338` - but there is no security by obscurity. 

### Solution and lessons learned
If you're done or just lame - take a look at my [Solution](https://github.com/BenjiTrapp/ssrf-playground/blob/main/exploit/SOLUTION.md). The most crucial part of this isn't the way on how to capute the flag, it's about the mitigation. Read it carefully and if I've missed something, please send me a Pull Request

### How to get started
The easiest way is to use the prebuild Docker image and spin the docker container up like usual: 

```bash
$ docker pull ghcr.io/benjitrapp/ssrf-playground:main
$ docker run docker run --name ssrf-playground -p 8080:80 -d -t ssrf-playground
```

Otherwise you can also build and run the Dockerfile locally. To start this simply use the Makefile like this:

```bash
# Build and run in one step
$ make all

# For control freaks use this path:
$ make run
$ make build
```

**Note:** Dependeing on your OS you may required to add `sudo` infront of each statement 


### Now some words of warning and disclaimer: 
> I'm not responsible for any harm caused by this CTF challenge. Do not deploy in productio and sandbox the Container since it's intentionally broken by design. 
