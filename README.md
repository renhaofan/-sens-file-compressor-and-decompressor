# Introduction
This is a copy of this [repo](https://github.com/ScanNet/ScanNet/tree/master/SensReader/python) with
extra environment settings for convience beacuse of python2.7 abandoned.

```
conda env create -f environment.yaml
```


# sens-file-generatorNcompressor

http://graphics.stanford.edu/projects/bundlefusion/
this script(builder.py) compress color, depth, (pose), camera parameter to .sens file

to do that you can test your data generation is right for bundlefusion program.

please put depth image as 16bit image(which elt. has value in mm)
not relative disparity, or something like retrived from opencv stereovision block matcher
(I mean, this only work with absolute value png)

## reader.py & SensorData.py
Usage:
```
python reader.py --filename [.sens file to export data from] --output_path [output directory to export data to]
Options:
--export_depth_images: export all depth frames as 16-bit pngs (depth shift 1000) 
--export_color_images: export all color frames as 8-bit rgb jpgs
--export_poses: export all camera poses (4x4 matrix, camera to world)
--export_intrinsics: export camera intrinsics (4x4 matrix)
```
Element in depth_images divideda by 1000 to get a depth in meters.
