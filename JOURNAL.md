# 04/03/2026 11:30 p.m. : Initial Research

Why am I making this toolhead? Well I need more funds for my blueprint designed abomination. Currently, the "best" non-CPAP bedslinger toolhead is the LH Stinger toolhead from what I've seen. Unfortunately, it's so good and well-thought that there aren't really many alternatives I can look at in terms of performance. So I guess my best course of action would be to design a toolhead, any toolhead, as well-thought out as I can make it in the few days I have and then iterate once I get the fans and can actually test ducts and all.   
Spent like an hour doing research throughout various Discords and in hopes of finding some more unique (but not completely stupid) fan options. I really like how the Trinity toolhead looks with the 3628 fans. So much so that I even slapped in on my WIP design to see how it'd look:
![image](/pics/trinity.png)
Yeah it's ridiculous...I'd lose ton of Z space, even though I could adapt the motor mounts so that I wouldn't lose that much X. Plus the 3628s are simply overkill, especially since I can just add sheet cooling like the stinger pretty easily as it's a bedslinger. The other fan option I found would be 5020s, which are like 5mm wider than the 5015s, and that seemed like an interesting option, but it turns out that it'd just be better to get some good 5015s, like the Berseker Vindrs for example. The 5020s don't have that much more CFM, the options are more limited, and thus the RPM options are as well. With 5015s on the other hand they go up to like 9500 RPM I think. RPM, as I just learned, matters because if you can't ramp them up and down you might find yourself over-cooling stuff at low speed, which might result in bridges for example curling up from thermal shock. According to PureComedi on the LH Stinger Discord this shouldn't be an issue if I don't print slower than 100 mm/s, so yeah CFM is mainly what I'm looking at. Anyways, seems I can worry about the exact specs of the 5015s after I finish designing a rough draft. Honestly using 5015s would also be good because if my toolhead doesn't work that great and I don't have time to work on it anymore once I've built v1 (because of exams) I can just print a Stinger toolhead and use that until I get around to it. 

So, design constraints. I'll need to use the LH Stinger belt block or something similar, as I can't tension the belts in any other place because of AWD X. I'll be using a Dragon Ace Volcano as my hotend, which I'll be getting from my own money, as I obviously can't fit that into this $75 budget. My toolhead obviously can't be direct clone of the Stinger or any other design, but I do want it to have like at least 6-70% of the performance (in CFD at least) that the former does. I'll probably be using a sherpa mini or a protoxtruder 2.0, gotta decide at some point. I want to try and have a decent COM. COM matters because the higher the accel/speed the higher the torque on the toolhead, and if the COM isn't as close to the rail block as possible it can wear out the rail pretty fast and also mess up the print from what I understand. I'll be using SimScale for the CFD, even though someone on the Monolith Discord suggested OpenFoam, as the former seems to be the most beginner friendly and TeachingTech and NeeditMakeit have tutorials on it over on Youtube. Oh and obviously I'll try to make the toolhead as rigid and light as possible. Rigidity is evidently the priority though, and I also have 48v AWD X, so weight shouldn't matter as much as it might on other setups. 

Ducts. Rewatched James Pray's video (colphaer on the Ice Cream Factory Discord) on duct design. I actually have a journal entry regarding toolhead and ducts in my blueprint project, but yeah forgot everything in one month. The Golden Rule of duct design according to him is to narrow your ducts gradually. Don't narrow a duct by more than 11 degrees measured from wall to wall. Secondly, if you are going for cooling, the goal is to get fast airflow out the end. You can get fast cooling by narrowing the outlet, but after a certain tipping point it starts to choke the airflow. You need to find outlet_area/input_area x 100 which equals the final reduction percentage. Unfortunately, this can only be tested empirically, which in my case is kind of impossible as I do not have the fans to test them yet. So I'll just use the outlet area dimensions of the Stinger as placeholder values and then adjust them once I actually get the toolhead. Though if I go for more of a Archetype Mjolnir setup, with the fans oriented like almost horizontal relative to the gantry then I don't think it'd matter *that* much.   Another tip listed in the video is to try and set your start and end constraints (outlet/input area) and then try and join them in the middle. Don't think that'll matter as much in my case but yeah. Ducts should obviously be as smooth as possible, with as big curves as possible.    

