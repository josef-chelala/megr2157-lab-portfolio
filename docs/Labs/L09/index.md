# Lab 9 – Laser Cutter

## Group Members
I worked on this project with Joel Holder and Jack Brandon

## Design
### CAD Process

### Parameters
#### Parameter Table 

The parameter table summarizes the measurements and values used to develop our design. To determine the material thickness, we used calipers to measure at least three different locations on each sheet and calculated the average thickness. We also determined the laser kerf in both the X and Y directions to understand how much material was removed during cutting. These measurements, along with our selected clearance, helped us determine the slot dimensions needed to achieve a proper fit between the parts.


| Variable Name | Value | Units | Source | What it controls |
|---|---|---|---|---|
| Material Thickness | 2.77 | mm | measured | slot height |
| Kerf (x) | .097 | mm | calculated | slot dim. |
| Kerf (y) | .137 | mm | calculated | slot dim. | 
| Clearance | 0.2 | mm | research, testing | fit |
| Slot Width | 2.95 | mm | testing | fit |


THE FOLLOWING IS ALSO FOR THE Manufacturing - Test coupons SECTION OF THE GRADING RUBRIC

At the beginning of the design process, we planned to use a clearance of 0.10 mm between the inserts and slots based on our initial research. However, after cutting and testing our coupons, we realized that some adjustments were necessary to improve the fit. Based on our testing, we found that increasing the slot dimension by 0.25 mm in the Y direction and decreasing it by 0.475 mm in the X direction produced the most consistent results. The Y-direction adjustment was reasonable because our material thickness measurements were fairly consistent across the sheets. This allowed us to increase the slot opening slightly to make assembly easier. For the X direction, we had to consider the material removed by the laser from both the slot and the insert. Because the kerf affected both connecting features, we reduced the slot length to compensate and create a more secure connection. One result we found interesting was that the slot dimensions that worked best during testing did not completely match our original clearance calculations. When considering the measured kerf, the theoretical clearance was approximately 0.28 mm, which was greater than our intended clearance of 0.20 mm. At the same time, reducing the slot length by nearly 0.50 mm suggested that the connection could be too tight in that direction. Despite these differences, the parts fit together well during our physical testing. This showed us that theoretical calculations do not always predict the exact results of the manufacturing process, making test cuts an important part of our design process. We will discuss these differences further in the report.


### CAD Creation
This section is limited because my group member has all the files for Fusion 360 that I do not own, and have never worked with that program even if I had it. It costs $85 a month and I simply do not have the money for it nor the time to learn how to use it. I hope all my previous work throughout the semester can show how detailed that I usually get and can be given a slight excuse for this project.

For our project, we chose to design a simple model airplane. Our goal was to make it resemble the shape of a real aircraft while paying closer attention to how the different parts connected, especially where the wings fit into the slots on the fuselage and engines. 

#### Parametric Design


<img width="1502" height="605" alt="Screenshot 2026-11-11 144200" src="https://github.com/user-attachments/assets/dcaef081-0f58-4ba4-8323-77669f3b9b3a" />


We used parametric variables to make the design easier to adjust. We were incredibly limited on using the parametric design, because nice curvature needed us to use splines (later we realized this made things more complicated).  As shown in our parameter table, the slot width remained constant because the material thickness did not vary significantly. We also used a variable called "x_diff", which was subtracted from the length of each slot to account for the necessary adjustments like tolerances and kerfs. Since the slots had different lengths, this variable allowed us to apply the same adjustment throughout the design. In the sketches below, the "fx" symbol next to the dimensions indicates that those values are controlled by parametric equations rather than being entered manually. Having had difficulty getting in contact with my group member, I am unable to show the proof. Using words to explain, if we change the slot width, it is like changing the thickness of the wood, so the holes must expand to compensate for a change in different wood. Furthermore, if a different laser cutter was used, or the same laser cutter was calibrated differently, the x_diff can be adjusted to take the new and different kerfs, tolerances, etc...  Since the laser cut is done in the x and y direction only, the same model will still work with increased joint dimensions within reason of course. It may take slightly different placement of them of course, but only slightly. 

#### Creating the Body

Starting with the body of the plane, we created a general outline of it. Then, and doing this for the rest of the model as well, we made the poor decision of using splines to make it. This wasted us an hour when we finished the whole model because fusion had a rough time exporting the splines correctly when we tried to put it in Inkscape, luckily, I figured out how by exporting it in a way that it treats a surface like an image. Anyhow, the body acted as the hub for joint holes to connect the wings. Then added a flat plate at the bottom of it, this allowed  us to connect it to the base for the wooden plane.

<img width="1012" height="467" alt="Screenshot 2026-11-11 144306" src="https://github.com/user-attachments/assets/859940da-8466-411a-a44b-a826e80a7f1d" />



#### Front Wing 
The wings were the easiest part. To create the front wing, we simply create two circles and a straight line. Then using the spline tool we connected them together. The front wing connects to the front of the body by sliding it into the joint hole. The wings are basically its own joint pin and makes it easy to push into the body. 

