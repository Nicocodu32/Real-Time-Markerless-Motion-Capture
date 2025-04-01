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
5. RTMO: Towards High-Performance One-Stage Real-Time Multi-Person Pose Estimation [[pdf]](https://arxiv.org/pdf/2312.07526.pdf)


### Methods based on body model such as smpl/smpl-x
6. Real-time RGBD-based Extended Body Pose Estimation [[code]](https://github.com/rmbashirov/rgbd-kinect-pose)
![image](https://github.com/visonpon/human-motion-capture/blob/main/images/rgbd-kinect-pose.png)
7. Deep3DPose: Realtime Reconstruction of Arbitrarily Posed Human Bodies from Single RGB Images [[paper]](https://arxiv.org/pdf/2106.11536.pdf)
8. Monocular Real-time Full Body Capture with Inter-part Correlations [[paper]](https://arxiv.org/pdf/2012.06087.pdf)


### Human 3d pose estimation
9. Faster VoxelPose: Real-time 3D Human Pose Estimation by Orthographic Projection [[pdf]](https://arxiv.org/pdf/2207.10955.pdf)
10. BlazePose GHUM Holistic: Real-time 3D Human Landmarks and Pose Estimation [[pdf]](https://arxiv.org/pdf/2206.11678.pdf)


### Simplify optical or inertial based motion capture
11. Real-Time Multi-person Motion Capture from Multi-view Video and IMUs[[paper]](https://link.springer.com/content/pdf/10.1007/s11263-019-01270-5.pdf)
12. Physical Inertial Poser (PIP):Physics-aware Real-time Human Motion Tracking from Sparse Inertial Sensors [[project]](https://xinyu-yi.github.io/PIP/)
13. Transformer Inertial Poser: Attention-based Real-time Human Motion Reconstruction from Sparse IMUs [[project]](https://github.com/jyf588/transformer-inertial-poser)
14. Fusion Poser: 3D Human Pose Estimation using Sparse IMUs and Head Tracker in real-time [[code]](https://github.com/LuzyCat/FusionPoser)
15. TIP: Real-time Human Motion Reconstruction from Sparse IMUs with Simultaneous Terrain Generation [[pdf]](https://arxiv.org/pdf/2203.15720.pdf)
16. Fusing Monocular Images and Sparse IMU Signals for Real-time Human Motion Capture [[project]](https://shaohua-pan.github.io/robustcap-page/)
17. EgoPoser: Robust Real-Time Ego-Body Pose Estimation in Large Scenes [[pdf]](https://arxiv.org/pdf/2308.06493.pdf)
18. Noise-in, Bias-out: Balanced and Real-time MoCap Solving [[project]](https://moverseai.github.io/noise-tail/)
19. SparsePoser: Real-time Full-body Motion Reconstruction from Sparse Data [[project]](https://upc-virvig.github.io/SparsePoser/)
20. HMD-Poser: On-Device Real-time Human Motion Tracking from Scalable Sparse Observations [[project]](https://pico-ai-team.github.io/hmd-poser)
21. Real-Time Simulated Avatar from Head-Mounted Sensors [[project]](https://www.zhengyiluo.com/SimXR/)


### Human motion capture in 3d scene
22. EgoLocate:Real-time Motion Capture, Localization, and Mapping with Sparse Body-mounted Sensors [[project]](https://xinyu-yi.github.io/EgoLocate/)


## Summary board

CV = Computer Vision
MPI = Max Planck Institute

| num | name              | fps | nb cam   | Multimodal | Open | date  | author       | conf       | MPJPE |  | precis | method calc | comp with | comments | link |
| --- | ----------------- | --- | -------- | ---------- | ---- | ----- | ------------ | ---------- | ----- | ------ | ------ | ----------- | --------- | -------- | ---- |
| 1   | XNect             | 30  | 1        | NO         |      | 07/20 | MPI          | SIGGRAPH20 |       | YES    |        |             |           |          | [[project]](http://gvv.mpi-inf.mpg.de/projects/XNect/) |
| 2   | 4D graph          | 30  | 5        | NO         | YES  | 01/21 | Tsinghua Uni | CVPR20     |       |        |        |             |           |          | [[code]](https://github.com/zhangyux15/4d_association) |
| 3   | Sequential P2M    | 30  | 1        | NO         |      | 12/23 | Tsinghua Uni |            |       |        |        |             |           |          | [[project]](https://liuyebin.com/proxycap/) |
| 4   | MOVIN             | 20  | 1 LIDAR  | NO         |      | 09/23 | KAIST        | PG23       |       |        |        |             |           |          | [[project]](https://movin3d.github.io/movin_pg2023/) |
| 5   | RTMO              | 141 | 1        | NO         | YES  | 06/24 | Tsinghua GS  |            |       |        |        |             |           |          | [[pdf]](https://arxiv.org/pdf/2312.07526.pdf) |
| 6   | RGBD-based        | 30  | 1 Kinect | NO         | YES  | 03/21 | Samsung AI   | WACV21     |       | YES    |        | SMPL        |           |          | [[code]](https://github.com/rmbashirov/rgbd-kinect-pose) |
| 7   | Deep3DPose        | 20  | 1        | NO         |      | 06/21 | Chinese prof |            |       |        |        |             |           |          | [[paper]](https://arxiv.org/pdf/2106.11536.pdf) |
| 8   | Inter-P correl    | 31  | 1        | NO         |      | 04/21 | Tsinghua Uni |            |       | YES    |        | IKNet       |           | precise hands and head | [[paper]](https://arxiv.org/pdf/2012.06087.pdf) |
| 9   | F VXPose          |     |          |            |      | 07/22 |              |            |       |        |        |             |           |          | [[pdf]](https://arxiv.org/pdf/2207.10955.pdf) |
| 10  | BlazePose         |     |          |            |      |       |              |            |       |        |        |             |           |          | [[pdf]](https://arxiv.org/pdf/2206.11678.pdf) |
| 11  | MultiVid IMU      |     |          |            |      |       |              |            |       |        |        |             |           |          | [[paper]](https://link.springer.com/content/pdf/10.1007/s11263-019-01270-5.pdf) |
| 12  | PIP               |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://xinyu-yi.github.io/PIP/) |
| 13  | TIP Attention     |     |          |            |      |       |              |            |       |        |        |             |           |          | [[pdf]](https://arxiv.org/pdf/2203.15720.pdf) |
| 14  | Fus poser         |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://shaohua-pan.github.io/robustcap-page/) |
| 15  | TIP Generation    |     |          |            |      |       |              |            |       |        |        |             |           |          | [[pdf]](https://arxiv.org/pdf/2203.15720.pdf) |
| 16  | Fusing            |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://shaohua-pan.github.io/robustcap-page/) |
| 17  | EgoPoser          |     |          |            |      |       |              |            |       |        |        |             |           |          | [[pdf]](https://arxiv.org/pdf/2308.06493.pdf) |
| 18  | Noise-in Bias-out |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://moverseai.github.io/noise-tail/) |
| 19  | SparsePoser       |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://upc-virvig.github.io/SparsePoser/) |
| 20  | HMD-Poser         |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://pico-ai-team.github.io/hmd-poser) |
| 21  | Simu Avatar       |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://www.zhengyiluo.com/SimXR/) |
| 22  | EgoLocate         |     |          |            |      |       |              |            |       |        |        |             |           |          | [[project]](https://xinyu-yi.github.io/EgoLocate/) |


