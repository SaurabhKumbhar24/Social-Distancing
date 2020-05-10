# Social-Distancing
Object Detection , Human Detection using Tensorflow Object Detection API

STEPS : 
1. Object Detection using TensorFlow Object Detection API
2. Convert Video To Images
3. Visualize Objects in Image
4. Delete Boxes of other Objects except for Human
5. Visualize Humans
6. Calculate distance between Human Objects using Euler's distance formula between center points of both objects
7. Change color of human objects which are breaking rules of social distancing.
8. Visualize The Output Image
9. Convert Images to Video

Input Dataset : https://www.robots.ox.ac.uk/ActiveVision/Research/Projects/2009bbenfold_headpose/Datasets/TownCentreXVID.avi

Outputs :

<h3>Object Detection</h3>

<img src="objectDetection.png" alt="Object Detection Image">

<h3>Social Distancing</h3>

<img src="SocialDistancing.png" alt="Social Distancing Image">

Functions

1. load_model
2. run_inference_for_single_image
3. VideoToFrames
4. VisualizeImage
5. DisplayImage
6. FramesToVideo
7. getSingleHumanCoordinates
8. getDistance
9. VisualizeSocialDistancing
10. VisualizeHumanImage
11. FramesToStore
12. SocialDistanceToVideo

**Functions Explaination**:

1. **load_model** <br> 

    Args  :<br>
            model_name : Passing Tensorflow model Name<br>
    Returns : <br>
            Trained model<br>

2. **run_inference_for_single_image** <br>

    Args :<br>
          model : Passing loaded Model<br>
          image : Image to be processed<br>
    
    Returns : <br>
              Output Dictionary which contains<br>
              1. Detected Boxes Dimensions<br>
              2. Detected Classes index <br>
                 eg [1,2,3] 1 is for Person<br>
              3. Detected Scores which is <br>
                 list of scores for each detection<br>
              4. Number of Detected Objects<br>

3.  **VideoToFrames** <br>

    Args : <br>
          VideoFileName : Pass name of video file with ext <br>
          Path : Pass Path where to store Frames<br>
    
    Returns:<br>
            Creates Frames From video and store it in path<br>

4.  **VisualizeImage**<br>
    
    Args: <br>
          ImageName : Pass name of Image to be Visualized<br>
          Path : path to the image<br>
          
    Returns:<br>
            Image with object detected boxes drawn on it<br>

5. **DisplayImage**<br>

    Args:<br>
          Image : numpy array Image<br>
          
    Output:<br>
            Prints image to output<br>

6. **FramesToVideo**<br>

    Args :<br>
          no_of_frames : Number of frames to be converted to<br>
                         Video<br>
                         
    Output :<br>
            The Video with 15 fps created using 0-n frames<br>

7. **getSingleHumanCoordinates**<br>

    Args :<br>
          Boxes : List of Detected boxes coordinates<br>
          Image : Image <br>
          position: position of object from list of <br>
                    coordinates<br>
                    
    Returns : <br>
            Left right bottom top coordinates of object<br>

8. **getDistance**<br>

    Args :<br>
          x1,x2,y1,y2 : Coordinates to find Distance<br>
          
    Returns :<br>
          Distance between (x1,y1) and (x2,y2)<br>

9. **VisualizeSocialDistancing**<br>

    Args :<br>
          Boxes : List of Coordinates of all objects<br>
          Image : Image To Visualize<br>
          
    Output :<br>
          Draws red color on boxes near to each other<br>

10. **VisualizeHumanImage**<br>

    Args :<br>
          ImageName : Name of Image File to Visualize<br>
          Path : path to Image<br>
          
    Returns :<br>
          Image with Boxes drawen<br>

11. **FramesToStore**<br>

    Args : <br>
          tillFrame : Pass number of Frames to Visualize<br>
          
    Output :<br>
            Stores Visualized Image To SocialDistancingFrames<br>
            Folder<br>

12. **SocialDistanceToVideo**<br>

    Args :<br>
          no_of_frames : Pass number of Frames<br>
          
    Outputs :<br>
            Video till no_of_frames of 15fps<br>