<img width="958" height="356" alt="Screenshot 2026-11-11 142854" src="https://github.com/user-attachments/assets/b77f35b0-72f9-4c92-84e8-2034b0881345" />


#### Engines

For the engines, we simply traced over an image we found online that we sadly could not find again later. Thank you to the random engine picture we found. These connect to the front wings. In reality, the engines' joint holes connecting to the wing actually do not need to be incredibly accurate because the wing ramps up and so just pushing continuously will eventually reach a good connection point. But we guesstimated where they might land using another sketch with a line in equal length as the pin holes length. 

<img width="731" height="522" alt="Screenshot 2026-11-11 144855" src="https://github.com/user-attachments/assets/4da8078a-cde2-44e0-811d-c9e8fe2ce888" />

#### Back Wing
The back wing works similarly to the front, only it isn't curved. We simply created a box shape with a slight straight ramp. Then we added indents to the side that will match the wood thickness forthe flaps to lay roughly flush on it. Meaning this time it needs to be a more accurate like the rest.

<img width="1247" height="426" alt="image" src="https://github.com/user-attachments/assets/8a410104-faf2-48a6-b8cf-5096e0fec2e5" />


#### Flaps
To keep the stability of the plane's direction when it flies in the air, we added these flaps. Ok, it is just for works you got me. To make it we just made four circles and connected them tangentially together and added the joint holes to connect it to the back wing

<img width="830" height="582" alt="Screenshot 2026-11-11 144009" src="https://github.com/user-attachments/assets/a76e2a10-0822-4f85-9b25-55ecdac69d89" />


#### Base 
The base was just a simple square with the hole for the flat plate attached to the body to connect to it. It could have been much smaller, but we decided to make it as large as possible to ensure that the plane would not tip over. 

<img width="606" height="638" alt="Screenshot 2026-11-11 150557" src="https://github.com/user-attachments/assets/1f73ed5f-0f8f-4d6e-bfd5-d16b475e01be" />


#### Complete Model

The following is all the parts put together to make:


<img width="802" height="510" alt="image" src="https://github.com/user-attachments/assets/2fd96b6b-8456-4e83-9284-a590125d8c7f" />


## Manufacturing 
### Process Research

Laser cutting is a manufacturing process that uses a high-powered laser beam to cut through materials like wood, acrylic, and cardboard. The laser follows a path created from a CAD design and uses heat to remove material. During this process, a small amount of material is removed, which is called kerf. This is important because it can affect how well the parts fit together. Laser cutting is a good manufacturing method because it is accurate, fast, and can produce detailed shapes. For our project, it was a good choice since we needed to cut multiple flat pieces for our model airplane and assemble them using slots.

Compared to FDM 3D printing, laser cutting has some advantages and limitations. One major difference is speed, since laser cutting is usually faster for flat parts while FDM printing builds objects layer by layer, which takes more time. Another difference is the materials used. FDM printing mainly uses plastic filaments like PLA and ABS, while laser cutting works with sheet materials such as wood and acrylic. However, FDM printing is better for making complex 3D shapes, while laser cutting is mostly limited to flat designs that need to be assembled. Overall, laser cutting was the better option for our project because it allowed us to make the airplane parts quickly and test different slot dimensions to improve the fit.

### Creating the Square and Coupon
This part of the project was a headache. We went through a ton of different squares and coupons trying to find a consistent result. Once we just accepted what we had, a worker at the fab lab told us this was a lost cause and did not understand why we were doing this. He explained that this is all incredibly random because of the structure of wood and so finding accurate results is nonsensical. 

To measure the kerf, we first designed and laser cut a square with dimensions of 25 mm x 25 mm. After cutting it, we used calipers to measure the actual dimensions of the square and compared them to the original dimensions from our design. By subtracting the measured values from the original 25 mm in both the X and Y directions, we were able to calculate the kerf. We also created test slots with different clearances to see which one would give us the best fit when assembling the parts. For this test, we decided to use three different fits: tight, target, and loose. This helped us compare the results and determine which clearance would work best for our final airplane design.

#### How We Made Them
Instead of just making 3D models, we decided to just make them within the inkspace program
<img width="442" height="393" alt="Test Fits V1" src="https://github.com/user-attachments/assets/21221849-a503-4fad-8eee-d4d5dda9fdd6" />

#### How We Cut Them

<iframe width="560" height="315" src="https://www.youtube.com/embed/c-uBDx4bq7c?si=3hryEov-dCtwe6AC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

#### The Immense Amount of Tests
We essentially combined the two tests together to try and be more consistent, and there did seem to be a general trend like in some of the examples below, but it still would come out different each time we cut them out. We actually have a bag of these things from all our trials. That is also only one of the coupons we made. We thought it was us that was the problem, but it turned out this was just flawed from the start. Our results was previously explained earlier on this webpage.

<img width="4283" height="5711" alt="Coupons and squares" src="https://github.com/user-attachments/assets/7e4fa922-93bd-4d0d-b265-df514d6dbe78" />


### Laser Process Record

