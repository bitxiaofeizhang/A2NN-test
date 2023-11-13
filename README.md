# A2NN-test
  The project implement the CNN, A2NN, Q-A2NN for optical remote sensing classification.

    test_code: 
      the test code for implementing the CNN, A2NN, Q-A2NN for optical remote sensing classification.
    hardware:
      adder_PE_code:
        the code of the adder kernel processing energy
      para_rom:
        the parameter files for on-chip ROM initialization when deploying QA2NN on FPGA
      vedio demo:
        demonstration of the entire process of deploying QA2NN quantized in 4bit on FPGA.

***************************************************************************************

How to run the ./test_code:

  1. First of all, you need to build a cuda computing environment for the adder kernel. We provide two methods:

  · The first method:
  
  You can build the environment by youself as follow steps:
      
  1) Environment Requirements：python 3.8, pytorch 1.8.2, CUDA 11.1
  2) modify PyTorch before launch (for solving compiling issue):

     Change lines:57-64 in anaconda3/lib/python3.8/site-packages/torch/include/THC/THCTensor.hpp from:

         #include <THC/generic/THCTensor.hpp>
         #include <THC/THCGenerateAllTypes.h>

         #include <THC/generic/THCTensor.hpp>
         #include <THC/THCGenerateBoolType.h>

         #include <THC/generic/THCTensor.hpp>
         #include <THC/THCGenerateBFloat16Type.h>
        

  · The second method:
  
    
    
      
  You can find the CNN, A2NN, and QA2NN versions of the vgg11 pre-trained model from the links we provide, and put these pre-trained models into the test_code folder.
     
     链接：https://pan.baidu.com/s/13vMXwFpoJImSbwjP9BZWCQ?pwd=mvov 提取码：mvov

  Download UC Merced Land Use Dataset and modify the image file path in the /data_process/UC_test_0.2.txt file according to the storage location of the UC dataset.
  
    http://weegee.vision.ucmerced.edu/datasets/landuse.html
     
 After above steps, you can run the test_code:

    python test.py
     
  =>Notes: The file size of QA2NN does not reflect the real resource overhead when deploying the inference phase of the QA2NN. We additionally provide the parameter files for on-chip ROM initialization when deploying QA2NN on FPGA.
    
