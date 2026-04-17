# Protein and Molecular Deep Learning

> Deep learning for biological and chemical structure — AlphaFold for protein structure prediction, protein language models (ESM), geometric deep learning on molecules, molecular generation, drug discovery, and the intersection of ML with structural biology.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[graph-neural-networks]] — molecular graphs are processed by GNNs; message passing on atomic graphs is the standard architecture for molecular property prediction
- [[3d-vision-and-neural-rendering]] — 3D geometric reasoning is essential for molecular structure; equivariant networks process 3D point clouds of atoms
- [[self-supervised-learning]] — protein language models use masked prediction on sequences; molecular pre-training learns representations from unlabeled chemical data
- [[diffusion-models]] — molecular generation (EDM, DiffSBDD, RFdiffusion) applies equivariant diffusion to 3D molecular coordinates; AlphaFold3 uses diffusion for structure generation
- [[attention-and-transformers]] — AlphaFold2's Evoformer is a specialized Transformer; protein language models (ESM) are standard Transformers; SE(3)-Transformers apply attention with geometric equivariance
- [[language-model-pretraining]] — protein LMs apply the BERT/GPT paradigm to amino acid sequences; SMILES-based models treat molecules as text; DNA foundation models pre-train on genomic sequences
- [[reinforcement-learning]] — RL-based molecular generation optimizes molecules for desired properties through exploration of chemical space
