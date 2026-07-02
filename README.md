# CAIOS V5: Unified Cognitive Scheduling and Memory Cubes
**[Anonymous Repository for Peer Review]**

This repository contains the official, hardware-optimized inference code for the paper: *"CAIOS V5: Unified Cognitive Scheduling, Memory Cubes, and Spreading Activation for Long-Horizon Agent Execution on Consumer Hardware."*

### Overview
CAIOS V5 is a Cognitive AI Operating System designed to eliminate the "Token Tax" and prevent GPU Out-Of-Memory (OOM) crashes during long-horizon agentic workflows on consumer hardware. It synthesizes three State-of-the-Art mechanisms:
1. **MemOS MemCubes:** Unifies parameter weights, KV-cache, and plaintext into manageable system resources with an 80% K-LRU SSD Eviction protocol.
2. **SYNAPSE Spreading Activation:** Replaces static RAG with a dependency-structured graph (ContextWeaver) using lateral inhibition (threshold = 0.25) to prune noisy reasoning paths.
3. **Adaptive Cognitive Control Loop (ACCL):** Schedules hardware resources based on the cognitive convergence ($\Delta_{cog}$) between current and target states.

### Hardware Requirements
This specific V5 kernel is tuned for consumer-grade deployment:
* **Target GPU:** NVIDIA RTX 5050 (or equivalent 8GB VRAM card)
* **Storage:** 1TB SSD for K-LRU Swap Memory
* **LLM Engine:** Local Ollama server running `llama3.1` (8B)

### Execution
To reproduce the empirical telemetry reported in our paper, ensure your local Ollama server is active and run:
```bash
python caios_v5_ollama.py
```
This will output the live VRAM allocation, SSD swap sizes, eviction triggers, and job completion latency.

***
