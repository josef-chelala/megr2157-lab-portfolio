# A5 – Design a Snap Fit

## Modeling
### Symbolically Solving for Length For Beam

### Symbolically solving for Shear of protrusion

[Found that 50% gyroid infill has an 2.2 ± 0.05 GPa Elastic Modulus from a study](https://link.springer.com/article/10.1007/s00170-020-06138-4/tables/6). I decided to use the highest possible to ensure the Beam will bend, which is about 326335 psi.

Using [the PLA data sheet given for A4](https://www.matweb.com/search/DataSheet.aspx?MatGUID=ab96a4c0655c4018a8785ac4031b9278&ckck=1), I chose its average 6555.706 psi rating for yield strength.


After writing the source for the yield strength down and posting the image of my work. I realized I had made a critical error by forgetting to divide the yield strength by the safety factor. I split the math over two days, so I must have written the yield strength down and didn't write the division by 3.5. The next day I assumed I already had done it. I am used to using MPa for yield and not psi, so I didn't notice the difference. Sadly, the model has already been printed and there is no time to go back and fix this. In real life, a serious mistake like this can cause someone harm. Later, using parametric design, I will show what the model should have been.

SolidWorks was having very strange problems with mirroring, so I was forced to make my clip an assembly
## Parametric Design and CAD
### Parameter Choices for Snap Fit
Instead of just choosing a select few parameters, I decided to add parameters for nearly everything I had used to solve for the length and shear for the beam. This was just incase if I had made any mistakes and so I could just quickly recalculate anything I needed. Ironically, I did not add the bending stress or the yield strength to the because I felt I had gone too far with the parameters I had added. 

Luckily I at least did most, meaning I could create a new model at the end

![Inserted Picture](Pictures/0.png)

The first new addition I added for the snap fit was a chamfer angle and length. The chamfer will be used to give an angle to the snap fit's protrusion to make it easier for it to slide into the block it will snap into. I decided to make these variable because my goal was to find an angle and length that would protect the sharp edge of the protrusion facing the normal force of the block by having it have about 6.5 mm behind it to make sure that it would not be destroyed. This seemed like a nice way to add a parameter, and it worked out. After adjusting several angles and lengths,  I found that a 35 degree angle and 2mm got me a close result. Instead of adjusting for exactly 3.5mm, I decided to stick with them since they were nice and even numbers. However, I found out after printing that the angle should have been steeper and closer to the tip of the beam.

![Inserted Picture](Pictures/1.png)

Next, the assignment recommended that we ought to add fillets to inner sharp edges to reduce stress concentration at those locations. Fillets can be rather tricky to work with in SolidWorks when trying to be precise, so instead of having to constantly adjust the fillet, I felt it would be another good parameter to add. My goal was to find a fillet radius that would align perfectly with the protrusions edge touching the block. The parameter ending up helping, however, I later decided that it was not a good idea to put a fillet at the protrusion since it would give a way for it to slip off the block. Also, due to the block's orientation that it would be printed, this meant that the filleted circular edge would not print a smooth surface. In the end, I decided to eyeball the other parts of the model with a fillet to see what looked nice, and I decided on a .1 inch radius.

Lastly, I also decided to turn the piece that connects the two snap ins together into a hand grip to give some leverage when having to test the part. There were several dimensions to take into consideration for this: the gap between the snap ins (including their displacements), the width of two fingers, and the thickness of the beams. To make things simple if I needed to change the gap or finger width if I wanted to change it to fit the professors hand (he wasn't there on Thursday), I turned these into parameters to create two different equations. The length of the side of the gap starting from half the thickness of the snap in to the edge of my finger width for one. The other length would be the addition of the other half thickness, plus the displacement of the snap ins, and then a variable amount of gap to give to ensure the two snap ins will not hit one another. To test, I measured two of my fingers and plugged it in, and then I chose a couple different gap sizes to how it looked. After, the hand grip variable ended up not being useful since the professor wasn't there, I did get some use out of the gap distance. I ended up decided on a 2mm gap since it gave an acceptable looking gap while also making sure there was a good enough distance to ensure they would not hit one another.

This was a wise choice, because it made giving a 


### Creating the Snap Fit in CAD
#### Creating the Cantilever Beam
To start, since the two snap fits would be mirrors of one another, only one needed to be focused on. Therefore, I began by making the cross section of the beam. To do so I simply plugged in the parameter values for the height and base of the beam into their respective dimensions.
![Inserted Picture](Pictures/1.gif)

<br>

After, I extruded the new square to the calculated length of the beam by plugging in the output variable of the deflection equation.
![Inserted Picture](Pictures/2.gif)
#### Creating the Protrusion
Next, to create the protrusion, I created a square that snapped on the edges of one side of the beam leaving one open to change. I created a dimension for it and plugged in the parameter of the protrusion length I decided on.
![Inserted Picture](Pictures/3.gif)

<br>

Then I extruded it out with the parameter equal to the height of the protrusion (also the deflection value).
![Inserted Picture](Pictures/4.gif)

<br>

Next, I created a chamfer at the outer edge of it and then typed in the variable parameter I had created for the angle and length of the chamfer (the below is a recreation which is why it has the dimesnions I had landed on).

![Inserted Picture](Pictures/5.gif)

#### Adding the Leverage
To add the finger leverage, I created a sketch on the "wall" side of the beam and created a centerline connecting both centers of the bases. Then I create two squares that aligned with the centerline and the base edges on opposing sides. I did this so that the entire slip fit would lay completely flat on the printing bed. Lastly, I added the the parameter length equations I created to their respective rectangle. 
![Inserted Picture](Pictures/6.gif)

<br>

Lastly, I extruded it out to a support thickness parameter I later created to make edits. It was originally set to the thickness I originally wanted (3/10 of an inch), and I ended up sticking to it so the parameter was unnecessary.

![Inserted Picture](Pictures/7.gif)

#### Filleting the Interior Edges
After selecting the chamfer tool, I selected every single interior edge on of the snap fit. Then I set the radius equal to the parameter I had created for it. Keep in mind that after creating the block, I came back here and deleted the fillet of the protrusion.
![Inserted Picture](Pictures/9.gif)

#### "Mirroring" the Snap Fit
After having to manipulate the chamfer several times, it seems to glitch out my file and create a "phantom" chamfer. After trying to mirror the half of my snap fit to make it whole, I constantly kept having errors saying a chamfer was causing issues. After an hour of testing, I realized it was the ghost chamfer and that the only way to fix it was to recreate the part. To not have to waste time doing that, I decided to just make an assembly to workaround and create my own "mirror". Since the snap fit was symmetrical along the axis I needed, all I did was create an assembly and mate the two snap fits halves at the gaps center.

![Inserted Picture](Pictures/8.gif)








mistake 
