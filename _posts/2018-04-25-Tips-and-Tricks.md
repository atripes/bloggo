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


## Syncronize a directory via rsync
`rsync --dry-run -P -a -z -e ssh --delete --exclude=node_modules --exclude=.git ./local_dir user@remote.server.com:~/dir`

```
--dry-run #remove when certain of command 
-P #prints progress information
-a #works like -r (recursive) with added benefits
-z #uses compression algo for transfer
-e #login shell ssh (use rsync over ssh connection)
--delete #also sync deletion of files
--exclude #exludes files or dirs
```

## Unattended linux install using preseed file
Fuck, this will be a standalone post at some point. Nah, wait, it's so easy:
`git clone https://github.com/core-process/linux-unattended-installation.git` and then follow the readme. Only works on Linux hosts.

## Compress mp4 via ffmpeg
This compresses the input by a factor of ~12:
`ffmpeg -i ds_orig.mp4 -c:v libx264 -c:a copy -crf 28 -preset veryfast x264_crf28.mp4`

## Disable mouse acceleration in OSX (High Sierra)
`defaults read .GlobalPreferences com.apple.mouse.scaling` to read the value.
`defaults write .GlobalPreferences com.apple.mouse.scaling -1` to disable it. Login again for changes being applied.
Create a task with Automator (shellscript) and paste the write portion to it. Add it as a login item in `system-preferences -> user and groups`

## Certbot (letsencrypt) for multiple domains
`certbot --nginx -d domain1 -d domain2 -d domain3`.



Don't forget about archive.org if the links are broken.
