# ffmpeg-scripts

1. ## Tv Noise
   ```bash
   ffmpeg -f lavfi -i nullsrc=s=1280x720 -filter_complex \
"geq=random(1)*255:128:128;aevalsrc=-2+random(0)" \
-t 5 output.mkv

```

2. ## Video countdown
   ``` ffplay -f lavfi "color=s=2x2:r=1:d=10,format=gray,geq=lum=9-N,datascope=s=24x12,crop=6:12:10:0,scale=iw*30:ih*30:flags=neighbor,pad=720:480:(720-iw)/2:(480-ih)/2"```

  Learn more here https://amiaopensource.github.io/ffmpeg-artschool/
