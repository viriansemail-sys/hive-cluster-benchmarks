# Hive Cluster Benchmarks

## ▶ [View the benchmarks (live pages)](https://viriansemail-sys.github.io/hive-cluster-benchmarks/)

- [Qwen3-14B · one RTX 3090 · 779 tok/s with 32 at once](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-30-qwen3-14b-awq-rtx-3090-1-box/)
- [Nemotron 3.5 Bolt 74B · one box · 19 tok/s flat to 16K](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-23-nemotron-3.5-bolt-74b-1-box/)
- [DeepSeek-V4-Flash-0731 + DSpark · 21–37% faster on 2 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-dspark-2-box/)
- [DeepSeek-V4-Flash-0731 · 2 boxes beat 3, up to 53% faster prompt reading](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-2-box/)
- [DeepSeek-V4-Flash-0731 + DSpark · 24–32% slower on 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-dspark-3-box/)
- [DeepSeek-V4-Flash-0731 · 14.5 tok/s on 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-3-box/)
- [DeepSeek-V4-Flash · new engine, up to 30% faster prompt reading](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-new-engine-3-box/)
- [GLM-5.3-Flash + MTP · 23–37% faster answers](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-09-glm-5.3-flash-mtp-3-box/)
- [GLM-5.3-Flash · 320B · 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-09-glm-5.3-flash-3-box/)
- [GLM-5.3 · 744B · 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-glm-5.3-3-box/)
- [DeepSeek-V4-Flash · 2 vs 3 boxes](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-deepseek-v4-flash-3-box/)

The `.html` files in this repo are the source. Clicking them on GitHub shows code; use the links above to see the pages.

Local frontier-class models, run as one model across a small home cluster: two AMD Strix Halo boxes and one NVIDIA Grace Blackwell box, pooled with llama.cpp RPC. No cloud, no API.

