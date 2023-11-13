# A2NN-test
  The project implement the CNN, A2NN, Q-A2NN for optical remote sensing classification.

    adder_cuda:
      the cuda computing environment for the adder kernel.
    test_code: 
      the test code for implementing the CNN, A2NN, Q-A2NN for optical remote sensing classification.
    hardware:
      adder_PE_code:
        the code of the adder kernel processing energy.
      para_rom:
        the parameter files for on-chip ROM initialization when deploying QA2NN on FPGA.
      result_count:
        output result of deploying QA2NN quantized in 4bit on FPGA.
    vedio_demo:
        demonstration of the entire process of deploying QA2NN quantized in 4bit on FPGA.

***************************************************************************************

How to run the ./test_code:

First of all, you need to build a cuda computing environment for the adder kernel. We provide two methods:

   · The first method:
  
   You can build the environment by youself as follow steps:
      
   (1) Environment Requirements：python 3.8, pytorch 1.8.2, CUDA 11.1
   
   (2) modify PyTorch before launch (for solving compiling issue):
   
   Change lines:57-64 in anaconda3/lib/python3.8/site-packages/torch/include/THC/THCTensor.hpp from:

          #include <THC/generic/THCTensor.hpp>
          #include <THC/THCGenerateAllTypes.h>

          #include <THC/generic/THCTensor.hpp>
          #include <THC/THCGenerateBoolType.h>

          #include <THC/generic/THCTensor.hpp>
          #include <THC/THCGenerateBFloat16Type.h>

   to:

          #include <THC/generic/THCTensor.h>
          #include <THC/THCGenerateAllTypes.h>

          #include <THC/generic/THCTensor.h>
          #include <THC/THCGenerateBoolType.h>

          #include <THC/generic/THCTensor.h>
          #include <THC/THCGenerateBFloat16Type.h>

   (3) compile the adder_cuda:  

         cd adder_cuda
         python setup.py install --user 
     
   · The second method:
  
   We provide configured virtual environments. You only need to download and unzip it, and you can run the test code directly in this environment：
   
      链接：https://pan.baidu.com/s/1OFKVO-Q5sfJlCNCMygeUDA?pwd=co8a 提取码：co8a 
    
  Secondly, you can find the CNN, A2NN, and QA2NN versions of the vgg11 pre-trained model from the links we provide, and put these pre-trained models into the test_code folder.
     
     链接：https://pan.baidu.com/s/1kPuayjwvg---K6XGuJpRjw?pwd=7yqn 提取码：7yqn 

  Thirdly, download UC Merced Land Use Dataset and modify the image file path in the /data_process/UC_test_0.2.txt file according to the storage location of the UC dataset.
  
    http://weegee.vision.ucmerced.edu/datasets/landuse.html
     
 After above steps, you can run the test_code:

    python test.py

  ***************************************************************************************

  
     
  =>Notes: The file size of QA2NN does not reflect the real resource overhead when deploying the inference phase of the QA2NN. We additionally provide the parameter files for on-chip ROM initialization when deploying QA2NN on FPGA.
    
