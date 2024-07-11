## Data Preparation 
You need to download KITTI dataset [here](http://www.cvlibs.net/datasets/kitti/eval_object.php?obj_benchmark=3d). Download left images, calibration files and labels.
Download the split files [here](https://drive.google.com/drive/folders/1YLtptqspOFw08QG2MsxewDT9tjF2O45g?usp=sharing) and place them at ${YOUR_KITTI_DIR}/SPLIT/ImageSets.
Your data folder should look like this:

   ```
   ${YOUR_KITTI_DIR}
   ├── training
      ├── calib
          ├── xxxxxx.txt (Camera parameters for image xxxxxx)
      ├── image_2
          ├── xxxxxx.png (image xxxxxx)
      ├── label_2
          ├── xxxxxx.txt (object labels for image xxxxxx)
      ├── ImageSets
         ├── train.txt
         ├── val.txt   
         ├── trainval.txt        
   ├── testing
      ├── calib
          ├── xxxxxx.txt (Camera parameters for image xxxxxx)
      ├── image_2
          ├── xxxxxx.png (image xxxxxx)
      ├── ImageSets
         ├── test.txt
   ```

## Download pre-trained model
You need to download the pre-trained checkpoints [here](https://drive.google.com/file/d/1JsVzw7HMfchxOXoXgvWG1I_bPRD1ierE/view?usp=sharing) in order to use Ego-Net. Unzip it to ${YOUR_MODEL_DIR}.

## Compile the official evaluator
Go to the folder storing the source code
```bash
cd ${EgoNet_DIR}/tools/kitti-eval 
```
Compile the source code
```bash
g++ -o evaluate_object_3d_offline evaluate_object_3d_offline.cpp -O3
```

## Download the input bounding boxes
Download the [resources folder](https://drive.google.com/drive/folders/1atfXLmsLFG6XEtNnwZuEYLydKqjr7Icf?usp=sharing) and unzip its contents. Place the resource folder at ${EgoNet_DIR}/resources


## Environment
You need to create an environment that meets the following dependencies. 
The versions included in the parenthesis are **tested**. Other versions may also work but are **not tested**.

- Python (3.7.9)
- Numpy (1.19.2)
- PyTorch (1.6.0, GPU required)
- Scipy (1.5.2)
- Matplotlib (3.3.4)
- OpenCV (3.4.2)
- pyyaml (5.4.1)

For more details of my tested local environment, refer to [spec-list.txt](https://github.com/Nicholasli1995/EgoNet/blob/master/docs/spec-list.txt). 
The recommended environment manager is [Anaconda](https://www.anaconda.com/), which can create an environment using this provided spec-list. 
For debugging using an IDE, I personally use and recommend Spyder 4.2 which you can get by
```bash
conda install spyder
```
