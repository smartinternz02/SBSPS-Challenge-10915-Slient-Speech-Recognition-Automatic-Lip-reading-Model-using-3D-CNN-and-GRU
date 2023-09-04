# SBSPS-Challenge-10915-Slient-Speech-Recognition-Automatic-Lip-reading-Model-using-3D-CNN-and-GRU
Slient Speech Recognition : Automatic Lip reading Model using 3D CNN and GRU


We have broke this priject into two parts 

1.Detecting the points on the lips.

2.Running this points through a Conv Network to map it to the corresponding word.

1)Detecting the points on the lips:
  ->For Landmarking the points on the face  we used  Dlib's facial landmark detector.
  
  ->This detector can accurately mark 81 points on the face and we need only the 19 points 
   which will be marked on the lips.
   
  ->This detected points will be normalized with brespect to the coordinates of the point number 48 ie first point if the lip 
  
  ->After marking the 19 ponits we have converted the detected land marks into tensors 


=========================================================================================================================================
  
  
2)Running this points through a Conv Network to map it to the corresponding word

 ->Now take this tensors and load it into data loaders 
 
 ->The size of the tensor will be [2,19,59] 
 
   where 2 is the x and y coordinates 
   
         19 is the no of points marked on thr lips
         
         59 is the total no of frames
         
 class/words to be detected
 
 1 pleased
 
 2 ok
 
 3 next
 
 4 previous
 
 5 back
 
 6 exit
 
 7 wait
 
 8 start
 
 9 stop
 
 10 pause
 
The Model 1 contain's the first part of the project where the lip landmarks are obtained the are converted into tensors

Model 2 takes data from dataset folder and identifies the lip landmarks converts them into tensor and then load it into the data loader
and runs it through a simple CNN network and training loop
