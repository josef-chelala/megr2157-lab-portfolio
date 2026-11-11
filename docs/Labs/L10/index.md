# A10 – Lead Screw Translating System

## Research and Planning 
### RC 2 Fit
According to the Machinery’s Handbook, “RC 2 Sliding fits are intended for accurate location, but with greater maximum clearance than class RC 1. Parts made to this fit move and turn easily but are not intended to run freely, and in the larger sizes may seize with small temperature changes.” RC 2 fits are used to allow two parts to move against each other without getting stuck, but keeping them close enough together that they don't wobble around excessively. In other words, you should be able to push and pull the shaft without it getting stuck, the shaft doesn't move sideways and wobble inside the hole, and you don't want it shifting around unpredictably. [As an example, when needing to use drill bits inside guiding bushings](https://fliphtml5.com/cvloa/pdtx/Design_of_Jigs%2C_Fixtures_and_Press_Tools_%28_PDFDrive_%29/107/). The RC 2 fit, keeps the drill bit aligned with the intended drilling location, prevents the drill bit from wandering when it contacts the workpiece, maintains consistent hole positioning across multiple parts, and lastly reduces errors caused by operator movement or inaccurate positioning. If the clearance is too small, the drill bit may bind or experience excessive friction. If too large, the drill bit can shift, vibrate, and produce inaccurate holes. When given the accurate clearance, when the drill bit moves it will be supported well. Below is an example of a drill guide bushing. The chart for the RC 2 fits is seen below (albeit only diameter sizes that can be reasonable for this project:


<img width="489" height="445" alt="MVQ3xDSjGxqLAXwGIGQwokU7-zERCm9oBA12yVE9mUxET5kMoxxkZtJrQukKO21i4XISLowIhkR5KRrZrR3RuLUtqPkmvx7p9rXcG1zwU4J1J9lrkMvLYnOFB9sbfD8GIvhrX-9Jwk5JpYWHe5DxAb3_oUmbL0p0UvdfmwPJRg2uGDthQ0L_Izmru_k8wgg3" src="https://github.com/user-attachments/assets/c03d69e6-edae-4e20-8976-7b0700ff1abf" />



<img width="1160" height="980" alt="image" src="https://github.com/user-attachments/assets/ed3055ff-4e60-437e-a5b5-a6d0d87747f7" />

### Limitations and My Design (Note to TA: Please Read Note at End of This Section)
This week was (and the following weeks ahead are) incredibly busy. Other classes and other projects in this class were taking a bunch of my time. Also, I had two seperate personal projects that had to be finished in an unknowable but short amount of time otherwise I could have been locked out from doing them forever, so I did not want to take chances and put more focus into them. For that reason I had very little time to do this project. By the time I was able to do it, I realized that everyone was using the machines at the same time. This then became apparent that I likely only had one shot at printing my parts, if it failed, there was a very real possibility there would not be enough printers left for me to finish on time. For those reasons, I was ironically forced on an assignment that required more creativity to make a much simpler design than my previous projects in this course. To not screw others over and to not make any mistakes that would ruin the print, I needed to make something that would not be massively affected by using the lowest quality but fastest settings (such as .1mm layer heights). This led me to the idea of making a spool that can be used for fishing lines. Essentially, a fishing wire can be wrapped around it to store it without making a mess, but due to the RC 2 fit, the spool itself can be rotated to quickly wrap the line around it without having to wrap the wire itself. This would also do the opposite affect when pulling some line to use quickly, where I didn't have to unravel it slowly. Due to all surfaces being parallel and circular, I thought that it may be possible for me to side step having to put them at an angle that may worsen shaft and hole tolerances that a .1mm layer height may cause with stepping (later I further thought this was possible when my coupon succeeded without a hitch). For my choice of hole and shaft diameter, I needed a balance that would give me a low print time but also a decently large RC 2 clearance (since larger diameters gave larger clearances). Looking at the chart, I decided on .25 inches since it was right at the smaller side of the .24in - .40in row of the RC 2 chart. This would give me clearance gap (in thousandths of an inch) of .2 to .85 Below is the general design I was going for followed by the section of the previous RC chart for a .25 inch diameter. 


<img width="1378" height="1580" alt="image" src="https://github.com/user-attachments/assets/7c9b7108-f083-4c3d-97d7-01bc124c7bac" />

<img width="1160" height="739" alt="image" src="https://github.com/user-attachments/assets/a879a2f0-f14e-474c-90f6-39644ee62d22" />



NOTE TO TA: I felt that this simple design would anger the teacher and cause my grade for this assignment to take a hit. However, when I mentioned this to him when I showed him the result the class day it was due, he did not care and implied it was fine. If you disagree or don't believe me, please ask him yourself before you take points off.


### Issues Using the Machinery’s Handbook
A major problem with using the handbook for creating fits is that this section of the book was made specifically for metal and at specific manufacturing grades. Additive manufacturing like FDM and SLA (which is used for this project) have far worse tolerances then the Grades 5 and 6 (like Broaching) manufacturing quality used in the above chart. This is were I think things should be made more clear in the class for the future, but from my understanding (and what I used for this project) is that the clearance gap shown in the image above is the standard range for RC 2 fits no matter the manufacturing process. However, the tolerance limit ranges listed can not be used for all types of manufacturing. It can be possible to use a grade chart a couple pages before in the handbook to add/subtract dimensions to the grade to account for this, however it is again for metal manufacturing. SLA is drastically more variable in dimensional accuracy, so simply finding what specific grade it follows is not a good option. 


Actually, it may be possible to use Turning, shown in the book, as a somewhat comparable situation. Turning's grade ranges is from 7 to 13, this is pretty massive gap. What this likely means, is that there are a variety of variables in turning that need to be accounted a for to know what grade of turning their setup even has. That can includes, but not limited to, the specific machine, tooling, material, and setup used. SLA is even worse than that. Now in addition to its horrid dimensional accuracy, it has to be taken further into account printing issues like cupping or layer stepping and how curing a finished print further changes dimensional accuracy. When reading how to take these and the mentioned shrinking or expansion of the resin prints into account, it was clearly explained that there is not really a one size fits all grade or tolerances to choose from. The only way to figure it out was to do test prints like a coupon. 









## Fit Test


### Results
The result was both a success and a failure. When first testing my part, I thought that the fits were too loose and I ended up failing. However, and hours later, I realized that it actually depended on the orientation shaft was inserted. On one side, the shaft is very loose and the spool could easily run along it. When inserted in the opposite direction, it worked as intended.
