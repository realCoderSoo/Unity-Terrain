# Unity-Terrain

The program creates a Unity terrain and add features of interest. This lab script specifies steps to be
followed, but the end result will be whatever you wish to put together.

1 Creating a Terrain

• Create a new 3D Project.
• Save the current scene in the assets directory, or a suitable folder inside it.
• Import the supplied assets for this lab (see module website) by unzipping the provided zip file and moving
the Provided folder into the Assets folder of your Unity project.
• Import the Environmental standard assets. Use Assets ! Import Package ! Environmental
• Add a Terrain game object to the scene. You can do this either by right-clicking inside the Hierarchy
(3D Object ! Terrain) or under the GameObject heading in the menu. This will automatically create an
associated terrain asset in the Project view, which stores the data for the terrain. You can rename this
asset if you wish, but do not delete it!
• You may wish to move the camera further out, as the created terrain will be large.


2 Shaping the Terrain
• When the terrain is selected, you will have access to some terrain-specific tools in the Inspector. If you
cannot see these tools, the terrain object is not selected.
• Use the first tool, Raise/Lower Terrain, to add some form of shape to the terrain. Clicking and dragging
on the terrain will raise the terrain, while holding shift and clicking and dragging will lower it.
• You can adjust the brush shape, the opacity and the brush size to see how different brushes affect the
terrain in different ways. Some add roughness to the height of the terrain while others allow for smoother
height transitions.
• Keep in mind that the provided base terrain is very large, and while a brush size of 100 may not seem
very large, the brush covers a 50 Unity unit radius, or the majority of a 100 by 100 unit square on the
XZ plane. This is the same size as a default cube scaled up to 100 on the X axis and 100 on the Z axis.
• You can use the second tool, Paint Height, to create plateaus and valleys in your terrain. Hold shift and
click on the terrain at a height you want to use, and then hold the left mouse button down after releasing
shift to paint only that height. If your shift click is at a low height, you will be able to easily paint valleys
or fissures through the landscape. A high height lets you paint plateaus and mesas.
• The third tool, Smooth Height, allows you to smooth the height of the terrain, with the brush opacity acting
as the strength of the smoothing. Use this tool along with Paint Height to make the height transitions
less abrupt.
• Try to create a terrain that features a mountain, or a valley, or some other interesting feature where the
elevation changes across the terrain.
1• You can, if you wish, also add some water to the terrain. Unity does not provide a direct way to do this, but
it does provide standard assets. In the Project View, open the folder Standard Assets ! Environmental
! Water ! Water4 ! Prefabs.
• Drag Water4Advanced into the scene. Scale it to fit as appropriate, but be aware that quality will drop
if the prefab is stretched too far.
• Other water assets are available, and the capabilities and performances of each differ. It’s advised to use
the prefabs provided instead of the raw assets.


3 Adding Textures to the Terrain
• Select the fourth tool with the terrain selected, Paint Texture.
• Before you can begin to paint textures onto the landscape, you need to set them up first.
• In the Project View, open the folder Standard Assets ! Environment ! TerrainAssets ! SurfaceTextures.
• Select Edit Textures... and then Add Texture. Click and drag one of the textures that is not MudRockyNormal into the box on the left of the window that comes up. Press Add.
• This will immediately paint the entire terrain with this texture, as it will be considered the default. Add
another texture in the same way.
• Select this second texture and paint your terrain with it. The brushes and settings are like before, with
the addition of a new Target Strength value. This is how much of this texture you’re painting up to. With
it set to 1, you can paint the terrain to be solid with this texture, and with it set to a lower value it will
remain overlaid on top of the textures it is painted over without overwriting them.
• If you double click the textures you have added, you can edit their properties and replace the actual image
being used with different ones while keeping the terrain data of how they show up.
• There is a limit of textures for the terrain, after which any future textures added will not be taken into
account. Try to stay around 4.
• Try adding different textures for different elevations, or drawing paths.


4 Adding Trees, Rocks and Grass
• Select the fifth tool with the terrain selected, Place Trees.
• As before with textures, we need trees to place. However, we need to add the trees to place them.
• There are three different trees provided within the standard assets (Standard Assets ! Environment
! SpeedTree). Inside each of these folders is a prefab tree, eg. SPalm Desktop, SConifer Desktop and
SBroadleaf Desktop. Remember to set the Bend property to 1 when adding the tree.
• These prefab trees may require materials to be generated first. With the prefab selected, press the
Regenerate Materials button at the bottom of the first panel of the Inspector.
• Select the terrain again, and select Edit Trees.... Click and drag the prefab tree of your choice into the
slot it provides.
• You can now add these trees to the terrain with a brush similar to before. You can hold down shift to
erase trees you have already placed. Be careful about placing large quantities of trees at a time, as it may
cause performance issues within Unity.
• As well as trees, you can place grass and rocks. Select the sixth tool, Paint Details.
• In the Project View, navigate to Standard Assets ! Environment ! TerrainAssets ! BillboardTextures.
• Select Edit Details... and select Add Grass Texture. Drag one of the two GrassFrond textures into the
Detail Texture slot. Uncheck Billboard, but feel free to experiment with the other parameters.
• As with every other terrain tool, you can now paint grass clusters onto the terrain, using shift to erase.
Holding ctrl will allow you to only erase the selected tree or detail type.
• Finally, select Edit Details... and Add Detail Mesh in order to add the provided rock prefab, RockMesh.
Drag the prefab into the slot, and make sure to change the render mode to Vertex Lit. Change the healthy
and dry colours to different shades of grey.
• When trying to place sparsely occurring objects down, do not hold the mouse button down when painting.
It is also helpful to set the opacity and target strength very, very low.
• Place all the trees, grass and rocks you want, but keep in mind that performance can be heavily affected
by trees and detail objects.


