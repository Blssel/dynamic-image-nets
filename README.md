# Dynamic Image Networks for Action Recognition


## License
The analysis work performed with the program(s) must be non-proprietary work. Licensee and its contract users must be or be affiliated with an academic facility. Licensee may additionally permit individuals who are students at such academic facility to access and use the program(s). Such students will be considered contract users of licensee. The program(s) may not be used for commercial competitive analysis (such as benchmarking) or for any commercial activity, including consulting.



## Installation
1. Clone the Dynamic Image Net repository:

    ```Shell
    git clone --recursive  https://github.com/hbilen/dynamic-image-nets
    ```
    
2. Compile matconvnet toolbox: (see [http://www.vlfeat.org/matconvnet/install/](http://www.vlfeat.org/matconvnet/install/)

3. Download your dataset : (e.g. UCF101 from [http://crcv.ucf.edu/data/UCF101.php](http://crcv.ucf.edu/data/UCF101.php))

4. Convert videos to frames, resize them to 256x256 and store them in such a directory structure:
    
    ```Shell
    data/UCF101/ucfTrainTestlist/
    ├── classIndFixed.txt
    ├── classInd.txt
    ├── testlist01.txt
    ├── testlist02.txt
    ├── testlist03.txt
    ├── trainlist01.txt
    ├── trainlist02.txt
    └── trainlist03.txt
    data/UCF101/frames/
    ├── v_ApplyEyeMakeup_g01_c01
    │   ├── 00001.jpg
    │   ├── 00002.jpg
    │   ├── 00003.jpg
    │   ├── 00004.jpg
    │   ├── 00005.jpg
    ```

## Compute and Visualise Approximate Dynamic Images
1. If you want to compute approximate dynamic images, try
  ```matlab
  di = compute_approximate_dynamic_images(images) ;
  ```

2. If you want to visualise approximate dynamic images, try
  ```matlab
  visualize_approximate_dynamic_images(images)
  ```

## Train 
1. Write your own `cnn_dataset_setup_data` or `cnn_ucf101_setup_data` to build your database (imdb):
2. Now you can train your model by running 

    ```matlab
    [net, info] = cnn_dicnn(opts)
    ```
## Evaluation

1. Download a trained model from the following link:
https://drive.google.com/open?id=0B0evBVYO74MEa29kZDQ2UlNDS1k

2. Set the appropriate opts parameters (e.g. opts.modelPath)

3. Run info = cnn_dicnn_evaluate(opts)


## Citing Dynamic Image Networks

If you find the code useful, please cite:

        @inproceedings{Bilen2016a,
          author    = "Bilen, H. and Fernando, B. and Gavves, E. and Vedaldi, A. and Gould, S.",
          title     = "Dynamic Image Networks for Action Recognition",
          booktitle = "CVPR",
          year      = "2016"
        }
 
