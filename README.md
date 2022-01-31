# w251 HW 3
### Files and Folders
#### Each folder represents a container. MQTT is used twice.
- `mqtt`: contains the Dockerfile and .yaml files for running the MQTT broker; same deployments used locally and in the cloud
- `camera`: contains the Dockerfile, .yaml file, and cam.py file for connecting to the USB camera, detecting a face, capturing the image, and publishing the image to the local MQTT listener
- `listener`: contains the Dockerfile, .yaml file, and listener.py file for running the MQTT listener that receives the image (as a bytestring) from the face-detector deployment and publishes it to the remote MQTT broker running on an EC2 in AWS
- `aws_listener`: contains the Dockerfile, .yaml file, and im_upload.py file for receiving the image from the remote MQTT broker and pushing it to the S3 bucket 
