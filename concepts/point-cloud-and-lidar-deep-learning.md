# Point Cloud and LiDAR Deep Learning

> Processing 3D point clouds with neural networks — PointNet's permutation-invariant design, PointNet++ hierarchical feature learning, sparse 3D convolutions (MinkowskiNet), outdoor LiDAR segmentation, point cloud transformers, and the connection to autonomous driving and 3D vision.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[3d-vision-and-neural-rendering]] — point cloud processing provides the geometric understanding that complements neural rendering; PointNet features can initialize NeRF/3DGS; point clouds are the bridge between raw sensor data and 3D scene representations
- [[autonomous-driving-perception]] — LiDAR point cloud processing is the core of the driving perception stack; PointPillars, CenterPoint, and BEVFormer build on point cloud architectures; sensor fusion combines point cloud and image features
- [[attention-and-transformers]] — Point Transformer brings self-attention to 3D; the evolution from PointNet to Point Transformer parallels CNN→ViT in images; serialization strategies (space-filling curves) enable efficient attention on point sets
- [[graph-neural-networks]] — point clouds can be viewed as graphs (k-NN graph); DGCNN (Dynamic Graph CNN) applies graph convolutions to point clouds; the local grouping in PointNet++ is a form of graph neighborhood
- [[object-detection]] — 3D object detection extends 2D detection to 3D bounding boxes; anchor-free methods (CenterPoint) parallel anchor-free 2D detection; DETR-style set prediction (3DETR) applies to 3D
- [[self-supervised-learning]] — Point-MAE and Point-BERT apply masked modeling to point clouds; pre-training on large unlabeled 3D data enables few-shot 3D understanding; CLIP-aligned 3D features enable zero-shot 3D recognition
- [[semantic-segmentation]] — 3D semantic segmentation of point clouds parallels 2D segmentation; U-Net-like encoder-decoder structures with skip connections are standard; per-point classification mirrors per-pixel classification
