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
if [ $c -ge 13 ]; then
l=$((l+1));c=1
if [ $l -ge 5 ]; then
break
fi
fi
sleep .1
done
````
