# Raspberry Pi Color Detection Project
    This project uses the Raspberry Pi and the Picamera2 module to detect colors in images captured by the camera.

# Prerequisites
    Raspberry Pi with Picamera2 module
    Python 3
    OpenCV library
# Setup
    Install the required libraries by running the following commands:
    Edit
    Full Screen
    Copy code
    sudo apt update
    sudo apt install python3-picamera2 python3-opencv
    Clone the project repository:
    Edit
    Full Screen
    Copy code
    git clone https://github.com/yourusername/color-detection.git
    Usage
    Navigate to the project directory:
    Edit
    Full Screen
    Copy code
    cd color-detection
    Run the color detection script:
    Edit
    Full Screen
    Copy code
    python3 color_detection.py
# Code
```python
from picamera2 import Picamera2, MappedArray, Preview
    import cv2
    import numpy as np
    import time
    
    cam = Picamera2()
    
    cam.framerate = 16 
    config = cam.create_preview_configuration({"format" : "XRGB8888"})
    cam.configure(config)
    cv2.startWindowThread()
    cam.start()
    cv2.namedWindow("Trackbars")
    def holder(x):
        pass
    cv2.createTrackbar("B" , "Trackbars" , 0 , 255 , holder)
    cv2.createTrackbar("G" , "Trackbars" , 0 , 255 , holder)
    cv2.createTrackbar("R" , "Trackbars" , 0 , 255 , holder)
    
    
    def colorTuning():
        B = cv2.getTrackbarPos("B" , "Trackbars")
        G = cv2.getTrackbarPos("G" , "Trackbars")
        R = cv2.getTrackbarPos("R" , "Trackbars")
        color = np.uint8([[[B , G , R]]])
        hsvC = cv2.cvtColor(color , cv2.COLOR_BGR2HSV)
        lowLim = np.uint8([hsvC[0][0][0]-10,100,100])
        upLim = np.uint8([hsvC[0][0][0]+10,255,255])
        return lowLim , upLim
    
    def findColor(frame):
        hsv_roi = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
        lowLim , upLim = colorTuning()
        print(lowLim , upLim)
        mask_1 = cv2.inRange(hsv_roi , lowLim , upLim)
        mask_2 = cv2.bitwise_and(frame , frame , mask=mask_1)
        cv2.imshow("mask1" , mask_1)
        cv2.imshow("mask2" , mask_2)
        mask = mask_1  
        kern_dilate = np.ones((8,8),np.uint8) 
        kern_erode = np.ones((3,3),np.uint8) 
        mask= cv2.erode(mask,kern_erode) #Eroding 
        mask=cv2.dilate(mask,kern_dilate) #Dilating 
        return mask 
        
    def find_blob(blob): #returns the red colored circle 
        largest_contour=0 
        cont_index=0 
        contours, _ =cv2.findContours(blob, cv2.RETR_CCOMP, cv2.CHAIN_APPROX_SIMPLE) 
        for idx, contour in enumerate(contours): 
            area=cv2.contourArea(contour) 
            if (area >largest_contour): 
                largest_contour=area 
                cont_index=idx 
        r=(0,0,2,2) 
        if len(contours) > 0: 
            r = cv2.boundingRect(contours[cont_index]) 
        return r,largest_contour 
    
            
                
    def main():
        sT = time.monotonic()
        while time.monotonic() - sT < 180:
            time.sleep(0.001)
            frame = cam.capture_array("main")
            mask = findColor(frame)
            loc , area = find_blob(mask)
            x,y,w,h = loc
            print(x , y , w , h , area)
            if area > 5000:
                print("FOUND")         
                cv2.rectangle(frame , (x,y), (x+y , y+h) , (0 , 255 , 0) , 3)
            cv2.imshow("mask" , frame)
        cam.stop_preview()
        cv2.destroyAllWindows()
    main()
```
This code captures frames from the camera, converts them to HSV color space, applies a color range filter to detect blue objects, and displays the original frame, the mask, and the detected blue objects.

You can modify the lower_blue and upper_blue variables to detect different colors.

Contributing
Pull requests are welcome! If you have any suggestions or improvements, please open an issue or submit a pull request.

License
This project is licensed under the MIT License.

This is a basic writeup for a Raspberry Pi project that uses the Picamera2 module to detect colors in images. You can modify the code to detect different colors or improve the color detection algorithm.

I hope this helps! Let me know if you have any questions.

