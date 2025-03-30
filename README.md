# Foundation_Pose
In this tutorial, we cover the setup, installation, and execution of the Foundation Pose Model in SinRef-6D for 6D pose estimation using an RGB-only camera. This step-by-step guide will show you how to run the model efficiently using Docker for seamless execution.
Foundation Pose Setup, Install and Execution | Docker Execution | 6D Pose Estimation Tutorial 2025
Installation Steps

1️⃣ Required Tools:

C++ Build Tools (VS Code)

CMake

Git Bash

VcXsrv Server (for GUI forwarding)

2️⃣ Build & Run Docker Container:

docker build -t foundationpose .  # Build the image  
docker pull viki1626/codingtamilan:latest  # Pull the prebuilt image from Docker Hub  

docker run --gpus all --env NVIDIA_DISABLE_REQUIRE=1 -it --network=host --name pose   --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --ipc=host  -e DISPLAY=${DISPLAY} -e GIT_INDEX_FILE viki1626/codingtamilan:latest bash  

3️⃣ Start X Server:
Make sure VcXsrv is running for GUI support.

4️⃣ Create a Folder Inside the Container & Exit:

exit
5️⃣ Re-enter the Container & Set Display:

docker exec -it pose /bin/bash  
export DISPLAY=192.168.x.x:0.0  # Replace with your IP  
echo $DISPLAY  
6️⃣ Run the Model:

python run_demo.py  
📌 Resources & Links:
(Include links to GitHub repo, model weights, and related documents if applicable.)

👍 If you find this video helpful, don’t forget to like, share, and subscribe for more AI and computer vision content!
#6DPoseEstimation #SinRef6D #FoundationPose #PoseEstimation #ComputerVision #AI #MachineLearning #DeepLearning #Docker #RGBPoseEstimation #AR #Robotics #ObjectTracking #PoseDetection #AIResearch #TechTutorial
