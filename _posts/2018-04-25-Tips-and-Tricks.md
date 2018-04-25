---
layout: post
title: Tips and Trips
description: This... you will love.
permalink: :title
---

## Serve a file in a network
You can use socket on pure Linux machines:
`tar -cvz .folder-to-serve | socket -sqw <port>` on the server and
`socket -q <server-ip>:<port> | tar -xvz` on the client and voila enjoy your file.

You have to use other measures when OSX is in play, because Apple. Use npms `http-server`!
`npm install -g http-server` and then 
`cd <DIR TO SERVE> && http-server` That's it. now you can `wget <server-ip>/file` and feel like a free man.

## Use pipenv instead of pip
(https://docs.pipenv.org/)


## Unattended linux install using preseed file
Fuck, this will be a standalone post at some point. Nah, wait, it's so easy:
`git clone https://github.com/core-process/linux-unattended-installation.git` and then follow the readme. Only works on Linux hosts.


This will be constantly updated.

Keep on rocking in the free world, and doo doo deloo doo ...

Don't forget about archive.org if the links are broken.
