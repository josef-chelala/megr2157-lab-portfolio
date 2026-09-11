# Lab 4 – Benchmark a Parameter
## Objective
The objective for this lab is to create our own benchmark artifact to test one of the labs 3D. We were recommended to test overhang angles, tolerances, and dimension calibration.

## Parameter 
### Choice of Parameter
When I first started the project, I initially wanted to combine the tolerance and overhand test to see how the different angles of overhang would affect the tolerances of the print. However, after discussing this with the professor, I realized it would likely take a decent amount of measuring with this combo. To make things simpler, I decided to chose the tolerance test to make measurements easy using a caliper. Specifically, I decided to test the dimensional tolerances of 

### Inspiration 
After being inspired from [this tolerance test I found online](https://www.printables.com/model/1114097-cylinder-tolerance-passthrough), I wondered if I could invert this idea to test the tolerance of a single hole among several poles. With additional help from my Professor to further develop the idea, I decided to commit to it. 

### Tolerance Dimension Ideas
When I was looking through printables.com, I saw that people were using a different range of numbers for the tolerance test in millimeters. The one that inspired me in particular went up to .4mm. The millimeter part made sense to me, given 3D printers operate in mm, however, I was not sure on what tolerance numbers I should use. Then I stumbled upon [this article](https://3dput.com/complete-guide-to-3d-printing-tolerances-and-fit-getting-perfect-clearance-for-moving-parts/#complete-guide-to-3d-printing-tolerances-and-fit-getting-per) that stated that depending on the quality of the printer, tolerances usually range from about ±1mm to ±5mm. So I set out to make a 3D model based on testing those numbers. I decided on testing a 10mm diameter to have simple numbers to work with. 10 mm ended up being a great decision because the next day in the middle of making the model, I remembered that the professor showed us the "Design Rules for 3D Printing" guide and tolerance was mentioned there. To double check my work, I looked back on it and noticed that this paper used a ±.3% tolerance percentage instead of a numbered range. With this realization, choosing 10mm was the perfect choice since it gave a ±.3mm so I did not have to completely change my work. I decided that I would keep the ±.4mm and ±.5mm section for a worst case scenario, but I would delete them if it made the print job way too long.

### Guessing
This is before I researched how build parameters affect tolerances. .5 and -.5 are extremes, I am positive it will not match at 0. My guess is that on the side that was printed on the bed, the material will be expanded toward the center of the cylinders axis since the filaments on first layers usually pancakes out, causing a +.1 to +.2 mm increase in diameter. On the top side, I believe the material will contract after the filament cools, so the top side might decrease by -.1 to -.2 mm in diameter. Lastly, I believe that each pole will also contract due to cooling, so again I expect those to decrease by -.1 to -.2 mm in diameter

## Choice of Build Parameters
Tolerance is not just based how accurate the printers motors or mechanism are able to move the hothead, it is also dependent on the other factors such as build parameters.

### Infill
While researching how infill patterns affect tolerances, I noticed that patterns affected different kinds of shapes differently. However, I found this study that stated that the[ Gyroid patterns have the least tolerance percentage for cylindrical shapes](https://journals.sagepub.com/doi/abs/10.1177/09544089241312637). Therefore I decided to use Gyroid pattern. 

Infill parameters seem to be hard to pin down on how exactly it affects tolerance. After skimming through some studies on the subject, it seems that there is a variation in results of various infill percentages. One study might say an increase in infill increases tolerance, while another might say the opposite. [Then I stumbled upon this study](https://www.researchgate.net/publication/403402693_Influence_of_Infill_Density_on_Dimensional_and_Geometrical_Deviations_of_PLA_Parts_Fabricated_by_FDM) that states that while it seems infill percentage affects tolerances, it is situationally affected, specifically stating that "that infill density has selective and direction-dependent effects on geometric accuracy, without indicating a general trend applicable to all types of deviations." Uncertain what percentage infill to use, I decided to base the percentage on what is used for benchy which [is about 10 to 15%](https://www.3dmakerengineering.com/blogs/3d-printing/the-power-of-the-3d-benchy). I decided on 15% to give the structure a little more strength.

### Build Orientation and Supports
The affect that build orientation and supports have on tolerances is significantly clearer then infill. Since 3D printers work in layers that give little steps when there are more rapid angle increases, so the way you orientate cylindrical models has a massive impact on its dimensional tolerance (although in a different fashsion) of its circular surfaces. For example, if one were to try to print a tiny rod by making its rounded sides touch the bed plate, then the curved surfaces will have tiny steps for each angle change and will require supports to make sure the print doesn't fail. Plus, since the supports need to be in contact with the object itself, this further warps the surface of the cylinder This clearly changes the dimensional geometry of the object. For that reason I need to make sure that the cylinders I am using for testing are vertical. 

### Scale
Scale also affect tolerances. On the extreme of small dimensions, 

How was it able to only be .1mm or possibly right above a 0mm difference? Is this a near perfect printer? No, this is not the case. It must be taken into account that the poles themselves have a tolerance as well. Upon measuring the poles and the inside of the hole, I found that both near equally had a change in diameter by -.2mm. This seems to be the problem with this sort of test. Clearly I did not take this into account when I originally designed this 
