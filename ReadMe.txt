MapEditorVR

*Program will not run properly without an HTC Vive*

*Logitech c270 webcam was used for tracking*

*Webcam image dimensions are "640 x 480"*

*Tracking Colors must be adjusted current lighting*

To make tracking easier, "Logitech Webcam Software" was downloaded and used to change the settings for the webcam to make tracking easier. We found that setting exposure, gain, brightness, and color intensity high and setting contrast low helped simply the tracking of colors greatly.

Tracking works but lighting must be Ideal. Although we used legos, colored objects used should to be shiny. Any shining light in webcam image will cause tracking errors. A black surface was used as the background and red, green, and blue legos were used as tracking objects.

The webcam texture is placed on a raw image in the same ratio as the webcam and objects are spawned parented to the ram image. By defealt the raw image text is disabled but can be enabled for debugging purposes. The raw image is parented to a panel wich is parented to a canvas which can be scaled to whatever play space is desired.

Currently not ready for full build and will need to be used in unity.

Load "Forest Scene"

Run the program and press "Space" to spawn objects based on webcam tracking. Everytime space bar is pressed the old tracked objects will be removed and the new ones will spawn. As of now the only other way to remove tracked objects is manually by deleting in the hierarchy or by ending the game.

UI system for tracking options will need to be build before it will be ready for a full build. For now the tracking options are adjusted through "ColorTrackerScript" which is attached to the game object called "TRACK_CONTROL_RawImage". This can be found parented to WCM_Panel which is parented to WebCamMonitorCanvas.

"T Ctrl Array" is an array of Tracking Control Objects. There will be one tracking control object for each color being tracked. The size is the number of colors to track.

Each tracking control object has a set of parameters for tracking control...

"Color" is the color the camera will be tracking. The best way we have currently to match the color to the color of the tracked object is to save the image of webcam by running the game and pressing "enter" on the keypad or right clicking the mouse. This saves over a test image in the images folder. This image can then be opened in an image editing program where you can select find the color of the object desired with the eyedropper tool and copying the RGB values.

"Color threshold" is used to adjust how close of a match the pixel needs to be.

"Distance threshold" is how close a pixel that matches the color must be to tracked as  the same object. If it is past the distance threshold then it will be part of a new object.

"Size threshold" determines if an object is big enough to be tracked.

"Spawn object" is a prefab of the object that will be spawned at tracked location.

"Rotation" determines the rotation of a spawned object.

"Scale" determines the scale of a spawned object.

"Tracking On" enables tracking for the given color when algorthm is ran.

"Tracking by pixel" is a boolean that changes the tracking algorithm from "clamping" which is faster but less accurate, to "by pixel" which is slower but more accurate.

"Show pixels" when enabled with change the matching pixels to a different color. Only works with test images and not the webcam. Used for debugging purposes.

"Object Spawn On" when enabled will spawn the spawn object on top of each marker which its location is based on the tracked colors found.

"Markers On" When enabled will make marker objects visible. These objects mark the tracked objects location and spawn the game objects.



Other parameters of Color Tracker Script...

"Webcam source" should be left on tracker. other options maybe platform specific.

"Tracking enabled" when enabled will run the tracking algorthm every frame update. Will not work well with VR and is used for debugging.

"Marker prefab" is a prefab that will be used to represent a marker.

"Image array" is an array of images that can be used for testing the tracking algorthm instead of using the webcam. Pressing "Enter" will toggle between whether tracking is based off of the webcam and test images. Pressing "left arrow" or "right arrow" will switch between test images. (different webcams can be scrolled through with the bracket buttons)

"Raw Image (script)" can be enabled to make the webcam texture visible for debugging purposes.



HTC Vive controls...

Trigger will pick up paintball marker and fire it.

grip buttons will drop paint ball marker.











- Nick Paulson