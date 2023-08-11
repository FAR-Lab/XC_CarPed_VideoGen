# Cross Cultural Video Generation Notes
## GitHub, Speed, Frames, Scale, References, Assets
**Summary:**\
Documentation for the animation creation for the crowdsourced study on implicit Driver to Pedestrian behavior (regarding the perception of a safe distance from the vehicle to the pedestrian to cross the street).

## GitHub
This project is currently stored in the XC_CarPed_VideoGen repository on GitHub under the FAR-Lab organization.
## Assets
The assets for this project are stored in the “3D Assets” folder in the main file structure.
### HDRI (Skybox)
Rustig Koppie (Pure Sky) by Greg Zaal and edited by Jarod Guest
https://polyhaven.com/a/rustig_koppie_puresky 
### Car Model
Generic Sport Sedan (midsize) 3D Model by magildo_bernardes
https://free3d.com/3d-model/generic-sport-sedan-midsize-27472.html 
### Pedestrian Model/Movement
Y bot “Walking” and “Stop Walking” from Mixamo
https://www.mixamo.com/ 
### Road Texture
Asphalt 01 by Charlotte Baglioni
https://polyhaven.com/a/asphalt_01
## Notes on Animation
### Scale
The environment was scaled to be a 1:1 ratio from the real world in Blender. This measurement is based on the width of the 2-lane road from sidewalk to sidewalk which in the Cross Cultural Walking project was measured to be 30 feet wide.
![AnimationScale](https://github.com/FAR-Lab/XC_CarPed_VideoGen/assets/78111993/24b8ab5e-d621-4746-a97c-65d53ad86aa5) \
The car model in the simulation is approximately 190.8 in which is on the longer side but still a reasonable length based on a sample of sedan models from four different brands: \
190.2 in https://www.kia.com/us/en/vehicles/stinger/2022/specs.html \
184.0 in https://automobiles.honda.com/civic-sedan/specs-features-trim-comparison \
167.9 in https://www.toyota.com/gr86/features/mpg_other_price/6255/6254 \
191.8 in https://www.edmunds.com/ford/fusion/2019/sedan/st-401757613/features-specs/
### Cameras
The car camera (and scene cameras) is set to 50mm and the pedestrian camera is set to 80mm. I set the pedestrian camera based on these videos: \
https://www.dropbox.com/s/3sc8jklqjj2k18a/noEHMI_NY_constant.mp4?dl=0 \
https://www.dropbox.com/s/2tf0acno7jovdfn/noEHMI_Y.mp4?dl=0 \
The cameras were set in order to minimize warping so the camera view looks as close to life as possible such that a participant could estimate depth through the video.
### Timing and Frames
The car starts at a constant speed of 30mph (around 48.28kmh) as measured from the distance between the location at frame 1 and frame 36 (66 feet over 1.5 seconds).
At 72 Frames (3 seconds) the pedestrian reaches the edge of the sidewalk and settles both feet onto the ground (see photo):
![72frames](https://github.com/FAR-Lab/XC_CarPed_VideoGen/assets/78111993/7c6e1956-18d7-4a53-ab0b-8aee5970fcc0) \
At the 0 second scenario, the car’s front bumper meets the pedestrian’s centerline path (represented by the orange dot below the pedestrian’s right foot above). The car will be further away from the pedestrian in the 2 to 5 second time scenarios, but the pedestrian always reaches the sidewalk at 3 seconds (72 frames).
Over-the-shoulder Scenarios
Scenario 2 and 3 require the camera to look through the pedestrian in order to see the car. This means that for rendering, the pedestrian needs to be hidden from the pedestrian camera but it needs to be made visible again when rendering the driver and scene perspectives.
Camera Animations
The cameras are also animated and must be modified when each time iteration is created for a scenario.

## Colors and Design Choices
### Car
The car is a basic sports car model. I picked one that didn’t stand out as exceptionally expensive as alternatives were lamborghinis, ferraris, and muscle cars. This model is titled “generic sports sudan.” We chose a dark gray to avoid bias associated with different colors of cars. We also needed it to stand out from the background and be visible to the pedestrian and therefore did not make it white. 
Pedestrian
We used the Y Bot from Mixamo. We also made the model blank white to avoid gender associations with the pedestrian, as the original Y Bot model is blue.
### Road
There are minimal markings on the road in order to ensure that the car and pedestrian are meeting at an ambiguous intersection. There are no signs, no crosswalks, etc., and therefore no right of way is implied. The road is modeled to mimic an urban, 4-way intersection.
### Environment
The skybox was chosen in order to provide no association with a location that could have been indicated by a ground like a parking lot or anything with foliage, buildings, etc. This is also why the buildings are blank, and this should keep the environment sterile
