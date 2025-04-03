# Real Time Markerless Motion Capture
Summary of all existing real time markerless motion capture tools

## Classification by type of method used
### Methods based directly on video
1. XNect: real-time multi-person 3D motion capture with a single RGB camera[[project]](http://gvv.mpi-inf.mpg.de/projects/XNect/)
![image](https://github.com/visonpon/human-motion-capture/blob/main/images/Xnet.png)
2. 4D Association Graph for Realtime Multi-person Motion Capture Using Multiple Video Cameras [[code]](https://github.com/zhangyux15/4d_association)
![image](https://github.com/visonpon/human-motion-capture/blob/main/images/4dAsspciation.png)
3. Real-time Monocular Full-body Capture in World Space via Sequential Proxy-to-Motion Learning [[project]](https://liuyebin.com/proxycap/)
4. MOVIN: Real-time Motion Capture using a Single LiDAR [[project]](https://movin3d.github.io/movin_pg2023/)
5. ELMO: Enhanced Real-time LiDAR Motion Capture through Upsampling [[pdf]](https://arxiv.org/pdf/2410.06963)
6. RTMO: Towards High-Performance One-Stage Real-Time Multi-Person Pose Estimation [[pdf]](https://arxiv.org/pdf/2312.07526.pdf)


### Methods based on body model such as smpl/smpl-x
7. Real-time RGBD-based Extended Body Pose Estimation [[code]](https://github.com/rmbashirov/rgbd-kinect-pose)
![image](https://github.com/visonpon/human-motion-capture/blob/main/images/rgbd-kinect-pose.png)
8. Deep3DPose: Realtime Reconstruction of Arbitrarily Posed Human Bodies from Single RGB Images [[paper]](https://arxiv.org/pdf/2106.11536.pdf)
9. Monocular Real-time Full Body Capture with Inter-part Correlations [[paper]](https://arxiv.org/pdf/2012.06087.pdf)


### Human 3d pose estimation
10. Faster VoxelPose: Real-time 3D Human Pose Estimation by Orthographic Projection [[pdf]](https://arxiv.org/pdf/2207.10955.pdf)
11. BlazePose GHUM Holistic: Real-time 3D Human Landmarks and Pose Estimation [[pdf]](https://arxiv.org/pdf/2206.11678.pdf)


### Simplify optical or inertial based motion capture
12. Real-Time Multi-person Motion Capture from Multi-view Video and IMUs[[paper]](https://link.springer.com/content/pdf/10.1007/s11263-019-01270-5.pdf)
13. Physical Inertial Poser (PIP):Physics-aware Real-time Human Motion Tracking from Sparse Inertial Sensors [[project]](https://xinyu-yi.github.io/PIP/)
14. Transformer Inertial Poser: Attention-based Real-time Human Motion Reconstruction from Sparse IMUs [[project]](https://github.com/jyf588/transformer-inertial-poser)
15. Fusion Poser: 3D Human Pose Estimation using Sparse IMUs and Head Tracker in real-time [[code]](https://github.com/LuzyCat/FusionPoser)
16. TIP: Real-time Human Motion Reconstruction from Sparse IMUs with Simultaneous Terrain Generation [[pdf]](https://arxiv.org/pdf/2203.15720.pdf)
17. Fusing Monocular Images and Sparse IMU Signals for Real-time Human Motion Capture [[project]](https://shaohua-pan.github.io/robustcap-page/)
18. EgoPoser: Robust Real-Time Ego-Body Pose Estimation in Large Scenes [[pdf]](https://arxiv.org/pdf/2308.06493.pdf)
19. Noise-in, Bias-out: Balanced and Real-time MoCap Solving [[project]](https://moverseai.github.io/noise-tail/)
20. SparsePoser: Real-time Full-body Motion Reconstruction from Sparse Data [[project]](https://upc-virvig.github.io/SparsePoser/)
21. HMD-Poser: On-Device Real-time Human Motion Tracking from Scalable Sparse Observations [[project]](https://pico-ai-team.github.io/hmd-poser)
22. Real-Time Simulated Avatar from Head-Mounted Sensors [[project]](https://www.zhengyiluo.com/SimXR/)


### Human motion capture in 3d scene
23. EgoLocate:Real-time Motion Capture, Localization, and Mapping with Sparse Body-mounted Sensors [[project]](https://xinyu-yi.github.io/EgoLocate/)


## Summary board

CV = Computer Vision
MPI = Max Planck Institute
MPI-INF-3DHP = Only Computer Vision
IJCV = International Journal of Computer Vision
GT = Ground Truth
CNN = Convoluted Neural Network
FCN = Fully Connected Network
DS = Data Set
CVAE = Conditional Variational AutoEncoder
HPE3DA = Human Pose Estimator 3D with Angles


| num | name              | fps | nb cam   | Multimodal | Multiperson | Open | date  | author       | conf/journ | output | MPJPE (mm) | Joint ang | MJRE (°) | method calc | dataset GT     | comments | link |
| --- | ----------------- | --- | -------- | ---------- | ----------- | ---- | ----- | ------------ | ---------- | ------ | ---------- | --------- | -------- | ----------- | -------------- | -------- | ---- |
| 1   | XNect             | 30  | 1        | NO         | YES         | NO   | 07/20 | MPI          | SIGGRAPH20 | HPE3DA | 63.6       | YES       | ungiven  | Neural Net  | Human3.6m (MC) | CNN (SelecSLS) estimating 2D/3D pose features for visible joints -> FCN computing complete 3D pose for all individuals -> space-time skeletal model fitting to predicted 2D/3D pose to reconcile 2D/3D pose and enforce temporal coherence | [[project]](http://gvv.mpi-inf.mpg.de/projects/XNect/) |
| 2   | 4D graph          | 30  | 5        | NO         | YES         | YES  | 01/21 | Tsinghua Uni | CVPR20     | HPE3D  | % given    | NO        | NONE     | NONE        | Own (MC OptiTrack) | 4D association graph where each limb detected by a camera from a bottom-up method is associated with the some limb detected by others cameras and there also is a a temporal connection between limbs | [[code]](https://github.com/zhangyux15/4d_association) |
| 3   | Sequential P2M    | 30  | 1        | NO         | NO          | NO   | 12/23 | Tsinghua Uni |            | HPE3D  | 45.9       | NO        | NONE     | NONE        | EgoBody/RICH (CV) & Human3.6m (MC) | precise hands / from 2DPE they estimate 3D body posture thanks to a neural network and they also separately estimate hand posture. Finally a specific neural network reconstruct plausible contact with ground | [[project]](https://liuyebin.com/proxycap/) |
| 4   | MOVIN             | 20  | 1 LIDAR  | NO         | NO          | YES  | 09/23 | KAIST        | PG23       | HPE3DA | 62.1       | YES       | 10.12    | CVAE        | Own (MC OptiTrack) | Use of a CVAE that encodes point cloud, skeletton from past and present and contact with ground and than decodes a sample of the features extracted in the latent space recombined with informations from the past. Basically a feature encoder and a pose generator | [[project]](https://movin3d.github.io/movin_pg2023/) |
| 5   | ELMO              | 60  | 1 LIDAR  | NO         | NO          | YES  | 10/24 | MOVIN inc.   | SIGASIA24  | HPE3DA | 48.6       | YES       | 10.41    | Neural net  | Own (MC OptiTrack) | Enhancement of MOVIN with a upsampling technique for LIDAR frequency augmentation | [[pdf]](https://arxiv.org/pdf/2410.06963)
| 6   | RTMO              | 141 | 1        | NO         | YES         | YES  | 06/24 | Tsinghua GS  |            | HPE2D  | AP given   | NO        | NONE     | NONE        | COCO/CrowdPose (CV) | One Stage method based on Neural network which allows a very high fps rate on GPU | [[pdf]](https://arxiv.org/pdf/2312.07526.pdf) |
| 7   | RGBD-based        | 30  | 1 Kinect | NO         | NO          | YES  | 03/21 | Samsung AI   | WACV21     | SMPL-X |            | YES       |          |             |                | Combination of existing neural networks for hands, body pose and facial expressions | [[code]](https://github.com/rmbashirov/rgbd-kinect-pose) |
| 8   | Deep3DPose        | 20  | 1        | NO         | NO          | NO   | 06/21 | Chinese prof |            | SMPL   | 41.8       | YES       | ungiven  |             |  Human3.6M (MC) & 3DPW (IMU) |          | [[paper]](https://arxiv.org/pdf/2106.11536.pdf) |
| 9   | Inter-P correl    | 31  | 1        | NO         |             |      | 04/21 | Tsinghua Uni |            | SMPLH  |            |           |          | IKNet       |                | precise hands and head | [[paper]](https://arxiv.org/pdf/2012.06087.pdf) |
| 10  | F VXPose          | 31  | 5        | NO         |             |      | 07/22 | Peking Uni   |            | HPE3D  |       |           |             |                |          | [[pdf]](https://arxiv.org/pdf/2207.10955.pdf) |
| 11  | BlazePose         | 15  | 1        | NO         |             |      | 06/22 | Google       |            | FullB  |       |           | GHUM        |                | works on phone | [[pdf]](https://arxiv.org/pdf/2206.11678.pdf) |
| 12  | MultiVid IMU      |     |          | YES (IMU)  |             |      | 01/19 |              | IJCV20     |        |       |           |             |                |          | [[paper]](https://link.springer.com/content/pdf/10.1007/s11263-019-01270-5.pdf) |
| 13  | PIP               |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://xinyu-yi.github.io/PIP/) |
| 14  | TIP Attention     |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[pdf]](https://arxiv.org/pdf/2203.15720.pdf) |
| 15  | Fus poser         |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://shaohua-pan.github.io/robustcap-page/) |
| 16  | TIP Generation    |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[pdf]](https://arxiv.org/pdf/2203.15720.pdf) |
| 17  | Fusing            |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://shaohua-pan.github.io/robustcap-page/) |
| 18  | EgoPoser          |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[pdf]](https://arxiv.org/pdf/2308.06493.pdf) |
| 19  | Noise-in Bias-out |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://moverseai.github.io/noise-tail/) |
| 20  | SparsePoser       |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://upc-virvig.github.io/SparsePoser/) |
| 21  | HMD-Poser         |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://pico-ai-team.github.io/hmd-poser) |
| 22  | Simu Avatar       |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://www.zhengyiluo.com/SimXR/) |
| 23  | EgoLocate         |     |          |            |             |      |       |              |            |        |       |           |             |                |          | [[project]](https://xinyu-yi.github.io/EgoLocate/) |

## Datasets

| name         | Real or Synthetic | Tools used for GT | comments | link |
| ------------ | ----------------- | ----------------- | -------- | ---- |
| Human3.6m    | R                 | Mo Cap system     | 11 actors 15 scenarios | [[project]](http://vision.imar.ro/human3.6m/description.php) |
| MPI-INF-3DHP | R                 | Computer Vision   | indoor/aoutdoor | [[project]](https://paperswithcode.com/dataset/mpi-inf-3dhp)
| HumanEva     | R                 | Mo Cap system     | Common gestures | [[project]](http://humaneva.is.tue.mpg.de/) |
| 3DPW         | R                 | CV and IMU        | outdoor w/ phone moving | [[project]](https://virtualhumans.mpi-inf.mpg.de/3DPW/) |
| CMU Panoptic | R                 | CV > 400 cam      | studio with a lot of VGA/RGB/Kinect| [[project]](http://domedb.perception.cs.cmu.edu/) |
| 4D graph DS  | R                 | MC OptiTrack      | close interactions/hard motions | [[project]](https://github.com/zhangyux15/multiview_human_dataset) |
| EgoBody      | R                 | 3 Kinect/hololens | capture from an interacting person's POV | [[project]](https://sanweiliti.github.io/egobody/egobody.html) |
| RICH         | S based on R      | CV SMPL-X         | labelling of contacts with environment thanks to BISTRO method | [[project]](https://rich.is.tue.mpg.de/) |
| PROX         | S based on R      | CV Kinect SMPL-X  |          | [[project]](https://prox.is.tue.mpg.de/) |
| MOVIN DS     | R                 | MC OptiTrack      | depth from a LIDAR and MC data | [[project]](https://github.com/MOVIN3D/ELMO_SIGASIA2024) |
| ELMO DS      | R                 | MC OptiTrack      | update to MOVIN DS more subject and poses same method | [[project]](https://github.com/MOVIN3D/ELMO_SIGASIA2024) |
| COCO         | R                 | Handmade anotatio | Large dataset anotated by pepole | [[project]](https://cocodataset.org/#keypoints-2020) |
| CrowdPose    | R                 | Handmade anotatio | Large dataset anotated by pepole | [[project]](https://github.com/jeffffffli/CrowdPose) |
| AMASS        | S based on R      | SMPL based on MC  | Combination of 15 MC datasets in one and applying SMPL model to thes 40hs of MC | [[project]](https://amass.is.tue.mpg.de/) |
| VoxCeleb     | R                 |                   | Youtube videos of people speaking | [[project]](https://www.robots.ox.ac.uk/~vgg/data/voxceleb/vox1.html)




## Brands doing MoCap

1. OptiTrack [[project]](https://www.optitrack.com/)
2. Vicon [[project]](https://www.vicon.com/)

