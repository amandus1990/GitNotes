```
#!/bin/bash
while true
do
ffmpeg -re -i /home/lilala/Faded2.mp4 -vcodec copy -acodec aac -b:a 192k -f flv "rtmp://live-send.acg.tv/live/live_2200026_7995624?streamname=live_2200026_7995624&key=XXXX"
done

screen nohup sh live.sh &
```
