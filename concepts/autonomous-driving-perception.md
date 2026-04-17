# Autonomous Driving Perception

> Deep learning for self-driving vehicles — 3D object detection (PointPillars, CenterPoint, BEVFormer), sensor fusion (LiDAR + camera), bird's-eye view representations, occupancy networks, lane detection, and the shift toward end-to-end driving.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[object-detection]] — 2D detection (YOLO, DETR) provides the foundation; 3D detection extends to bounding boxes in 3D space with depth, rotation, and velocity
- [[3d-vision-and-neural-rendering]] — point cloud processing (PointNet), voxel representations, and depth estimation are core components of the perception stack
- [[multimodal-models]] — sensor fusion (LiDAR + camera + radar) is fundamentally a multimodal problem; BEV representations unify modalities in a shared space
- [[attention-and-transformers]] — BEVFormer and DETR3D use Transformer attention for spatial reasoning; Transformers are replacing CNNs throughout the driving stack
- [[world-models-and-predictive-learning]] — end-to-end driving increasingly uses world models to predict future states and plan accordingly; Dreamer-style imagination for driving
- [[semantic-segmentation]] — segmenting drivable area, lane markings, and sidewalks is a core perception task; occupancy networks extend segmentation to 3D
- [[video-understanding-and-generation]] — temporal consistency across frames is crucial; video understanding techniques (temporal attention, feature propagation) apply to driving perception
