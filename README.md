# lab02-debugging

# Shader & Info 
Team: Neha

Link to the shader: https://www.shadertoy.com/view/l3fyD2

Bug 1: (line 111) 

This was a compilation error since 'vec' is not valid. It had to be changed to 'vec 2'.

Bug 2: (line 115)

The ray cast function parameter was 'uv' instead of 'uv2', which caused everything to be oriented weirdly (the middle of the red sphere was fixed to the bottom left of the screen). 
This was discovered via a hint from Rachel to take a closer look at the function's parameters and by adjusting the eye but being unable to orient the view to the desired view. 

Bug 3: (line 15)

The order of 'eye - ref' and 'H' was flipped. 
This bug was discovered by double-checking the order of the cross products to calculate the x, y, and z values and realizing the value was flipped. 

Bug 4: (line 20) 

Originally, the line said 'iResolution.x / iResolution.x', which would have resulted in 1 (thus not multiplying anything), so this was changed to be 'iResolution.x / iResolution.y'.
This bug was discovered by going through the raycast function and realizing that the division would result in 1, and it would have to be altered. 

Bug 5: 

The reflect function took in eye and the normals as the parameters instead of dir and the normals. 
This bug was discovered by accident-I was confident that there would be an issue in march, so while following how the outputs in that function were being used in sdf3D, I found that reflect was using eye instead of dir. Which doesn't make sense when calculating the reflection, so it was changed. 

# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