| Setting	| Kerf coupon	| Fit coupon | Final cut |
|---|---|---|---|
| Laser cutter (name or number) | SFL LA-5 | SFL LA-5 | SFL LA-5 |
| Material type	| wood | wood | wood| 		
| Nominal thickness	|	3 | 3 | 3 |	
| Measured thickness (mean) | 2.77 | 2.77 | 2.7 |	
| Speed | 20% | 20% | 20% |
| Power	| 100% | 100% | 100% |
| Frequency or PPI (if applicable) | 20%| 20% | 20% |
| Number of passes | single | single | single |
| Focus method and how you confirmed it | default | default | default |
| Air assist on? Exhaust on? | both on | both on | both on |
| How you set origin and alignment | top left | top left | top left |

We used the default focus method since the TA recommended to try and keep the default settings since they were good enough

### Layout for Plane Cutting


## Lessons Learned

When looking back at our measurements and the final results, we noticed that the calculations did not always match what happened during testing. Our measured kerf was around 0.1 mm, and if we had only used this value to calculate our slot dimensions, we would have ended up with different measurements than the ones we selected. For example, using a material thickness of 2.7 mm and our target clearance of 0.2 mm, the slot width would have been approximately 2.8 mm after accounting for the kerf. However, during testing we found that a slot width of 2.95 mm worked better. We also noticed that the thickness between our two wood sheets had a difference of about 0.07 mm, which could have affected the results. Using the smaller slot width might have improved the connection, but it also could have made assembly more difficult since some of our parts already required a little force to fit together.

Another issue we noticed was with the length of the slots. Based on our calculations, the kerf from both the insert and slot should have created about 0.2 mm of clearance without needing to change the original slot length. Instead, our testing showed that reducing the length by 0.475 mm gave us a better fit. The interesting part was that this adjustment should have created an interference of around 0.275 mm, making the parts difficult to assemble. However, when we assembled our final airplane, most of the pieces connected without much effort. One area where we did experience some problems was the main wing. The width of the connection was acceptable, but the slot length was slightly too tight by approximately 0.1 to 0.2 mm. The wing was still able to connect to the fuselage, but the fit was not exactly what we wanted.

This situation can also be related to Taguchi's Quality Loss Function, which is represented by the equation L(y) = k(y - m)^2. In this equation, y represents the actual result, m is the target value, and k is a constant related to the cost of being away from the target. The equation shows that the farther a measurement is from its intended value, the greater the quality loss becomes. For our airplane, a connection that is slightly too tight might not seem like a major problem. However, if we were producing 1,000 airplanes with the same issue, the total losses could become much more significant because every unit would have the same problem. This helped us understand why small dimensional errors matter in manufacturing.

A real-world example of this would be a wooden puzzle that uses interlocking pieces. If the kerf is not properly considered during manufacturing, the pieces could end up being too loose or too tight. A tight connection could make the puzzle frustrating to assemble or even damage the pieces, while a loose connection could make them fall apart easily. This shows how an incorrect kerf measurement can affect the quality of a product and the experience of the customer.

If we had the opportunity to make another cut, we would spend more time checking our measurements and testing the connections before cutting the final model. We would especially focus on the slot length because that was where we noticed the most unexpected results. We would also try slightly reducing the slot width to see if we could get closer to our intended 0.2 mm clearance. Our goal would be to make the airplane more stable while still allowing the pieces to be assembled without too much force.


### Process Log
| Date | Time | Step | Occurrence/Decision |
| ----| ----- | ----| --------------------- |
| 10/23/26 | 1:57pm | 1 | Material thickness measured (2.77 mm) |
| 10/23/26 | 2:38pm | 2 | Test Coupon cut, Measured |
| 10/23/26 | 3:24pm | 3 | Fit test V1 cut |
| 10/23/26 | 3:32pm | 3 | Fit test V2 cut |
| 10/23/26 | 3:39pm | 3 | Fit test V3 cut |
| 10/23/26 | 3:50pm | 3 | Fit test V4 cut |
| 10/23/26 | 4:02pm | 3 | Fit test V5 cut |
| 10/23/26 | 4:10pm | 4 | Clearance chosen (0.2 mm) |
| 10/26/26 | 2:24pm | 2 | Kerf calculated (.097 mm X, .137 mm Y) |
| 10/26/26 | 3:05pm | 5 | Initial CAD completion |
| 10/26/26 | 5:04pm | 5 | Final CAD completion |
| 10/26/26 | 6:16pm | 5 | Final Inkscape file made |
| 10/26/26 | 6:31pm | 5 | Final laser cut completed |
| 10/26/26 | 6:44pm | 5 | Final assembly completed |
| 10/26/26 | 11:28pm | 6 | Parameter and Laser Process Record completed |
| 10/27/26 | 1:24pm | 6 | Documentation Completed |


### Resources Used and Time Spent

For this project, we used two wooden sheets that were approximately 12 x 12 inches, with a nominal thickness of 3 mm. The first sheet was mainly used to cut our test coupons and experiment with different fits, while the second sheet was used for the final airplane parts. From the beginning of the design process to the final assembly, we spent approximately 12 hours completing the project.

