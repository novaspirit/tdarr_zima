# tdarr_zima
list of commands used in the tdarr video
https://www.youtube.com/watch?v=WczGt7Wk9to

install docker as you see fit, if your are using casa os you can skip this step since docker is already pre-installed

```sudo install docker```

depending on your intel gpu you will need either one of these

```sudo apt install intel-media-va-driver```

this would be for zima hd500 igpu

```sudo apt install i965-va-driver```


to test if hardware decoding is working (optional)

```vlc --ffmpeg-hw -v```


```
sudo apt install intel-gpu-tools
intel_gpu_tools
```

docker command I used in video for tdarr
```
docker run -d -v /portainer/Files/Appdata/tdarr/server:/app/server -v /portainer/Files/Appdata/tdarr/configs:/app/configs -v /portainer/Files/Appdata/tdarr/logs:/app/logs -v /media:/media -v /transcode_cache:/temp -e "serverIP=0.0.0.0" -e "serverPort=8266" -e "webUIPort=8265" -e "internalNode=true" -e "nodeID=MyInternalNode" --network bridge -p 8265:8265 -p 8266:8266 -e "TZ=Europe/London" -e PUID=1000 -e PGID=1000 --device=/dev/dri:/dev/dri --log-opt max-size=10m --log-opt max-file=5 --name=tdarr ghcr.io/haveagitgat/tdarr
```
