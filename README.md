### first [show all shape of cowsay command]:
````shell
temp='apt                elephant           luke-koala         stimpy           
bud-frogs          elephant-in-snake  mech-and-cow       suse             
bunny              eyes               milk               three-eyes       
calvin             flaming-sheep      moofasa            turkey           
cheese             fox                moose              turtle           
cock               ghostbusters       pony               tux              
cower              gnu                pony-smaller       unipony          
daemon             hellokitty         ren                unipony-smaller  
default            kangaroo           sheep              vader            
dragon             kiss               skeleton           vader-koala      
dragon-and-cow     koala              snowman            www              
duck               kosh               stegosaurus'

c=1;l=1; while true; do
cowsay -f `echo $temp | awk '{print $'"$l}" | sed -n "${c}p"` 'Hello!!'
c=$((c + 1))
if [ $c -ge 12 ]; then
l=$((l+1));c=1
if [ $l -ge 5 ]; then
break
fi
fi
sleep .1
done
````

### 2 - [create draft image for fill hole in web desine]
````
#!/bin/zsh

width=$1
height=$2
avg=$(((width + height) / 80 ))

convert -size ${width}x${height} xc: +noise Random -quality 80 output.jpg

convert output.jpg -fill xc:white -draw "rectangle $avg,$avg $((width - avg)),$((height - avg))" output.jpg

convert output.jpg -gravity center -bordercolor yellow -border $((avg/4)) -pointsize $((width/10)) -annotate +0+0 "${width}x${height}" output.jpg

````

1- example: (path of file) 500 500 (this create a draft image with size 500x500 px)