Spent like 40m trying to find an accurate Dragon Ace Volcano CAD model. In the end I took the main body from the UAP toolhead CAD and the sock from the Trinity CAD. The sock is obviously just a rough estimate that the creator of Trinity used, but it's the best thing I've found so it'll have to do. I also assigned some colors to it so that it'd look closer to the original. I'll have to assign the materials (so I get the proper mass for calculating the COM) tomorrow.

![image](/pics/dragon_ace_volc)

Anyway moving on to other orders of business, I'll be using the Protoxtruder 2.0. So I accidentally discovered that Kevin (the one and only, creator of KevEnder) also uses the Protoxtruder for his toolheads. Talked with him a bit, and he gave me an onshape link to a version with all the mass stuff assigned, which is amazing, as I dreaded assigning materials for each of the gears, collet, motor, etc. I didn't even have a version with the gears. Anyway he said that the stock bearings for both the HGX and the HGX 2.0 are shit, and that they'll wear down in a month and have horrible backlash afterwards. He said he swapped the bearings for larger bearing and has been running it with no issues for the past year or so, 683 instead of mr63. The Onshape link he gave me was his modified version of the Protoxtruder which uses said bearings and also has a third bolt in the back which according to him increases rigidity by a lot. So I'll be using his version...will have to see from where to source the bearings. 
Did a little work on the basic toolhead cage. Referenced both the Stinger and Trinity toolhead (the latter as it's made for the Dragon Ace Volcano). 
![image](/pics/rough_draft.png) 
![image](/pics/rough_draft2.png)

**Total Time Spent: 6h**





# 05/03/2025 **12:48 a.m. : First Rough CAD Design 
![img](/pics/dragon_mass.png)
Spent some time assigning materials to the Dragon Ace and the fans. Speaking of the fans, I think I'll go with a 2510 axial for cooling the heatsink. Stinger uses a 4010 axial, and there's also others that use a 3010, but both the UAP and the Trinity use the 2510, and as the Trinity use the Dragon Ace Volcano as well and is considered one of the best monolith toolheads I think I'll be fine. Plus it's more compact. For the hotend, I just referenced the diagram they have on their website and assigned the most similar materials I could find in Onshape's material library, and for the fans I just set them as Nylon. Printed parts will be assigned as PC/ABS. I was worried a few days ago that I'd have to find a perfect weight/mass for each part and then custom assign that in the CAD, but after seeing how Kevin assigned his I realized that I'm overcomplicating things...the COM is just an estimate after all. I still have to assign the materials for the Stinger tensioner block, but I'll do that later as I think I might have to modify that. I also have set a rough position for the fans. I think in the end this will end up as basically a Mjolnir inspired simpler/better core bedlsinger toolhead.  
![img](/pics/rough_fan_pos.png) 

Did some more CAD work and here's how it's looking right now. 
![img](pics/pic1.png)
![img](pics/pic3.png)
I messed around with the chamfers and like did partial chamfers of different dimensions, and in my opinion it's looking pretty good.

The two main problems I ran into today were accidentally forgetting that the fans have to be above the nozzle (I know, I'm stupid, but in my defense it's 12 am), which you can see in the above pics and was relatively easy to fix (though tedious) and more importantly the 2510 screw holes. Now the problem is that with how I'm planning to mount the like 5015 fan "wings" to the core I'm reusing the screws of the axial fan, but I don't have the space to fasten it in the back, as the potential heat insert/hex would interfere with the heat sink. While I have solved the former problem I cannot at the moment think of a good way to solve the latter. I'll have another go at it tomorrow.

![img](pics/pic6.png)
![img](pics/pic7.png)

**Total Time Spent: 5h**

# 10/03/2025
It's getting kind of hard to journal now, as most of the time is wasted on small CAD stuff (eg. an error here, go back and fix it, rethink X feature so it's "cleaner", etc). Anyways, after experimenting some more with a 3010 I've decided to go with a 2510 after all, as I think I can manage mounting it. So here's what I currently have, after several more hours.
![img](pics/pic11.png)
![img](pics/pic12.png)
![img](pics/pic13.png)
![img](pics/pic14.png)
![img](pics/pic15.png)
