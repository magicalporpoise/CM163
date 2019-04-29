# CMPM163 - HW1
# Philip Stanley - pdstanle@ucsc.edu 

ESC can always be used to exit the applications

======
Part A
======
I stated with a plane; 3 objects (bananas, a hotdog, and a pineapple);
and 3 point lights (red, green, and blue)

bananas: I wanted to learn how to use transparency in shaders,
so from a tutorial I modified a "hologram" code to manipulate
the bananas to grow and twist with a light blue transparent skin

hotdog: used a simple phong shader in an attempt for it to handle more than 2 lights.
However a strange error occured where while the material was attached to the object,
it would disappear in the scene view, but not the game view
(even after including the shader in Project Settings > Graphics)

pineapple: combining aspects from the previous shdaers,
I made the fruit react to the multiple lights (same error as the hotdog)
and made it such that only the top half of the fruit would be expanded
and manipulated

I than made the lights and objects rotate around the scane above the plane
using a simple rotator script

======
Part B
======
My goal with the texture modification shader was to use the blur effect,
but excluding a certain color. I started with the provided blur shader,
as it contained code that I would need for bluring and neighboring pixels,
and then added in another property to account for a color to ignore in the
blur (along with a float for the tolerance / acceptable range / closeness to that color).

I made several cubes with this shader attached and scripts to add the correct image
on top of the texture (as modifiying the shader on the object in the inspector causes
all instances of the shader to update with that image). Then I made a controller script to
adjust: the range of the tolerance (0.0 - 1.0) and the blur steps (0.0, 75.0),
using W S and E D to increase and descrease them repsectively.

The color can only be modified in the inspector of the project since I did not have 
time to put in color controls into the application.

======
Part C
======
For my cellular automota, I made these rules:
1 - 6 colors { <- red <- cyan <- yellwo <- green <- blue <- pink <-} 
2 - Eaten <-- Killer (wraps around)
3 - Each cell looks at its 24 double neighbors
4 - If there are enough Killers and not enough Saviors, 
    that cell becomes its killer, otherwise is stays
The number of killers needed is 3, the number of svaiors needed is 18.
The script used to iterate the texture uses the ping pong method
described in class. It also allows for setting the update speed
and height/width per object.

======
Part D
======
What do you like about it?
 - It has a very grand effect, there is a lot of weight and intensity behind this still image
Does the effect change depending on the camera view? The lights? 
 - It changes the lights
Is it an effect that updates the geometry itself, or change the color of the pixels, or does it alter a texture?
 - There is a strong light being created from the center of the laser, and I imagine
   that the laser itself is a dynamic, semi-transparent texture put on top of a simple cylinder 
How do you think it was created? 
 - see above. There was also likely a lot of work put into the surroundings of the laser to allow
   its lights to affect them
What is the effect called? 
Do some research/Googling and see if you can find papers, online tutorials, or blog posts that give insight into how it
was created and how you might emulate it in a Unity shader.
 - No tutorials, but many people use this as an example for effects that would look good on a
   portfolio for visual effects.