5 Adding Wind and Sounds
• Add a WindZone to the scene. GameObjects ! 3D Object ! Wind Zone
• Wind Zones can be directional (globally affecting wind) or spherical (wind that only affects a certain
radius). Set the Wind Zone to Directional.
• Move the Main Camera to a point where you can see the trees relatively closely, and press play. You
should see the trees being affected by wind.
• The scene is relatively quiet. There are two provided sounds, a wind loop and a loop of birds chirping.
You can add either or both audio clips to the scene as 3D sounds to add some sound to the environment
and make it feel slightly more alive.
• Add an empty game object to the scene, and position it in your terrain where you think it would make sense
for any of the sounds to come from, such as a forest. Name it "Sound Source" or something descriptive.
• Drag the sound of your choice onto the empty game object. Make sure that Play on Awake and Loop are
checked.
• Set the Spatial Blend to 1. This makes the sound fully 3D. With a Spatial Blend of 0, the sound will
play at full volume no matter how far the listener is from the source. With a Spatial Blend of 1, distance
matters entirely. If you always wanted a sound to be slightly audible, you could use a value between 0
and 1.
• Test playing the scene with the camera in different proximities to the sound. Notice that the sound volume
drops off the further away you are. You can adjust how far the sound carries and also how sharply the
volume drops off the further away you are with the 3D Sound Settings in the Audio Source settings for
the game object.


6 Day and Night Cycle
• In the same way that the camera’s transform can be animated, a light’s properties can also be animated.
• Select the Directional Light in the scene and rename it to \Sun". Set its rotation to (0, 0, 0).
• Open up the Lighting window (Window ! Lighting), select Scene if it is not already selected, and drag
the Sun light into the box that says Sun in the Lighting window. Now the sun will appear in the sky
based on the rotation of the Sun light.
• Create an Animation asset in the Project View and name it something like \DayNightCycle". Drag this
animation onto the Sun light, and open the Animation window (Window ! Animation) with the sun
selected.
• Create a new Animation Clip in this window. If you can’t see a button to do so, try making the window
larger.
• Add the rotation (Transform ! Rotation) and intensity (Light ! Intensity) to the animation properties.
• If the number next to Samples is not 12, set it to 12. The Samples box is just above the properties box,
to the top left.
• Select the beginning frame, make sure the rotation is still (0; 0; 0), and set the light intensity to 0:5. You
can select frames by clicking underneath the timeline shown at the right of the window. The red line
indicates your currently selected frame.
• Select the frame 25% of the way into the animation (Frame 3 or 0: 03 by default), press record and set
the X rotation of the sun to 90.
• Select the middle frame (Frame 6 or 0: 06 by default), press the record button at the top left of the
Animation window, and set the X rotation of the sun to 180. Set the light intensity to 0:5.
• Select the frame 75% of the way into the animation (Frame 9 or 0: 09) and set the sun’s X rotation to
270 and set the intensity of the light to 0.
• Select the very last frame and set the sun’s X rotation to 360, and the light intensity to 0:5.
• This animation will provide a day/night cycle, but it is far too fast to be used and will only play once.
• Select the Animation asset you originally created in the Project View. Check the box marked Loop Time.
• Double click on the Sun animator controller asset in the Project View. In the Animator view that comes
up, select the orange box. Change the Speed to 0:02 for a faster cycle, or to 0:005 for a slower one. Adjust
the values as you see fit.
• Optional: Using the idea of animating intensities, you could add and animate a Point Light that only
lights up a small area during the night.


7 Animating the Camera
• As has been shown in previous labs, it is possible to animate the camera from a starting point to an end
point. This time, however, we will create a slow flyby animation that moves the camera through your new
terrain, on a loop.
• To begin with, create an Animation asset in the Project View. Name it \CameraFlyby" or something
similar. Drag this animation onto the Main Camera.
• Select the Main Camera and create a new Animation Clip by pressing the button to the right of the
window, as before.
• Add the Position and Rotation properties (both from Transform) to the animation.
• From here, select a frame in the animation by clicking at a suitable point. You can add extra spaces for
frames by changing the Samples number from 12 to whatever it is you wish.
• At whatever points in the animation you wish, move the camera and rotate it to focus on whatever you
want in the scene. One way that can make this easier would be to navigate in the Scene view to places
you want the camera to focus on, and to use GameObject ! Align With View with the camera selected.
• You can make the flyby animation loop by selecting the asset in the Project View and checking the box
next to Loop Time, and you can make the animation faster or slower by double clicking on the Main
Camera animation controller in the Project View, selecting the orange box, and adjusting the Speed value
there.
• If the animation does not seem to be going the way you want it to, try selecting the animation frame
between the start of the problem and the end of the problem region, and, making sure that record is on
(record button is pressed down, play buttons show red, relevant fields are red, etc.), move and rotate the
camera into a more appropriate in-between state.
• As with most of this lab, whether or not the camera’s tour of your terrain is acceptable will be ultimately
up to you!
