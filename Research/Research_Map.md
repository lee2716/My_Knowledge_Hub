# Research Map: Accelerator Simulation and AI Compilers on PULP

> **Source:** reverse-engineered from my PULP-related GitHub repositories, October 2026
> **Tags:** `research-map` `pulp` `gvsoc` `deeploy` `hw-sw-codesign` `in-memory-computing`
> **Interactive version:** [claude.ai artifact](https://claude.ai/artifact/LBnCJfM7u19xS3otoGZADb) (private link; this file is the canonical copy)

## TL;DR

My main line is **hardware/software co-design for PULP-family heterogeneous SoCs**. On one side I build cycle-level models of new accelerators in GVSoC (a multi-tile heterogeneous SoC that is not yet public; its name and composition are withheld here). On the other side I use Deeploy to turn networks such as FP32 microLlama into bare-metal C for the Snitch cluster. Between the two sits a path I opened myself: capability-driven kernel generation, which I have since broken into work packages for a master's student. Five work lines on GitHub feed this main line, and they touch nine fields.

## The five work lines

| # | Work line | Category | Evidence |
|---|-----------|----------|----------|
| P2 | **Tile-mesh SoC modelling in GVSoC** | Hardware · architecture · simulation | `lee2716/gvsoc-pulp` fork, development branches for an unreleased SoC (name, branch names and paths withheld); active since summer 2026 |
| P3 | **PULP-AutoKernel: capability-driven kernel generation** | Compilers · code generation | `lee2716/pulp-autokernel` (private); `_docs/` holds the four-way comparison, the cross-platform extension plan and `thesis_guidance.md` |
| P1 | **Deeploy × Snitch: FP32 microLlama deployment** | Compilers · code generation | `lee2716/Deeploy` branches `update_lee2716_devel`, `rmsnorm`, `fix-tiler-aliases`; upstream Deeploy PR 153; notes `microLlama_Complete` and the DB-vs-SB series; thesis chapter 4 |
| P6 | **NeuroSoC → Snitch deployment (collaboration)** | ML systems · applications | `diaconuccalin/neurosoc_deeployment` (private); `kernels/`, `models/`, `cmake/simulation.cmake` |
| P5 | **RTL and platform notes (113 deep dives)** | Hardware · architecture · simulation | `lee2716/tech-notes-backup` (private); tags `v1`, `v2`, `v3`; nine merged documents under `merged/` |

### P2 · Tile-mesh SoC modelling in GVSoC

A cycle-level GVSoC model of an unreleased multi-tile heterogeneous SoC. The mesh combines a controller tile with DMA engines and NoC ports, a tile built around a digital in-memory-computing accelerator, a tensor-accelerator tile and a vector-unit tile. The modelling work covers job queues and prefetch for the in-memory accelerator, DMA pipelining and transaction concurrency, scratchpad constraints, and the interplay between wide and narrow NoC paths. The architecture, the tile types and the commit history are withheld here because the project is not yet public.

### P3 · PULP-AutoKernel

Mine SSR/FREP intrinsics out of expert-written kernels with libclang; extract chip capabilities from `Bender.yml`, `cfg/*.hjson` and generated headers; extract a loop-nest IR and a fingerprint from a generic C reference; match, then let PySynth compose a dispatcher; verify bit-exact under Banshee. Four generation strategies were compared head to head (Mako templates, HAL + glue, pure-Python synthesis, MLIR/xDSL). The thesis is **retrieval + composition over synthesis**. The project is now written up as a master's thesis plan with five research questions and six work packages.

### P1 · Deeploy × Snitch

FP32 microLlama on the Snitch cluster: FP32 MatMul, Add and RMSNorm kernels; fixes for the SSR/FREP all-zero bug and the BSS DMA overflow; the analysis of why an L1 budget of 16K beats 20K (O-tile alignment to the unroll factor of 8 plus FMA latency hiding, verified on RTL); and the finding that "double buffering is always slower than single buffering" was an artefact of GVSoC's default `latency=0`. With a 1000-cycle latency injected, double buffering is 2.6× faster.

### P6 · NeuroSoC → Snitch

Convert IBM NeuroSoC models (JSON graph plus pickle weights) to ONNX, run a Deeploy-style code generator to the Snitch cluster, validate on both GVSoC and Questa VSIM. KCLResnet18 runs end to end; MobileBert is blocked on missing kernels.

### P5 · RTL and platform notes

Line-by-line RTL analyses of the Snitch core and cluster, CVA6, RedMulE, iDMA, FlooNoC, Cheshire, the HWPE and HCI frameworks and AXI; architecture notes for the nine Deeploy targets (Generic, PULPOpen, MemPool, Neureka, GAP9, CortexM, Chimera, SoftHier, Picobello); a comparison of four simulators (Banshee, GVSoC, QEMU, Questa); a MAGIA Verilator porting handbook; learning roadmaps for Picobello and for reading Deeploy against GVSoC. In July 2026, 76 notes were re-verified by rerunning commands against the current code, which corrected three conclusion-level errors.

## The nine fields

Colour categories used in the interactive map: **HW** (hardware, architecture, simulation), **SW** (compilers, code generation), **ML** (ML systems, applications), **Meta** (supervision, research training).

| Field | Category | Role for me | Strongest work lines | Where this work would go |
|-------|----------|-------------|----------------------|--------------------------|
| Computer architecture | HW | Core ground | P2, P5 strong; P1, P3 medium | DAC, DATE, ICCAD, ASP-DAC; ISCA, MICRO, HPCA; IEEE TC, TCAD, IEEE Micro |
| Simulation methodology / EDA | HW | Core ground | P2 strong; P1, P5, P6 medium; P3 light | SAMOS, RSP, ICCD, DATE modelling track; IEEE TCAD; gem5 and QEMU workshops |
| Compilers and programming languages | SW | Core ground | P1, P3 strong; P5, P6 medium | CGO, PLDI, ASPLOS, CC, LCTES; MLSys |
| In-memory computing (CIM) | HW | The newest axis | P2 strong | ISSCC, JSSC, DAC, TCAD; JETCAS special issues on CIM |
| ML systems / edge AI | ML | The payload | P1, P6 strong; P3 medium; P2 light | MLSys, tinyML Summit, efficient-ML workshops at NeurIPS and ICML, IEEE JETCAS |
| Digital IC and RTL design/verification | HW | Ground truth for my simulation models | P5 strong; P2 medium | DATE, ICCAD, VLSI Symposium, IEEE TCAS, TVLSI |
| HPC and data movement | HW | Methodological neighbour | P2 medium; P1 light | SC, IPDPS, PPoPP, ICS; NOCS |
| Embedded and real-time systems | ML | An under-sold strength | P1 medium; P3, P6 light | ESWEEK (CASES, CODES+ISSS, EMSOFT); RTSS; IEEE Embedded Systems Letters |
| Master's supervision and research training | Meta | Turning a project into gradable work packages | P3 strong; P5 medium | Not a publication venue; shows up in acknowledgements, co-authorship and teaching records |

### What each field means for me

- **Computer architecture.** Heterogeneous tile meshes, HWPE job queues and prefetch, wide and narrow NoC ports, TCDM bank structure, memory hierarchy and DMA are the field's home questions. My edge is that every structural decision can be quantified immediately on real Deeploy-generated workloads instead of synthetic traces.
- **Simulation methodology / EDA.** GVSoC is an event-driven, instruction-level full-system simulator. I add new models to it (an in-memory-computing accelerator, tiles, DMA engines) and I probe its accuracy boundary: `latency=0` hides the benefit of double buffering, which is a finding about the simulator, not the design. The four-simulator comparison and the Banshee bit-exact checks live here too.
- **Compilers and programming languages.** Deeploy's graph lowering, operator templates, tiling and static memory planning are classic compiler problems for bare-metal targets. AutoKernel goes further: source mining with libclang, algorithm recognition by loop-nest fingerprint, and a direct comparison of retrieval + composition against synthesis in MLIR/xDSL. There is a lot of room to bring in ILP memory planning, cost models and autotuning.
- **In-memory computing.** The in-memory accelerator model answers "how does a digital CIM macro get fed inside a tile mesh with DMA engines and a job queue": how weights are held and prefetched, how jobs are queued and overlapped, and which structural hazards between loading and computing must be respected. These are macro-and-above, system-and-below questions, which is the thinnest layer of the CIM literature.
- **ML systems / edge AI.** The payloads run from ResNet and MobileBert to FP32 microLlama to low-precision operators on an in-memory-computing accelerator. Prefill versus decode, RoPE mapping, flash-attention tiling: model structure and hardware structure accommodating each other is the core MLSys question.
- **Digital IC and RTL design/verification.** Most of the 113 notes are line-by-line RTL: Snitch's SSR and FREP sequencer, CVA6's divider and caches, RedMulE, iDMA, FlooNoC, the HWPE framework. The tile-mesh GVSoC model is written against the RTL's own address map, and the 16K-beats-20K result was confirmed on RTL. This is what lets my simulation results claim alignment with silicon.
- **HPC and data movement.** Attention kernels on a tensor accelerator, GEMV spread across several in-memory-computing tiles, double buffering and DMA prefetch are all scheduling problems where compute is cheap and bandwidth is scarce, the same shape HPC deals with on GPUs and many-core. Tiling, pipelining and NoC scheduling methods transfer directly.
- **Embedded and real-time systems.** Deeploy-generated code has no heap and a memory layout fixed at compile time, which gives predictable worst-case execution time. The NeuroSoC line also touched Zephyr. I have not yet made "determinism" a claim, but it is one of the properties the embedded community values most.
- **Master's supervision and research training.** `thesis_guidance.md` turns AutoKernel into a complete thesis plan: five research questions each with a hypothesis and a measurement, six work packages layered so that WP0–WP2 is a pass and WP3–WP5 reaches distinction or a publishable result, a six-month timeline and a three-week reading list. The Picobello and Deeploy-vs-GVSoC roadmaps in the notes are the same skill: turning the road I walked into one someone else can walk.

## Work line × field matrix

● core relationship · ◐ method or tool borrowed · ○ light contact

| Work line | Architecture | Simulation | Compilers | CIM | ML systems | RTL | HPC | Embedded | Supervision |
|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Tile-mesh SoC modelling (P2) | ● | ● | | ● | ○ | ◐ | ◐ | | |
| AutoKernel (P3) | ◐ | ○ | ● | | ◐ | | | ○ | ● |
| Deeploy deployment (P1) | ◐ | ◐ | ● | | ● | | ○ | ◐ | |
| NeuroSoC deployment (P6) | | ◐ | ◐ | | ● | | | ○ | |
| RTL notes (P5) | ● | ◐ | ◐ | | | ● | | | ◐ |

Edge labels from the interactive map, for the record:

- P1 → Compilers: tiling and static memory planning · ML systems: FP32 small-LLM inference · Architecture: L1 and DMA hierarchy · Simulation: the `latency=0` artefact · Embedded: deterministic bare-metal code · HPC: double-buffered data movement
- P2 → Architecture: heterogeneous tile mesh · CIM: in-memory accelerator cycle model · Simulation: event-driven modelling · RTL: address map checked against RTL · HPC: flash attention and cross-tile GEMV · ML systems: low-precision operators
- P3 → Compilers: retrieval + composition vs synthesis · Supervision: five RQs and six work packages · Architecture: chip capability description · ML systems: automatic operator libraries · Simulation: Banshee bit-exact verification · Embedded: targets Deeploy's TargetLibraries
- P5 → RTL: line-by-line analysis · Architecture: Snitch, CVA6, NoC · Simulation: four-simulator comparison · Compilers: Deeploy platform abstraction · Supervision: learning roadmaps and platform notes
- P6 → ML systems: ResNet and MobileBert deployment · Compilers: NeuroSoC → ONNX → C · Simulation: GVSoC and VSIM double validation · Embedded: Zephyr RTOS

## Three judgments

1. **I stand on a two-way loop.** Most people have either a compiler without a trustworthy simulator or a simulator without an automated deployment path. I have both. The double-buffering conclusion flipped when the GVSoC latency model changed; only someone holding both ends could have seen that. Papers should be argued around this coupling, not as a list of simulation results next to a list of compiler results.
2. **In-memory computing is the newest axis.** The GVSoC work since summer 2026 puts a macro-level CIM unit inside a tile mesh with DMA engines, a NoC and a job queue. The literature mostly stops at the macro or engine; how CIM above the tile is constrained by compilers and data movement is the thinnest layer, and the one I am best placed to fill.
3. **AutoKernel decides whether I am an empirical or a methodological researcher, and it is where I start supervising.** Deeploy deployment and the tile-mesh SoC modelling are empirical; reviewers trust the numbers. AutoKernel's claim that retrieval + composition beats synthesis is methodological; reviewers trust the fairness of the comparison. Handing the work packages to a student means the methodological line gets validated by someone else, and my own next paper can stay on the empirical side.

## Sources

- [`lee2716/Deeploy`](https://github.com/lee2716/Deeploy) — branches `update_lee2716_devel`, `rmsnorm`, `fix-tiler-aliases`; upstream [Deeploy PR 153](https://github.com/pulp-platform/Deeploy/pull/153) (FP32 operators and tiling for microLlama on Snitch) and [PR 136](https://github.com/pulp-platform/Deeploy/pull/136) (RMSNorm, merged)
- [`lee2716/gvsoc-pulp`](https://github.com/lee2716/gvsoc-pulp), [`lee2716/gvsoc`](https://github.com/lee2716/gvsoc), [`lee2716/gvsoc-core`](https://github.com/lee2716/gvsoc-core) — development branches for an unreleased SoC (not named here)
- [`lee2716/pulp-autokernel`](https://github.com/lee2716/pulp-autokernel) (private) — four-way comparison, cross-platform extension plan, master's thesis guidance
- [`lee2716/tech-notes-backup`](https://github.com/lee2716/tech-notes-backup) (private) — 113 notes, `merged/` consolidations, learning roadmaps
- [`diaconuccalin/neurosoc_deeployment`](https://github.com/diaconuccalin/neurosoc_deeployment) (collaboration, private)
- Upstream projects: [Deeploy](https://github.com/pulp-platform/Deeploy), [GVSoC](https://github.com/gvsoc/gvsoc), [Snitch cluster](https://github.com/pulp-platform/snitch_cluster), [PULP platform](https://pulp-platform.org/)
