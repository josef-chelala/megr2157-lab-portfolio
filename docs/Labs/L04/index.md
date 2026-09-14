# Lab 4 – Benchmark a Parameter
## Objective
The objective for this lab is to create our own benchmark artifact to test one of the labs 3D. We were recommended to test overhang angles, tolerances, and dimension calibration.

## Parameter 
### Choice of Parameter
When I first started the project, I initially wanted to combine the tolerance and overhand test to see how the different angles of overhang would affect the tolerances of the print. However, after discussing this with the professor, I realized it would likely take a decent amount of measuring with this combo. To make things simpler, I decided to chose the tolerance test to make measurements easy using a caliper. Specifically, I decided to test the dimensional tolerances of a Prusa 3D printer.

### Inspiration 
After being inspired from [this tolerance test I found online](https://www.printables.com/model/1114097-cylinder-tolerance-passthrough), I wondered if I could invert this idea to test the tolerance of a single hole among several poles. With additional help from my Professor to further develop the idea, I decided to commit to it. 

### Tolerance Dimension Ideas
When I was looking through printables.com, I saw that people were using a different range of numbers for the tolerance test in millimeters. The one that inspired me in particular went up to .4mm. The millimeter part made sense to me, given 3D printers operate in mm, however, I was not sure on what tolerance numbers I should use. Then I stumbled upon [this article](https://3dput.com/complete-guide-to-3d-printing-tolerances-and-fit-getting-perfect-clearance-for-moving-parts/#complete-guide-to-3d-printing-tolerances-and-fit-getting-per) that stated that depending on the quality of the printer, tolerances usually range from about ±1mm to ±5mm. So I set out to make a 3D model based on testing those numbers. I decided on testing a 10mm diameter to have simple numbers to work with. Luckily, 10 mm ended up being a great decision because while I was in the middle of making the model, I remembered that the professor showed us the "Design Rules for 3D Printing" guide and tolerance was mentioned there. To double check my work, I looked back on it and noticed that this paper used a ±.3% tolerance percentage instead of a numbered range. As will be explained in the scaling section below, the percentage based vs fixed tolerance range are used depending on the print or can even be used at the same time. With this realization, choosing 10mm was the perfect choice since it gave a ±.3mm range so I did not have to completely change my work. I decided that I would keep the ±.4mm and ±.5mm section for a worst case scenario, but I would delete them if it made the print job way too long.

### Guessing
This is before I researched how build parameters affect tolerances. .5 and -.5 are extremes, I am positive it will not match at 0. My guess is that on the side that was printed on the bed, the material will be expanded toward the center of the cylinders axis since the filaments on first layers usually pancakes out, causing a +.1 to +.2 mm increase in diameter. On the top side, I believe the material will contract after the filament cools, so the top side might decrease by -.1 to -.2 mm in diameter. Lastly, I believe that each pole will also contract due to cooling, so again I expect those to decrease by -.1 to -.2 mm in diameter. Possibly resulting in the side printed on the bed ending up fitting unto one of the poles ranging in ±.1mm, and the opposing side having to be fit unto the poles ranging from -.1mm to -.4mm, though I second guess it reaching -.4mm.


## Design Process
### Sketch Idea
To start, I quickly wrote down a rough idea on how I wanted to make my test using my inverted idea. Based on my originally found ±.5mm tolerance difference, I wanted make each hole in intervals of .1mm from  -.5mm to +.5mm. It is better to do .05mm intervals (as will be shown in the results), however I felt at the time it would not make a big difference, so to decrease the print time, I stuck with .1mm intervals. Since the base diameter being tested is 10mm, I decided to make the hollow cylinders outer diameter double its inner to guarantee the thickness between the diameters would not affect the inner diameters tolerance. I decided to make two rows of the poles with tolerance changes instead of one to decrease the length of the part. Since the "exact" size pole left an odd number of poles, I decided to put it in-between the rows at an outer edge for better aesthetics. Due to giving the hollow cylinder a 20mm outer diameter, I decided to make sure that each poles center were 20mm away from each other to give enough clearance for when I need to test.
![Inserted Picture](Pictures/rough_sketch.png)

### Hollow Cylinder
#### Starting Sketch
The sketch of the hollow cylinder was incredibly simple, it was simply two concentric circles with the 10mm and 20mm diameters that I had chosen.
![Inserted Picture](Pictures/1.png)
#### Extrusion
Next, was deciding on the dimension of the extrusion. Earlier, I did not plan an extrusion distance so that I could decide on it based on how long the part would print. So I decided on a 10mm thickness as a placeholder. Later, I found that the print time using this thickness value was under the requires, and since 10mm is more than enough to give an accurate reading for the tolerance test based on others I had seen, I decide to not make any changes and leave it at 10mm.
![Inserted Picture](Pictures/2.png)

### The Tension Test
#### Starting Sketch
Instead of starting with the base, I decided to start with the poles so that I could base the base on the poles and not the other way around. I started with the positive tolerance row, placing once circle at a time, changing its diameter to its respective tolerance, and making sure they were all horizontally aligned with the horizontal axis of the plane with a 20mm center to center distance from one another. Then I did the same thing with the negative tolerance row, except I aligned them vertically with their respective positive tolerance partner. Since they where all horizontally aligned, I only had to make one of the tolerance partners have a 20mm gap between the two. Lastly I added the exact sized diameter pole next to the -.1mm and +.1mm poles. In order to make it, I simply created an equilateral triangle of 20mm, and set the last pole at the tip of it. Keep in mind that since I chose center to center distances, that outer diameters of each pole will not have exactly 10mm gaps between them. The reason I chose 20mm was to take this into account. 
![Inserted Picture](Pictures/3.png)
![Inserted Picture](Pictures/4.png)
#### Pole Extrusion
I decided to make the pole extrusion thickness the same as the hollow cylinder to possibly keep it flush when I tested it. Again, the 10mm was a place holder, but I kept it since it fit within the print time requirement
![Inserted Picture](Pictures/5.png)

#### Base Sketch
To make the sketch of the base, I chose one side of one of the poles to use as the plane for my sketch. Then, I made a rectangle that enclosed all the poles. Since the outer diameter of the hollow cylinder was 20mm, that meant that it would at a minimum stick out 5mm in all directions from the poles. To make sure that the hollow cylinder did not stick out over the edge of the base, I decided to take the 10.5mm pole, and made sure the rectangles sides next to it was 6mm way from it.  
![Inserted Picture](Pictures/6.png)
Then I moved over to the exact diameter pole. I made the center of the rectangles height be horizontal to the center of the exact pole so that the base was symmetrical along center horizontal axis on the averages of all the poles centers.
![Inserted Picture](Pictures/7.png)
Then I used a 6mm gap from the outer diameter of the exact pole from the last unaffected side to again make sure the tested piece wouldn't hang over the base. 
![Inserted Picture](Pictures/8.png)

#### Base Extrusion
Then I extruded it by 10mm for the same reasons as the other extrusions.
![Inserted Picture](Pictures/9.png)

#### Edits to the Base
When I finished the base, I did not like how the sides were rectangular and it added unnecessary time to the print job. So I decided to make the corners rounded. Instead of using fillets, I decided to simply start with a circle starting at the center of the 10.5mm pole and made a circle that touched one of the sides. This circle would then have its perimeter 6mm away from the poles perimeter in every direction, making sure the test cylinder would not hover over the edge. Then I connected the parts of the circle that were touching the rectangles edges, and deleted the rest of the circle. For symmetry I did the same thing but with the same sized circle for the 9.5mm pole. 
![Inserted Picture](Pictures/10.png)
Then for the exact pole, I made 3 circles at the exact, 10.1mm, and 9.9mm poles and attached their respective circles to the closest edge of the rectangle they were next to. Then I made two lines connected to the newly created circles, one from the 10.1mm pole to the exact pole and one from the 9.9mm pole to the exact pole. I forced these lines to be tangent between their respective pairs to create a nice transition from the circular edges to the straight edges. 
![Inserted Picture](Pictures/11.png)
Then I connected the parts of the 10.1mm and 9.9mm poles' circles by following the edge of the part of the rectangle I wanted to cut. However, I had to create lines that went off the path of the left side of the rectangle. This is because this would not make a successful sketch that can be extruded where the edge connects to the exact pole's circle. This gave me the final sketch to cut with.
![Inserted Picture](Pictures/12.png)
Then I simply cut all the way through to give me this final shape
![Inserted Picture](Pictures/forgot.png)

#### Adding the Tolerances for Each Pole
To indicate each poles tolerance, I engraved their tolerance number under each pole. To start, I made construction lines that were parallel to the top edges of the base and had their sides of the line aligned with their respective poles sides (from that perspective) to make sure that the text would align with its center correctly. Then I made a bolded 0 text on the line as a reference on how to make the constructive lines be a set distance away from the bottom edge of the base, so that the center of each text was roughly at the center of the horizontal parts of the base.
![Inserted Picture](Pictures/13.png)
Then I inserted each poles respective tolerance as text at their respective construction line. I made sure the text was centrally aligned, bolded, and at 13 size font (I have learned in the past 10 sized font as the minimum is the rule of thumb, though very situational). This gave a higher chance of the text coming out well.
![Inserted Picture](Pictures/14.png)
I realized that parts of the text that were on curved edges would not cut extrude well, so I used the wrap feature with the cut setting so that it would cut evenly into the base at all parts of the sketch.
![Inserted Picture](Pictures/15.png)
![Inserted Picture](Pictures/16.png)
Finally so that the back of the base wasn't empty, I simply added my name to fill it out. With the total result below.
![Inserted Picture](Pictures/17.png)
![Inserted Picture](Pictures/18.png)

## Inserting the Finished Models into PrusaSlicer
Over the years I have off and on used 3D printers, I learned that STL and sometimes OBJ files from some CAD software are not good for highly advanced models or models with a lot of curves and just flat out circles. To reduce the size of the file, they simply create low resolution STL files, which results in curves turning into several flat edges. This is terrible when trying to do this sort of tolerance tests with cylinders, since they require high details in order to be accurate. 
![Inserted Picture](Pictures/stl.png)
There are ways usually to increase the resolution of STL files exported by CAD software, but it can be rather unnecessarily cumbersome or confusing on the software. For SolidWorks I have to go through several settings. Even then, there still might be micro edges. To by pass all this work, I could just use a STEP file (the closet to a universal CAD file), which basically keeps everything in the model the exact same as how I made it with absolutely no strange edges. Luckily, PrusaSlicer allows directly importing STEP files, so I did it. So I simply exported my model as a step file.
![Inserted Picture](Pictures/19.png)

Then I dragged and dropped the STEP into PrusaSlicer which opened up a menu. What is great about the program is that it allows you to select just how highly detailed you want the file to be imported. Since this is a relatively simple model, I decided to select the custom selection, and bumped up the quality to the max. 
![Inserted Picture](Pictures/20.png)

As you can easily tell, it came out nearly like it was in SolidWorks. It still creates straight edges, however, they are at .25 degree intervals, meaning the 3D printer itself will likely be the limit on how curved something can get since the poles are only 10mm in diameter.
![Inserted Picture](Pictures/step.png)

## The Affect and My Choices of Build Parameters
Tolerance is not just based how accurate the printers motors or mechanism are able to move the hothead, it is also dependent on the other factors such as build parameters. [[[NOTE: I decided to combine the "Decide" section of the "Document Design" part with the "Preproccess" part since they directly influenced each other]]]

### Infill
While researching how infill patterns affect tolerances, I noticed that patterns affected different kinds of shapes differently. However, I found this study that stated that the[ Gyroid patterns have the least tolerance percentage for cylindrical shapes](https://journals.sagepub.com/doi/abs/10.1177/09544089241312637). Therefore I decided to use Gyroid pattern. 

<br>

Infill percentage parameters seem to be hard to pin down on how exactly it affects tolerance. After skimming through some studies on the subject, it seems that there is a variation in results of various infill percentages. One study might say an increase in infill increases tolerance, while another might say the opposite. [Then I stumbled upon this study](https://www.researchgate.net/publication/403402693_Influence_of_Infill_Density_on_Dimensional_and_Geometrical_Deviations_of_PLA_Parts_Fabricated_by_FDM) that states that while it seems infill percentage affects tolerances, it is situationally affected, specifically stating that "that infill density has selective and direction-dependent effects on geometric accuracy, without indicating a general trend applicable to all types of deviations." Uncertain what percentage infill to use, I decided to base the percentage on what is used for benchy which [is about 10 to 15%](https://www.3dmakerengineering.com/blogs/3d-printing/the-power-of-the-3d-benchy). I decided on 15% to give the structure a little more strength.

### Build Orientation and Supports
The affect that build orientation and supports have on tolerances is significantly clearer then infill. Since 3D printers work in layers that give little steps when there are more rapid angle increases, so the way you orientate cylindrical models has a massive impact on its dimensional tolerance (although in a different fashion) of its circular surfaces. For example, if one were to try to print a tiny rod by making its rounded sides touch the bed plate, then the curved surfaces will have tiny steps for each angle change and will require supports to make sure the print doesn't fail. Plus, since the supports need to be in contact with the object itself, this further warps the surface of the cylinder This clearly changes the dimensional geometry of the object. Although, supports can also help give better tolerances depending on the situation. The example I gave is an extreme in how support can affect tolerances vs the better orientation. However, in many situations, some parts of a model are required to have overhangs in order to be printed. In such cases, the supports might slightly affect tolerances, however no support may affect tolerances significantly more or the print will just fail. For that reason I need to make sure that the cylinders I am using for testing are vertical and to lay the part on its flat side so that no supports were needed.
![Inserted Picture](Pictures/21.gif)

### Scale
Scale also affect tolerances. Interestingly, I discovered that my original choice of ±5mm was not necessarily wrong and that percentage based tolerance could actually be wrong instead. What I found is that the size of the dimension is directly responsible between the choice of the two. [This article](https://www.syntax3dlab.com/blog/tolerances-clearances-guide) states that you actually chose between fixed vs percentage based tolerance estimates depending on which gives a worse tolerance range. What this means is that small dimensioned parts or a part's features will be using the fixed dimension range vs large dimensions will be using the percentage based. Relating this to specifically my test, the percentage based tolerance gave me ±.3mm for a 10mm diameter vs the article's ±.5mm. So does that mean I should chose ±.5mm because of this? Well, something to keep in mind is that the fixed and percentage dimension ranges depends on other factors such the material being used, the quality of the printer, the type of additive manufacturing being used and so fourth. PLA has decent tolerances, and Prusa printers are very high quality, so it may not be a bad idea to use ±.3mm poles instead. However, I decided to just stick with the ±.5mm tolerance because I found the print time was 15 minutes below the time requirement and that most people were done printing by the time I went to start mine. Lastly, because I was careful with my dimensions in CAD, I had no reason to actually scale the part.

### Result
After setting my chosen orientation as well as the infill pattern and pattern type. Then disabling supports and setting the print job to  .2mm SPEED mode. I found that the print time would be 44 minutes long. However, I forgot to screen shot this part, so below is a close setup of what I originally had. Except, for some strange reason this shows 50 minutes and I could not really fidn a reason why.
![Inserted Picture](Pictures/22.png)


## Printing the Artifact
After running the Slicer, I exported the g-code to a USB and attached it to the PC_1 table to print. Later in the print job, I greatly regretted choosing this printer because it set on a very wobbly table with another printer. From my understanding, a single printer can handle a bit of wobbling by itself do to how they are set up and the wobbly motions of the table can MAYBE be in frequency with the printers head and bed. However, when there are two or more printers, this creates out of sync frequencies that can really ruin the quality of a print. As will be shown, I believe it did have an effect on the outcome of the text, but that would require further testing. Below is a video of the wobble, it is strangely difficult to capture correctly, so use the reflection in the glass to see it a little bit.
<iframe
  width="315"
  height="560"
  src="https://www.youtube.com/embed/5UMjY0SFJqg"
  title="YouTube Short"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
  allowfullscreen>
</iframe>

### Printing 
Luckily, there were no failures while printing for the first time. Adding a brim to the hollow cylinder might have affected the results of the tolerance test, so I was worried that not using a brim might causing it to fail. But it came out great. Below is a very speed up video of the print. Sadly I missed the last layer by a minute, but I at least got the bed moving down.

## Now that it is finished, what is the point of this artifact?
The overall point of tolerance tests is to see how much a 3D printer affects the actual printed dimensions of a part vs the dimensions of the original part created in CAD software. This test I made in particular was originally only to see how much of a gap was needed between the main part (the hollow cylinder) and the variably sized holes. Also, I further deviated from other similair versions of this test since made the hollow cylinder open on both sides. This allowed me to also test the side that was touching the bed Later, I will realize there is a bit more than what I initially thought

## Outcome of the Artifact
### Testing the Artifact
Finally, once the print finished and cooled down, I immediately tested which pole the hollow cylinder could fit into. As seen in the first half of the video below, I chose to start with the side that was on the print bed. To my surprise, it actually almost slide right into the exact dimensional pole. This told me that the part likely needed just a slightly bigger gap (and therefore a smaller diameter pole), so I was not surprised when it fit in the -.1mm hole. Further surprising, the exact same result happened with the opposite side. The last big surprise, as seen in the second half of the video, was that on a second attempt, both sides fitted into the exact hole.

### Was my guess wrong then?
At first glance, it seems that my guess was right about the printer bed side of the hollow cylinder, while being wrong about the opposite side. While this is technically true, I was still very surprised by this result that I further investigated it. I decided to measure the diameter of everything, and the result is seen below.





How was it able to only be .1mm or possibly right above a 0mm difference? Is this a near perfect printer? No, this is not the case. It must be taken into account that the poles themselves have a tolerance as well. Upon measuring the poles and the inside of the hole, I found that both near equally had a change in diameter by -.2mm. This seems to be the problem with this sort of test. Clearly I did not take this into account when I originally designed this 
