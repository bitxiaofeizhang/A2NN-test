# A2NN-test
  The project implement the CNN, A2NN, Q-A2NN for optiacal remote sensing classification.

    test code: 
      the test code for implementing the CNN, A2NN, Q-A2NN for optiacal remote sensing classification.
    hardware:
      d:
        fd
      vedio demo:
        ds

How to run the test code:
  1. You need to follow the link: https://github.com/GATECH-EIC/ShiftAddNet#compile-adder-cuda-kernal to Compile Adder Cuda Kernal.
  2. You can find the CNN, A2NN, and QA2NN versions of the vgg11 pre-trained model from the links we provide:
     链接：https://pan.baidu.com/s/13vMXwFpoJImSbwjP9BZWCQ?pwd=mvov 提取码：mvov
     Put these pre-trained models into the test folder.
  3. Download UC Merced Land Use Dataset: http://weegee.vision.ucmerced.edu/datasets/landuse.html
     Modify the image file path in the /data_process/UC_test_0.2.txt file according to the storage location of the UC dataset.
  =>Notes: The file size of QA2NN does not reflect the true resource overhead when deploying the inference phase of the QA2NN. We additionally provide the parameter files for on-chip ROM initialization when deploying QA2NN on FPGA.
    