| Date | Model | Size | Boxes | Answer speed | Page |
|---|---|---|---|---|---|
| 2026-10-30 | Qwen3-14B (14.8B dense) · AWQ 4-bit · vLLM 0.20.0 · one RTX 3090 at 200 W | 9.4 GB | 1 | ~46.5 tok/s (779 peak, 32 at once) | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-30-qwen3-14b-awq-rtx-3090-1-box/) |
| 2026-10-23 | Nemotron 3.5 Bolt 74B-A9B (74B MoE, 9B active) · UD-Q5_K_XL | 58.9 GB | 1 | ~19.4 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-23-nemotron-3.5-bolt-74b-1-box/) |
| 2026-10-11 | DeepSeek-V4-Flash-0731 + DSpark (official drafter, 3 draft tokens) · UD-IQ2_XXS | 90.9 GB + 10.9 GB | 2 | ~20 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-dspark-2-box/) |
| 2026-10-11 | DeepSeek-V4-Flash-0731 · UD-IQ2_XXS | 90.9 GB | 2 | ~14.9 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-2-box/) |
| 2026-10-11 | DeepSeek-V4-Flash-0731 + DSpark (official drafter, 3 draft tokens) · UD-IQ2_XXS | 90.9 GB + 10.9 GB | 3 | ~11.0 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-dspark-3-box/) |
| 2026-10-11 | DeepSeek-V4-Flash-0731 · UD-IQ2_XXS | 90.9 GB | 3 | ~14.5 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-0731-3-box/) |
| 2026-10-11 | DeepSeek-V4-Flash · IQ2XXS · engine b1341 | 86.7 GB | 3 | ~13.95 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-11-deepseek-v4-flash-new-engine-3-box/) |
| 2026-10-09 | GLM-5.3-Flash + MTP (2 draft tokens) · UD-Q4_K_XL | 199.7 GB | 3 | ~14.2 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-09-glm-5.3-flash-mtp-3-box/) |
| 2026-10-09 | GLM-5.3-Flash (320B MoE, ~18B active) · UD-Q4_K_XL | 199.7 GB | 3 | ~10.8 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-09-glm-5.3-flash-3-box/) |
| 2026-10-08 | GLM-5.3 (744B MoE, 40B active) · UD-Q2_K_XL | 253.9 GB | 3 | ~7 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-glm-5.3-3-box/) |
| 2026-10-08 | DeepSeek-V4-Flash · IQ2XXS | 86.7 GB | 3 | ~13 tok/s | [open page](https://viriansemail-sys.github.io/hive-cluster-benchmarks/benchmarks/2026-10-08-deepseek-v4-flash-3-box/) |

## The cluster

| Box | Hardware | GPU stack | OS | Link |
|---|---|---|---|---|
| CC (head) | ASUS ROG Flow Z13 GZ302EA · Ryzen AI Max+ 395 · 128 GB | ROCm | Windows 11 | — |
| Corsa (worker) | Corsair AI Workstation · Ryzen AI Max+ 395 · 128 GB | ROCm / Vulkan | Windows 11 (pooled runs) · Ubuntu 26.04 since Oct 22 | USB4 cable to the head |
| Skypad (single-box runs) | GMKtec EVO-X2 · Ryzen AI Max+ 395 · 96 GB | Vulkan (RADV) | Ubuntu 26.04 | USB4 cable to Corsa |
| Spark (worker) | ASUS Ascent GX10 · NVIDIA GB10 · 128 GB | CUDA 13 | Linux | 1 Gb Ethernet to the head |
| Little Geek (single-GPU runs) | MSI MAG X870 Tomahawk · Ryzen 7 7800X3D · 96 GB · NVIDIA RTX 3090 24 GB | CUDA 13 · vLLM | Ubuntu 22.04 | — |

Engine: llama.cpp (b1328 on the AMD boxes, matching commit 8172e65 CUDA build on the GB10), layer-split pipeline parallelism over RPC.

## The test

[llama-benchy](https://github.com/eugr/llama-benchy) 0.4.0, one request at a time: prompts of 512 and 2,048 tokens, 128-token answers, with no history and with 4,096 tokens of history, 3 runs each. Every box logs its temperature the whole run with a 203 °F automatic stop.

## Notes
- Nemotron 3.5 Bolt 74B (one box, Oct 23): llama.cpp 184f653 Vulkan build on Skypad, 131,072-token context allocated, thinking off, depths 0 / 4K / 16K. Answer speed 19.4 → 19.1 tok/s across depth.

- GLM-5.3: 744B is Z.ai's parameter count. Hugging Face lists 753B because the files include a built-in next-token draft (MTP) layer that llama.cpp does not use yet.
- Loading a 254 GB model split this way hit a freeze at the end of the head box's own GPU upload (llama.cpp issues [#19482](https://github.com/ggml-org/llama.cpp/issues/19482) and [#19745](https://github.com/ggml-org/llama.cpp/issues/19745)). Starting the head with `-lm mmap` avoided it.
- GLM-5.3-Flash needs a newer engine: it ran on llama.cpp b1341 on the AMD boxes and the matching commit b86d2f0 CUDA build on the GB10. Its built-in draft (MTP) layer was not used in this run.
- GLM-5.3-Flash + MTP: same file, engine, boxes and split as the plain Flash run, with `--spec-type draft-mtp --spec-draft-n-max 2` on the head. Answer speed rose 23–37%; prompt reading stayed within 4%. About 71% of draft tokens were accepted. The head needed ~5 GB more memory for the draft context.
- DeepSeek-V4-Flash on engine b1341 (same file, boxes and flags as the b1328 run): prompt reading 14–30% faster, first-word wait up to 11 s shorter, answer speed +2–4%.
- DeepSeek-V4-Flash-0731 (unsloth UD-IQ2_XXS) on b1341: 4–7% faster than the original V4-Flash on the same setup.
- DeepSeek-V4-Flash-0731 + DSpark (`--spec-type draft-dspark --spec-draft-n-max 3`, official Q8_0 drafter): 24–32% slower answers on 3 boxes; 51% of draft tokens accepted. The draft file must be in the `dflash` format; the ds4-fork `deepseek4-dspark` format does not load in mainline llama.cpp. Do not pass `-devd`.
- DeepSeek-V4-Flash-0731 on 2 boxes (CC + Corsa over USB4 only, no third box): prompt reading 41–53% faster than on 3 boxes, first-word wait 29–35% shorter, answer speed +2–4%. The boxes still take turns (layer split).
- DeepSeek-V4-Flash-0731 + DSpark on 2 boxes: answers 21–37% faster than plain 2-box (up to ~20 tok/s), prompt reading 4–26% slower; 48% of draft tokens accepted. The same drafter lost 24–32% on 3 boxes, where every draft round also crossed the 1 Gb link.
- `--tensor-split` is applied in model-load order (RPC workers first, then the local GPU), which is not the order `--list-devices` prints.

The pages are single HTML files, served with GitHub Pages.
