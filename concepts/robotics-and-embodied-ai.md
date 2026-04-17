# Robotics and Embodied AI

> Deep learning for physical agents — manipulation (RT-2, Octo), locomotion, sim-to-real transfer, imitation learning, robot foundation models, and the convergence of language models, vision, and control in embodied systems.

> **Note:** This is a placeholder article in the demo repository. The full content is available in the complete knowledge base. The tagline, connections, and structure are preserved to show how articles link together.

## Connections

- [[reinforcement-learning]] — RL (PPO, SAC) is the primary training paradigm for robotic control; sim-to-real RL is the dominant approach for locomotion and dexterous manipulation
- [[world-models-and-predictive-learning]] — Dreamer and model-based RL learn environment dynamics for sample-efficient robot learning; world models enable planning in imagination
- [[multimodal-models]] — robot foundation models (RT-2) are VLMs extended with action output; the VLM's visual and linguistic understanding transfers to physical tasks
- [[agents-and-tool-use]] — LLM-based robot planning (SayCan, Code as Policies) uses LLMs as high-level planners with robot skills as "tools"
- [[large-language-models]] — LLMs provide semantic understanding, planning, and code generation for robot systems; the "language-to-action" paradigm
- [[diffusion-models]] — diffusion policies represent multimodal action distributions; diffusion-based planning generates action sequences by denoising
- [[data-augmentation]] — domain randomization is augmentation for sim-to-real; visual and physical parameter randomization makes policies robust to the real world
- [[autonomous-driving-perception]] — autonomous driving is a specific robotics domain; end-to-end driving and robot manipulation share architectural approaches (Transformers for control, imitation learning, sim-to-real)
