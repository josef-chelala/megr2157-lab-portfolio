# Lab 4 – Benchmark a Parameter
## Objective
The objective for this lab is to create our own benchmark artifact to test one of the labs 3D. We were recommended to test overhang angles, tolerances, and dimension calibration.

## Parameter 
### Choice of Parameter
When I first started the project, I initially wanted to combine the tolerance and overhand test to see how the different angles of overhang would affect the tolerances of the print. However, after discussing this with the professor, I realized it would likely take a decent amount of measuring with this combo. To make things simpler, I decided to chose the tolerance test to make measurements easy using a caliper. Specifically, I decided to test the dimensional tolerances of a Prusa 3D printer.

### Inspiration 
After being inspired from [this tolerance test I found online](https://www.printables.com/model/1114097-cylinder-tolerance-passthrough), I wondered if I could invert this idea to test the tolerance of a single hole among several poles. With additional help from my Professor to further develop the idea, I decided to commit to it. 

### Tolerance Dimension Ideas
When I was looking through printables.com, I saw that people were using a different range of numbers for the tolerance test in millimeters. The one that inspired me in particular went up to .4mm. The millimeter part made sense to me, given 3D printers operate in mm, however, I was not sure on what tolerance numbers I should use. Then I stumbled upon [this article](https://3dput.com/complete-guide-to-3d-printing-tolerances-and-fit-getting-perfect-clearance-for-moving-parts/#complete-guide-to-3d-printing-tolerances-and-fit-getting-per) that stated that depending on the quality of the printer, tolerances usually range from about ±1mm to ±5mm. So I set out to make a 3D model based on testing those numbers. I decided on testing a 10mm diameter to have simple numbers to work with. Luckily, 10 mm ended up being a great decision because while I was in the middle of making the model, I remembered that the professor showed us the "Design Rules for 3D Printing" guide and tolerance was mentioned there. To double check my work, I looked back on it and noticed that this paper used a ±.3% tolerance percentage instead of a numbered range. As will be explained in the scaling section below, the percentage based vs fixed tolerance range are used depending on the print or can even be used at the same time. With this realization, choosing 10mm was the perfect choice since it gave a ±.3mm range and did not need to worry about percentages so I did not have to completely change my work. I decided that I would keep the ±.4mm and ±.5mm section for a worst case scenario, but I would delete them if it made the print job way too long.

### Guessing
This is before I researched how build parameters affect tolerances. .5 and -.5 are extremes, I am positive it will not match at 0. My guess is that on the side that was printed on the bed, the material will be expanded toward the center of the cylinders axis since the filaments on first layers usually pancakes out, causing a +.1 to +.2 mm increase in diameter. On the top side, I believe the material will contract after the filament cools, so the top side might decrease by -.1 to -.2 mm in diameter. Lastly, I believe that each pole will also contract due to cooling, so again I expect those to decrease by -.1 to -.2 mm in diameter. Possibly resulting in the side printed on the bed ending up fitting unto one of the poles labeled from +.1 to +.3, and the opposing side having to be fit unto the poles labeled from +.1mm to -.1mm, though I second guess it reaching to 0 and +.1mm


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
There are ways usually to increase the resolution of STL files exported by CAD software, but it can be rather unnecessarily cumbersome or confusing depending on the software. For SolidWorks I would have to go through several settings. Even then, there still might be noticeable edges. To by pass all this work, I could just use a STEP file (the closet to a universal CAD file), which basically keeps everything in the model nearly the exact same as how I made it with absolutely no strange edges. Luckily, PrusaSlicer allows directly importing STEP files, so I did it. So I simply exported my model as a step file.
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
After setting my chosen orientation as well as the infill pattern and pattern type. Then disabling supports and setting the print job to  .2mm SPEED mode. I found that the print time would be 44 minutes long. However, I forgot to screen shot this part, so below is a close setup of what I originally had. Except, for some strange reason this shows 50 minutes and I could not really find a reason why.
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
Luckily, there were no failures while printing for the first time. Adding a brim to the hollow cylinder might have affected the results of the tolerance test, so I was worried that this might cause the first couple layers to fail. But it came out great. Below is a very speed up video of the print. Sadly I missed the last layers by a minute, but I at least got the bed moving down. The problem is that I didn't have a stand, so the video is extremely wobbly (ironically).
<iframe width="560" height="315" src="https://www.youtube.com/embed/lJ8dkJ6RToU?si=EvshKCLK3nC1i2vl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


## Now that it is finished, what is the point of this artifact?
The overall point of tolerance tests is to see how much a 3D printer affects the actual printed dimensions of a part vs the dimensions of the original part created in CAD software. As I got closer to the end of writing my project report, I slowly realized that I have been somewhat misled by the works that inspired me of what exactly tolerance has to do with this type of test. In reality, it seems that this is a mix of tolerance and clearance. Clearance in 3D printing means how much of a gap is needed in order to allow part to mate to each other. This test I made in particular was originally only to see how much of a gap was needed between the main part (the hollow cylinder) and the variably sized holes. Does this mean that I messed this project completely up? No, I did not. Luckily, I unintentionally kept in account both tolerance and clearance through out this paper with my guesses, my parameter explanations, and so fourth. My results, as will be seen, also show both included as well. Meaning I could rewrite parts of this lab in order to show both, however, I am incredibly busy in all my classes so I simply do not have the time. 

## Outcome of the Artifact
### Testing the Artifact
Finally, once the print finished and cooled down, I immediately tested which pole the hollow cylinder could fit into. As seen in the first half of the video below, I chose to start with the side that was on the print bed. To my surprise, it actually almost slide right into the exact dimensional pole. This told me that the part likely needed just a slightly bigger gap (and therefore a smaller diameter pole), so I was not surprised when it fit in the -.1mm hole. Further surprising, the exact same result happened with the opposite side. The last big surprise, as seen in the second half of the video, was that on a second attempt, both sides fitted onto the exact hole.

<iframe width="560" height="315" src="https://www.youtube.com/embed/w2wCQVreWRE?si=-NEHjpYei2S38lgX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Was my guess right or wrong then?
#### At First Glance
At first glance, it seems that my guess was wrong about the printer bed side of the hollow cylinder, while being right about the opposite side. While this is technically true, I was not satisfied with the answer from this result and so I further investigated it. 
#### Digging Deeper
I decided to measure the diameter of everything, and the result is seen below. Although, keep in mind that using the inner measuring jaws of a caliper can be fairly inaccurate when measuring inner diameters.
![Inserted Picture](Pictures/measured.png)
As shown, it seems that each poles' CAD diameter decreases at an average of .175mm and the hollow cylinder's inner diameter decreased about .1mm (on both sides). It also shows that the size of the inner diameter is in-between the exact hole and the pole labeled +.1. Now, these measurements were made after testing that may have caused some yielding, so it is possible that the inner diameter of the test object increased after the first test and/or the outer diameters of the exact pole decreased after the second test. Even just a .05mm difference could cause "inaccuracies". As seen in the video, I believe this to be the case because the hollow cylinder simply would not go into the exact diameter pole on the first test. 
#### What was right?
 For tolerance, I was right that the poles' diameters (-.175mm) and the non-bed side of the hollow cylinder (-.1mm) would decrease by .1mm to .2mm. For clearance, I was at least right on the range of labeled poles +.1mm to -.1mm in which the the non-bed side of the hollow cylinder would fit. 
#### What was wrong?
The most obvious part I was wrong about was the tolerance of the diameter of the bed printed side of the hollow cylinder. It appears that the Prusa 3D printer I used is excellent at not noticeably pancaking first layers ( my tests do not measure the opposite), and so I massively overestimated how much the first layer (or more) might be compressed. Now, it is possible that there may have been some pancaking, and my two trials may have affected my measurements. However, it was thin enough that if there was any, it was easily overcome and basically imperceivable. This also means that I was wrong about its clearance pole range since mine implied it would at +.1 or above.
#### Round up of results
Keeping in mind that these are flawed results due to time of measurement. In the end, the physical test showed that the tolerance of the outer diameters of non-hollow cylinders will decrease about .175mm. While the only inner diameter shows a smaller decrease of .1mm. One sample size of the inner diameter is not good enough, but this does possibly show a trend that inner and outer diameters face different levels of tolerance, leading to having to take clearance in consideration. With clearance, the results are less clear. It seems that physically testing the clearance (like in the testing video) may show a difference in clearance before testing and final testing. It seems that before testing the clearance was likely in between the -.1mm and 0 range, and after it was in the 0 to +.1mm. Upon measuring, however, it is possible that the before and after clearance was within the ±.05mm range.

## 3D printing design rules
### How does this compare to 3D printing design rules?
Basing the design rules on the data sheet "Design Rules for 3D Printing" by Protolabs given to us in class, it seems that this printer did indeed follow those rules. The paper states that the tolerance for FDM printers depends on a ±.3% of a given length or a ±.3mm tolerance. Which one to use is based on which gives a bigger absolute value difference in length. This meant that a minimum length of 100mm was required in order to start worrying about the percentage based tolerance. Since all my testing diameters ranged from 9.5 to 10.5mm, I did not need to worry about it. Therefore, I just need to compare it to ±.3mm tolerance. As show in my measurements, the worst deviation from the CAD model for anything dependent on testing was only -.19mm. This meant that the tolerance was well within the ±.3mm tolerance.
### Why this result?
To start, all the parameters I chose for the G-Code minimized any sort of possible additional tolerance increase. Specifically, the gyroid infill pattern (based on my research) and my build orientation were the best possible choices for cylinders that are at the heart of a tolerance test. Also, my choice in using a STEP file likely made sure that the 3D printer was receiving the closest possible geometry of the CAD model that it could actually read. This meant that the only real major variables that affected the tolerance was the material used and the 3D printer itself. I used PLA, and PLA is generally really good with tolerances. PLA has a [very low shrinkage range of 0.3% to 0.5%](https://xometry.pro/en/articles/3d-printing-tolerances/) and is generally considered to not have a huge noticeable affect on tolerances, especially at the sizes I am testing. So my earlier guess as to how shrinkage will affect the dimensions was essentially wrong. This therefore means that the tolerances come directly from the printer itself. The actual range of tolerance at this level is heavily dependent on the quality of a 3D printer, the components used and how well calibrated it is. I obviously can not know about the calibration, however, Prusa is a world renowned brand for 3D printers and is well know for making quality printers (although maybe over priced). The problem is that it uses a .4mm nozzle and there are inherent issues with 3D printers that a tolerance range is inescapable, yet the parts used in their printers are high quality. Sadly, I could not find tolerance ratings for the printer that was used, however, using the data for my specifically used geometry does show that the printer is high enough quality to stay with in the Protolabs expectiation of ±.3mm.

## Learn Lessons 
1. I learned that infill percentages are not very clear cut on the affect that they have on tolerances of a print job. It appears that research on the topic shows widely varying results. This is likely a result of the fact that the infill percentage's affect has on tolerance is very situationally based. What was also nice to learn is that Gyroid was perfect for this test since it seems have the least affect on tolerances than other patterns. I say that because gyroid has become my favorite pattern due to this class, first because of the way it looks, and now because its properties consistently allow it to out preform most patterns in most tasks we have needed so far.
2. Another thing I learned that surprised me was how exactly the extent of tolerances work in 3D printers. It was surprising to learn that the tolerances expectations of a printed object depended on whether the tolerance based on the percentage of a length was bigger than a fixed based tolerance range. I haven't thought of that before, but it makes sense now. Since small lengths are less affected by overall incremental tolerances increases from things like material properties or warping, the only really major tolerances to take in consideration are the printer and its components as well as possible software limitations. However, as the size of a length increases, the incremental tolerances start to add up to the a point that it does create tolerance difference that need to be taken into consideration
3. One of the biggest changes I would make is reducing the tolerance increments from 0.1 mm to 0.05 mm. I originally chose 0.1 mm increments to reduce print time, but the final measurements showed that differences as small as 0.05 mm could affect whether the hollow cylinder fit over a pole. Since the purpose of the artifact was to characterize dimensional tolerance and clearance, using 0.05 mm increments would provide greater resolution and make it easier to identify the actual transition between an interference fit and a clearance fit.
4. I would also repeat the dimensional measurements and fit tests instead of relying on a single sample. The difference of clearnce between tests showed that the hollow cylinder and poles could be facing some yielding or deformation. In a future experiment, I would create more hollow cylinders of the same inner diameter (taking into account the possible variance between them). This would provide a more reliable estimate of dimensional variation and reduce the influence of measurement error and part deformation.

## Time Commitment
The amount of time I took on this project was about 1.25 hours of actually printing the object and 10 hours of any other work. 

## Resources
### Websites
1. https://www.printables.com/model/1114097-cylinder-tolerance-passthrough
2. https://3dput.com/complete-guide-to-3d-printing-tolerances-and-fit-getting-perfect-clearance-for-moving-parts/#complete-guide-to-3d-printing-tolerances-and-fit-getting-per
3. https://journals.sagepub.com/doi/abs/10.1177/09544089241312637
4. https://www.researchgate.net/publication/403402693_Influence_of_Infill_Density_on_Dimensional_and_Geometrical_Deviations_of_PLA_Parts_Fabricated_by_FDM
5. https://www.3dmakerengineering.com/blogs/3d-printing/the-power-of-the-3d-benchy
6. https://www.syntax3dlab.com/blog/tolerances-clearances-guide
7. https://xometry.pro/en/articles/3d-printing-tolerances/
8. www.youtube.com
### Software
1. PrusaSlicer
2. DaVinci Resolve
3. SolidWorks
4. GIMP
### Physical
1. Prusa Core One+ labeled PC_1
2. PLA
3. Caliper
### Data Sheet
1. "Design Rules for 3D Printing" by ProtoLabs
### People
1. Class Professor





