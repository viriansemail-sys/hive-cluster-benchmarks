# Hive Cluster Benchmarks

## ▶ [View the benchmarks (live pages)](https://viriansemail-sys.github.io/hive-cluster-benchmarks/)

- [GLM-5.3-Flash · 320B · 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-09-glm-5.3-flash-3-box/)
- [GLM-5.3 · 744B · 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-glm-5.3-3-box/)
- [DeepSeek-V4-Flash · 2 vs 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-deepseek-v4-flash-3-box/)

The `.html` files in this repo are the source. Clicking them on GitHub shows code; use the links above to see the pages.

Local frontier-class models, run as one model across a small home cluster: two AMD Strix Halo boxes and one NVIDIA Grace Blackwell box, pooled with llama.cpp RPC. No cloud, no API.

| Date | Model | Size | Boxes | Answer speed | Page |
|---|---|---|---|---|---|
| 2026-10-09 | GLM-5.3-Flash (320B MoE, ~18B active) · UD-Q4_K_XL | 199.7 GB | 3 | ~10.8 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-09-glm-5.3-flash-3-box/) |
| 2026-10-08 | GLM-5.3 (744B MoE, 40B active) · UD-Q2_K_XL | 253.9 GB | 3 | ~7 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-glm-5.3-3-box/) |
| 2026-10-08 | DeepSeek-V4-Flash · IQ2XXS | 86.7 GB | 3 | ~13 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-deepseek-v4-flash-3-box/) |

## The cluster

| Box | Hardware | GPU stack | OS | Link |
|---|---|---|---|---|
| CC (head) | ASUS ROG Flow Z13 GZ302EA · Ryzen AI Max+ 395 · 128 GB | ROCm | Windows 11 | — |
| Corsa (worker) | Corsair AI Workstation · Ryzen AI Max+ 395 · 128 GB | ROCm | Windows 11 | USB4 cable to the head |
| Spark (worker) | ASUS Ascent GX10 · NVIDIA GB10 · 128 GB | CUDA 13 | Linux | 1 Gb Ethernet to the head |

Engine: llama.cpp (b1328 on the AMD boxes, matching commit 8172e65 CUDA build on the GB10), layer-split pipeline parallelism over RPC.

## The test

[llama-benchy](https://github.com/eugr/llama-benchy) 0.4.0, one request at a time: prompts of 512 and 2,048 tokens, 128-token answers, with no history and with 4,096 tokens of history, 3 runs each. Every box logs its temperature the whole run with a 203 °F automatic stop.

## Notes

- GLM-5.3: 744B is Z.ai's parameter count. Hugging Face lists 753B because the files include a built-in next-token draft (MTP) layer that llama.cpp does not use yet.
- Loading a 254 GB model split this way hit a freeze at the end of the head box's own GPU upload (llama.cpp issues [#19482](https://github.com/ggml-org/llama.cpp/issues/19482) and [#19745](https://github.com/ggml-org/llama.cpp/issues/19745)). Starting the head with `-lm mmap` avoided it.
- GLM-5.3-Flash needs a newer engine: it ran on llama.cpp b1341 on the AMD boxes and the matching commit b86d2f0 CUDA build on the GB10. Its built-in draft (MTP) layer was not used in this run.
- `--tensor-split` is applied in model-load order (RPC workers first, then the local GPU), which is not the order `--list-devices` prints.

The pages are single HTML files, served with GitHub Pages.
