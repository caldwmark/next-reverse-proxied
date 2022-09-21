# next-reverse-proxied

my boilerplate for a quick and easy docker container with ssl and cache

## features

- [ssl-proxy](https://github.com/suyashkumar/ssl-proxy) - for taking the headaches out of certbot 
- [nginx](https://nginx.org/) - for caching the apps responses !speed! !speed! !speed!
- [node](https://nodejs.org/) - this example uses a [next.js](https://nextjs.org/) app. it could be any framework

## usage

clone this repo into your projects short name.  in this example I use bcp as my short name<br /> 
`git clone https://github.com/caldwmark/next-reverse-proxied.git bcp`

move into the empty app folder and clone or copy your project into it. Be sure to replace bcp with your own project short name. <br />
`cd  bcp/next/app`<br /> 
`git clone <my blog code> .`

### containers

the idea here is ssl-proxy answers the call on port 443.  it handles the certificates and ssl then passes the requests to nginx.

nginx here is acting as a reverse caching proxy.  It catches the request on and looks for it in cache and fetches it from the next app if it's not cached

<div text-align="center">browser requests => ssl-proxy => nginx => next</div> 

#### nginx

rename the bearcountry.conf to something more appropriate for your site.  this is the server section of the nginx.conf  edit it to your unique needs.  

check the nginx.conf also.  edit it if needed.

#### next

next could be python, or whatever...  if you rename the next container name in docker-config.yml.  make sure to also catch the proxy pass redirect in the yoursite.conf of nginx to reflect the new name:port

#### ssl-proxy

[ssl-proxy](https://github.com/suyashkumar/ssl-proxy) is a binany generated from go code.  it's a handy little tool for handling ssl.  more info on it's usage can be found on [its github page](https://github.com/suyashkumar/ssl-proxy).

## startup

once you are satisfied with your settings, you can start it by going back into the project folder.  the one holding docker-compose.yml and entering the following command<br />
`docker compose up -d --build`

to see if they all started
`docker ps`
should show the three containers

view the logs
`docker compose logs`




