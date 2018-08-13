# Video-object-segmentation-paper-list
This page is for organizing the contents of Video Object Segmentation.


>ICCV 2015
### Fully connected object proposals for video segmentation
  1) Graph-based object segmentation algorithm.

>CVPR 2016
### A Benchmark Dataset and Evaluation Methodology for Video Object Segmentation (DAVIS 2016 dataset)
  - Paper : https://graphics.ethz.ch/~perazzif/davis/files/davis.pdf
  - Project repository : https://github.com/fperazzi/davis-2017 (2016, 2017)
  1) To evaluate three evaluation metric, one can link the veido segmentation result *.png with the project.
  2) DAVIS challenge evaluation example 

Input example :

python eval.py -i ../../../OSVOS-PyTorch/models/Results/ -o result.yaml --year 2016 --single-object --phase val

Evaluation example :
![screenshot from 2018-07-25 21-51-31](https://user-images.githubusercontent.com/41351363/43202009-2c29ceb6-9055-11e8-912b-b53569804a36.png)

See DAVIS Git repo for detail.


### Video segmentation via object flow (OFL)
  - Paper : http://files.is.tue.mpg.de/black/papers/TsaiCVPR2016.pdf
  - Project repository : https://github.com/wasidennis/ObjectFlow

### Bilateral space video segmentation



>BMVC 2017

### Online Adaptation of Convolutional Neural Networks for Video Object Segmentation
  - Paper : https://arxiv.org/pdf/1706.09364.pdf
  - Project repository : +https://www.vision.rwth-aachen.de/software/OnAVOS


>ICCV 2017

### SegFlow: Joint Learning for Video Object Segmentation and Optical Flow
  - Paper : https://arxiv.org/pdf/1709.06750.pdf
  - Project repository : https://github.com/JingchunCheng/SegFlow
  
  1) Using FlowNet for temporal information and FCN for segmentation in bidirectional way.
  2) Iterative training scheme

  

### Pixel-Level Matching for Video Object Segmentation using Convolutional Neural Networks
  - Paper : https://arxiv.org/pdf/1708.05137.pdf
  
  1) Using two stream network (i.e., Search and Query)
  2) Network consists of three parts: encoding, pixel-level similarity FC layer and decoding.
  3) Compressers are used for memory efficiency. 
  
  
>CVPR 2017
### One-Shot Video Object Segmentation (OSVOS)

  - Paper : http://openaccess.thecvf.com/content_cvpr_2017/papers/Caelles_One-Shot_Video_Object_CVPR_2017_paper.pdf
  - Project repository : https://github.com/kmaninis/OSVOS-PyTorch
  
  1) Adapt the CNN to a particular object instance given a single annotated image
  2) Segmenting each frame independently
  3) Can work at various points of the trade-off between speed and accuracy
  4) Improve the performance by a significant margin (79.8%)
  5) Propose two network streams for segmentation and segmentation result refinement
  6) Muilt-training step. (e.g., Base Network using pretrained weights, Parent Network using DAVIS dataset, Test Network using the frame 1)
  
### Online Video Object Segmentation via Convolutional Trident Network
  - Paper : http://openaccess.thecvf.com/content_cvpr_2017/papers/Jang_Online_Video_Object_CVPR_2017_paper.pdf
  - Project repository : https://github.com/wdjang/CTN
  
  1) Trident Network : separative(sgementation) / definite foreground / definite background
  2) Encoder - Deconder structure : 1-encoder stream / 3(tri)-decoder stream
  
### Learning Video Object Segmentation from Static Images (MaskTrack)
  - Paper : https://graphics.ethz.ch/~perazzif/masktrack/files/masktrack.pdf  
  - Project repository : https://graphics.ethz.ch/~perazzif/masktrack/index.html
  
  1) MaskTrack : use only one segmentation network (Deeplabv2-VGG16)
  2) Training time : Input -> RGB + synthesize training mask (video whole frames are not required)
     [Offline] affine transformations and non-rigid deformations are used for augmentation ~ 10^4
     [Online] Using first frame with ground turth is exploited ~ 10^3
  3) Test time : Input -> RGB + t-1 segmentation mask
  4) Optical flow and CRF are optionally used
  
### Video Propagation Networks (VPN)
  - Paper : https://varunjampani.github.io/papers/jampani17_VPN.pdf
  - Project repository : https://github.com/varunjampani/video_prop_networks
  
  1) Using bilateral filter networks 
  2) Online propagation : The method need no future frame (real-time, casual)
 
 ### Learning to segment instance in videos with spatial propagation network (Workshop Paper)
   - Paper : https://davischallenge.org/challenge2017/papers/DAVIS-Challenge-6th-Team.pdf
   - Project repository : https://github.com/JingchunCheng/Seg-with-SPN

>CVPR 2018
  ### Reinforcement Cutting-Agent Learning for Video Object Segmentation
  
  - Paper : http://openaccess.thecvf.com/content_cvpr_2018/papers/Han_Reinforcement_Cutting-Agent_Learning_CVPR_2018_paper.pdf
  
  ### Fast Video Object Segmentation by Reference-Guided Mask Propagation (RGMP)
  
  - Paper : http://www.eecs.harvard.edu/~kalyans/research/videosegmentation/FastVideoSegmentation_CVPR18.pdf
  - Project repository : https://github.com/seoungwugoh/RGMP
  
  1) Siamese encoder-decoder network for one-shot VOS
  2) The network works without any online-learning or post-processing
  3) Using two-stage scheme that pre-trains the network on synthetically generated image data & fine-tunes it on vedio data
  4) In fune-tuning step, they exploit BPTT (i.e., RNN structure) 
  5) Training time is so long (totally 5 days)
  
  
  
  ### Fast and Accurate Online Video Object Segmentation via Tracking Parts
  
  - Paper : http://faculty.ucmerced.edu/mhyang/papers/cvpr2018_video_segmentation.pdf

  ### Efficient Video Object Segmentation via Network Modulation
  
  - Paper : https://arxiv.org/pdf/1802.01218.pdf
  - Project repository : https://github.com/linjieyangsc/video_seg
  
  1) Motivated by conditional batch normalization
  2) y = r
  3) Feature maps are modulated by visual / spatial modulator
  4) Visual modulator : [input] first frame image [output] scale parameters
     Spatial modulator : [input] t-1 frame image [output] bias parameters

  ### Motion-Guided Cascaded Refinement Network for Video Object Segmentation
  
  - Paper : http://openaccess.thecvf.com/content_cvpr_2018/CameraReady/0391.pdf
  
  1) Optical flow-based  + Active contour (Level-set) + CRN
                                                                                                                                                                     
  
  ### MoNet: Deep Motion Exploitation for Video Object Segmentation
  
  - Paper : http://openaccess.thecvf.com/content_cvpr_2018/papers/Xiao_MoNet_Deep_Motion_CVPR_2018_paper.pdf
  
  1) Non-casual VOS system (see Figure 2)
  2) Using optical flow for robustness (Flownet 2.0 is used)
  3) For segmentation, DeepLab is utilized
  4) Distance Transform layer using FastMBD algorithm 
  5) MoNet consists of a segmentation stream and an optical flow stream.


>TPAMI

  ### Video Object Segmentation Without Temporal Information (2018, Extended version of OSVOS)
  - Paper : https://arxiv.org/pdf/1709.06031.pdf

>arXiv

  ### Lucid Data Dreaming
  - Paper : https://arxiv.org/pdf/1703.09554.pdf
  - Project repository : https://github.com/ankhoreva/LucidDataDreaming

