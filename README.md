# FootBall Analysis CV Project
## Project Overview

The FootBall Analysis CV Project leverages advanced computer vision techniques to analyze football match videos. This project encompasses several functionalities, including object detection, tracking, team assignment, and ball possession analysis. The core of the project is built using Python and powerful libraries such as YOLO for object detection and Supervision for tracking.
Features

    Object Detection: Detect players, referees, and the ball in football match videos using the YOLOv8 model.
    Tracking: Track detected objects across video frames with ByteTrack.
    Team Assignment: Assign detected players to their respective teams using k-means clustering.
    Ball Possession: Determine which player and team have possession of the ball at any given time.
    Annotations: Visualize the results with annotated video frames showing player, ball, and referee positions, along with ball possession statistics.

Detailed Description
### bbox_utils.py

This module provides utility functions for handling bounding boxes:

    get_center_of_bbox(bbox): Returns the center coordinates of a bounding box.
    get_bbox_width(bbox): Calculates the width of a bounding box.
    measure_distance(p1, p2): Measures the Euclidean distance between two points.
    get_foot_position(bbox): Returns the position of the bottom center of a bounding box.

### video_utils.py

This module includes functions for reading and saving videos:

    read_video(video_path): Reads frames from a video file.
    save_video(output_video_frames, output_video_path): Saves frames to a video file.

### tracker.py

This module includes the Tracker class for object detection and tracking:

    init(model_path): Initializes the tracker with a YOLO model.
    detect_frames(frames): Detects objects in video frames using the YOLO model.
    get_object_tracks(frames, read_from_stub=False, stub_path=None): Tracks objects across video frames.
    draw_annotations(video_frames, tracks, team_ball_control): Draws annotations on video frames.

### team_assigner.py

This module includes the TeamAssigner class for assigning players to teams:

    assign_team_color(frame, player_detections): Assigns team colors to players based on clustering.
    get_player_team(frame, player_bbox, player_id): Determines the team of a player based on their color.

### main.py

The main script orchestrates the entire pipeline:

    Reads the input video.
    Detects and tracks objects.
    Assigns players to teams.
    Determines ball possession.
    Annotates and saves the output video.

### yolo_inference.py

This script performs inference using the YOLO model on a video file:

    Loads the YOLO model.
    Runs the model on an input video and prints detection results.
