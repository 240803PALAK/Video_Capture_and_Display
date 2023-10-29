# Video_Capture_and_Display
It play the video which you have recorded.


    import cv2 as cv
    import numpy as np
    import time
    
    capture=cv.VideoCapture(0)
    
    fourcc=cv.VideoWriter_fourcc(*'XVID')
    out=cv.VideoWriter('Video.mp4',fourcc,20.0,(640,480))
    
    while (capture.isOpened()):
        ret,frame=capture.read()
        if ret==True:
            out.write(frame)
            cv.imshow('output',frame)
        
            # Enter 'd' to off the video recording
            if cv.waitKey(1)& 0XFF==ord('d'):
                break
        else:
            break 
            
    capture.release()
    out.release()
    cv.destroyAllWindows()
    
    time.sleep(3)
    
    # code to display
    display=cv.VideoCapture(r"Video.mp4")
    while True:
        isTrue,frame=display.read()
        cv.imshow('Video',frame)
        if cv.waitKey(20) & 0XFF==ord('d'):
            break
    capture.release()
    cv.destroyAllWindows()
