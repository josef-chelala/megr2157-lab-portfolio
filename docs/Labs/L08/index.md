# Lab 8 - Design and Print Something Useful

## Why Asking Smart Questions Matter


## Problem Statement


## Design 
### Approach
Due to a lack of time, the approach to design the chains was to overengineer them to do little to no math. While the attachment to the pen would be more precise due to trying to minimize the size of the attachment (which due to the overengineering of the chains made it larger than I had hoped). 
### An Individual Chain
#### Choosing the General Dimensions of individual Chain
The dimension that will most affect the rest of the project is the thickness of a chain. Since this will be connected to the laptop that goes into my backpack, I had to take into consideration the backpack slamming the ground with a ton of books in it. Therefore, I needed the chain to be thick enough to possibly take a large impact while not too large enough to be obscenely big. Using my caliper, I decided on a 8.5 mm thickness. This will be a print in place chain, so I also need to take into account gaps between each chain via their thickness and that they so do not interact with one another. Also, the pair of "male" chains connecting to the one "female" chain (all act as both) need to have as little interaction inside of the female, to ensure they are easily able to move around. To ensure that two chains in a row do not infuse with one another, I set a hardline distance of 1.2mm on each gap from one another. I was unsure how big to make the gap between the two male chains, so I decided to chose 4mm base on observations of the finished chain and I would adjust it later if it would not work (luckily, this worked on the first try). Lastly, I needed to decide on an angle at which each chain will interlock with one another. To reduce any and all necessary adjustments or the like, I decided that a 45 degree angle would be perfect to keep things symmetrical. Additional, putting it at a 45 degree angle would greatly reduce the amount of support needed.

#### Creating the Equations
The equations were easy to make. Since a pair of chains on the width side of the female chain (male and female connection) will basically create 3 layers of thickness with the additional 1.2mm gap on each side. The parameter equation simply needs to be 3 times the thickness plus 2 time 1.2mm. When looking along the length, there will be two male chains and one female that connects them. So each male has one of their thicknesses inside the female, and to ensure they do not fall out the female needs two thicknesses as well. Additionally, there is the variable gap between males. So the equation for the length of a chain must be 4 times the thickness plus the gap (which I chose to be 4mm). Lastly, I also created an angle variable, however, it was later unnecessary since a 45 degree angle would work in nearly all cased.
<img width="1023" height="385" alt="image" src="https://github.com/user-attachments/assets/c0b68146-1f3a-4906-bf92-ae3b67b92268" />

#### Creating the Base of an Individual Chain
##### Sketch
To do so, I simply created two concentric rectangles. For the larger rectangle, I set its sides to the length and width equations. Then, since I incorporated the desired gap at the center with-in the earlier equations, I simply had the internal rectangle have each of its sides a thickness length away from the external rectangle's equivalent sides.
<img width="1617" height="1171" alt="image" src="https://github.com/user-attachments/assets/8aa29cb3-fac4-4cb3-9954-c425cf08bbce" />
##### Extrusion
The extrusion was simple, I simply had to extrude it by my chosen thickness.
<img width="1471" height="1183" alt="image" src="https://github.com/user-attachments/assets/bae16732-e46f-4aa8-a00b-6006e1029597" />

#### Cutting Flat Side for Print Bed
##### Sketch
Since the chains will be put at an angle, I am required to cut one corner to create a flat side for the chain to rest on that would allow the chain to generally print at 90 degrees. Furthermore, due to how the chains connected to one another, I had to pick a corner of one of the lengths. To do so, I simply created a triangle at a corner with variable sides except I chose the hypotenuse to be locked at 6mm. I chose 6 mm so that each chain would have a good amount of surface area with the print bed. Next, I simply angled the hypotenuse in a way that that would allow the chain to be angled at 45 degrees from the print bed.
<img width="1291" height="963" alt="image" src="https://github.com/user-attachments/assets/d0eebde5-2a74-42d6-b8f6-3088e0797fb0" />
##### Cut Extrusion
To finish this, I simply cut all the way to the other side of the chain
<img width="1537" height="793" alt="image" src="https://github.com/user-attachments/assets/e2760a09-d03d-4d3d-a4b2-78cb03d6c967" />
#### Giving Curvature
The last edit to the chain was to give it curavture on all the sharp edges. This will allow the chains to move around more freely instead of allowing diagonal corners (that exceed 8.5 mm) that can get stuck inside a female chain and limit movement. To this, I filleted all sharp edges. To allow a little bit of a flat side at each side to make assembly easier, I used 4mm radius fillets instead of 4.25 mm (half the thicknness).
<img width="1371" height="931" alt="image" src="https://github.com/user-attachments/assets/03aed8cc-fcaf-4f80-b34d-da458aadab03" />
#### Adding Planes
Lastly, I added 3 perpendicular planes along the center of the length of the chain. This will allow the chains to align with one another.
<img width="1539" height="1167" alt="image" src="https://github.com/user-attachments/assets/ae050c04-30ff-415d-89c9-16d5e9ad3938" />


### Creating the Chain
To create the chain, I simply started with an assembly of two chains
<img width="1027" height="915" alt="image" src="https://github.com/user-attachments/assets/eaf5f7e6-08aa-45ee-b272-bf932d4ebf48" />
#### Aligning the Flat Bed Side
To start, I simply aligned the two flat sides that will lay on the bed.
<img width="1614" height="923" alt="1" src="https://github.com/user-attachments/assets/d178afbd-8a46-4703-8533-dba02ef85af8" />
#### Mind the Gap and Orentation
Next, I distance mated the center plane of one link with one of the smaller, outer flat sides of the other link. This will make them parallel with one another with a distance of .6mm. The reason for .6mm is that when an additional chain is added, that will also be given a .6mm gap but on the other side of the plane. Added up, this will leave the desired gap of 1.2mm I wanted between the male chains. Additionally, I flipped the orientation of the chain so that it creates an x shape. This will allow the chain to be printed in place since they will not be touching one another.
![Inserted Picture](Too_Big/2.gif)








## 3D Print

## Lessons Learned

