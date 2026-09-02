# Siril scripts

A set of utility scripts for stacking deep sky images with [Siril](https://siril.org/), taken with a color camera.

More info about using scripts from [official siril tutorial](https://siril.org/tutorials/tuto-scripts/).

All the steps can be done manually. Scripts are a convenience.

## Scripts

The scripts expect the following folder structure

``` 
[project home]
|
+- /lights
+- /biases
+- /flats
+- /darks
``` 

### Script numbers refer to the expected order of execution.

0. Convert calibration images to `.ser`
1. preprocess calibration images
2. convert light images to `.ser`
3. calibrate and align lights
4. stack final image as `.fit`

### Special scripts

##### 01234_Convert_and_Stack_All.ssf 
Does what it says. Does all steps from 0 to 4 in one go. If a step fails, you can fix the issue and 
continue with the remaining steps using individual scripts.

##### 0123_Prepare_all_files_wo_stacking.ssf
Does what it says. Does all steps from 0 to 3 in one go. Allows you to do the final stack manually.

##### 3b_Process_Lights_wo_Flats.ssf
If you haven't taken flats, this will replace step 3. Steps 0 and 1 will give errors, because flats 
are missing, but it doesn't matter.

### *Light* exposures
The actual images of the target
- Unless you know better, use ISO 1600

### Calibration Shots

#### Bias
Black images with camera with cap on, at minimum exposure time
- [ ] 50 - 100 à
- Temperature: (Same as lights)
- ISO: Same as lights
- 1/4000 s  or shortest possible

#### Dark
Black images with cap on at the same exposure settings and temperature as the actual *light* exposures
- [ ] 20 - 50 à 
- Temperature: Same as lights
- Time: Same ...
- ISO: Same ...

#### Flat
Light gray images of a uniformly lit, white target, such as a white t-shirt. Use the telescope in the same configuration as used for *light* exposures
- [ ] 20 - 50 à
- ISO: Same
- 2/3 exposure through the same scope/lens, aperture and focus
