# AnjeloPeiris711.github.io
## Hi there <picture><source srcset="https://fonts.gstatic.com/s/e/notoemoji/latest/1f44b/512.webp" type="image/webp"><img src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f44b/512.gif" alt="👋" width="32" height="32"></picture> , You can call me Anjelo Peiris
#### I am undergraduate Students of Plymouth University & NSBM University 
<img align="left" alt="nick" width="325" src="https://images6.fanpop.com/image/photos/41200000/IMG-1970-PNG-nick-wilde-41239315-702-970.png">
<p align ="right" style="color:green; writing-mode: vertical-rl;">I made this project just for fun,it allows me to create nice and simple blog</p>

> How to Install Nessus in wsl(26/09/2022)

if you  trying to install nessus for a vulnerability study in Kali linux. Kali is running as a Win-Kex instance from WSL2 on windows 11. I have downloaded Nessus and trying to install with:

```python
~/root💀junior# sudo dpkg -i Nessus-10.3.0-debian6_amd64.deb
```

But you are getting error as ...

```python
~/root💀junior# System has not been booted with systemd as init system (PID 1). Can't operate
```
I guess this is because WSL2 doesn't actually "boot up" Linux, instead Linux behaves like a docker container without any kind of init system.The easiest way to install is as a docker image.

So you can try this

```python
~/root💀junior# docker pull tenableofficial/nessus
```

After that

```python
~/root💀junior# docker run -d --name tenableofficial_nessus -p 8834:8834 tenableofficial/nessus
```
And that’s it! Now the container should be running and we can open https://localhost:8834/ and activate our new shiny Nessus instance.

----
> How to fix situation Error ERESOLVE could not resolve [duplicate](09/10/2022)

After running ```npm install``` I'm getting this error:

```json
  npm ERR! code ERESOLVE
  npm ERR! ERESOLVE could not resolve
  npm ERR! 
  npm ERR! While resolving: client@0.0.0
  npm ERR! Found: @angular/compiler@11.0.9
  npm ERR! node_modules/@angular/compiler
  npm ERR!   @angular/compiler@"^11.0.7" from the root project
  npm ERR!   peer @angular/compiler@"11.0.9" from @angular/compiler-cli@11.0.9
  npm ERR!   node_modules/@angular/compiler-cli
  npm ERR!     dev @angular/compiler-cli@"~11.0.7" from the root project
  npm ERR!     peer @angular/compiler-cli@"^11.0.0" from @angular-devkit/build-angular@0.1100.7
  npm ERR!     node_modules/@angular-devkit/build-angular
  npm ERR!       dev @angular-devkit/build-angular@"^0.1100.6" from the root project
  npm ERR! 
  npm ERR! Could not resolve dependency:
  npm ERR! @angular/platform-browser-dynamic@"^11.0.7" from the root project
  npm ERR! 
  npm ERR! Conflicting peer dependency: @angular/compiler@11.2.14
  npm ERR! node_modules/@angular/compiler
  npm ERR!   peer @angular/compiler@"11.2.14" from @angular/platform-browser-dynamic@11.2.14
  npm ERR!   node_modules/@angular/platform-browser-dynamic
  npm ERR!     @angular/platform-browser-dynamic@"^11.0.7" from the root project
  npm ERR! 
  npm ERR! Fix the upstream dependency conflict, or retry
  npm ERR! this command with --force, or --legacy-peer-deps
  npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
  npm ERR! 
  npm ERR! See /home/salami/.npm/eresolve-report.txt for a full report.

  npm ERR! A complete log of this run can be found in:
  npm ERR!     /home/salami/.npm/_logs/2021-09-25T09_49_52_657Z-debug.log
```

So you can try this

```python
npm config set legacy-peer-deps true
```

```python
npm install --save --legacy-peer-deps
```
----
> how to slove ```Uncaught ReferenceError: process is not defined``` Error 

```json
Uncaught ReferenceError: process is not defined
at Object.4043 (<anonymous>:2:13168)
at r (<anonymous>:2:306599)
at Object.8048 (<anonymous>:2:9496)
at r (<anonymous>:2:306599)
at Object.8641 (<anonymous>:2:1379)
at r (<anonymous>:2:306599)
at <anonymous>:2:315627
at <anonymous>:2:324225
at <anonymous>:2:324229
at HTMLIFrameElement.e.onload (index.js:1)
```

You might have started facing this problem either after updating your CRA or starting a new project using create-react-app which lead to the probable lead cause of it to be react-error-overlay.

So try this ```npm i -D react-error-overlay@6.0.9```

----
>What the hell is this saying? ```Access to fetch at from origin 'http://localhost:3000' has been blocked by CORS policy```

I don't have a deep understanding of this but the reason to face this issue is because of making "API" requests with the same domain name.So i enable CORS in flask

``` pip install -U flask-cors ```
```python
from flask import Flask, render_template, url_for, request
from flask_cors import CORS, cross_origin
app = Flask(__name__)
cors = CORS(app)
app.config['CORS_HEADERS'] = 'Content-Type'
@app.route("/members",methods=["GET"])
@cross_origin()
def members():
    return{
        "members":[
            "Member1",
            "Member2",
            "Member3"
        ]
    }
if __name__ == "__main__":
    app.run(debug=True)
```
----
