# Trend Radar: Fifteen People to Follow Deeply

> **Purpose:** train my sense of where accelerators, in-memory computing and AI compilers are going. Whoever reads the future correctly gets to build it.
> **Tags:** `trend-radar` `in-memory-computing` `accelerators` `ai-compilers` `research-taste`
> **Started:** 2026-10-20 · **Next prune:** 2027-10

## Rules

**Three seats must always be filled.**

1. **Same work** — people doing what I do. Only this seat, on its own, turns my taste into an echo of my own group.
2. **Different interests** — industry, investors, the algorithm side. They see the constraints academia cannot see.
3. **Opposite conclusions** — people whose results or theses cut against my direction. They show me where my direction is most fragile.

**Follow fifteen deeply, not a hundred shallowly.** Deep means: read all of their major papers, watch their keynotes, write down their predictions and grade them two years later. Past twenty people this becomes scrolling a feed.

**Rotation.** Someone joins the fifteen only when someone leaves. The bench below is where candidates wait.

**Links.** Where I am sure of a home page I link it. Where I am not, I link a DBLP search, which is stable and lists every paper. A link to a repository means "watch the commits", a link to a newsletter means "read the issues", a link to a video channel means "watch the talks".

## The fifteen

Pairs who publish as one lab count as one seat. **Why** says why they are on the list. **Follow** says which of their outputs to read. **Log** says which of their claims to write into the prediction ledger.

### Seat 1 · Same work

**1. Abu Sebastian** — IBM Research Zurich · [profile](https://research.ibm.com/people/abu-sebastian) · [DBLP](https://dblp.org/search?q=Abu%20Sebastian)
- **Why:** flag-bearer of analog in-memory computing on phase-change memory, and geographically my nearest authority. How his view of "can analog IMC scale to a full system" shifts is the field's weather vane.
- **Follow:** the Nature-family papers (device review 2020, the 64-core PCM chip 2023, the analog-AI speech chip 2023), his ISSCC and IEDM invited talks, and the IBM Research blog posts that accompany each chip.
- **Log:** his stated position on ADC overhead, conductance drift and accuracy at system scale; any sentence of the form "analog IMC is / is not the right choice for X".

**2. Naveen Verma** — Princeton; founder of EnCharge AI · [Princeton](https://ee.princeton.edu/people/naveen-verma) · [EnCharge AI](https://www.encharge.ai/) · [DBLP](https://dblp.org/search?q=Naveen%20Verma)
- **Why:** the live sample of IMC moving from papers to product. The gap between how he writes it in papers and how the company ships it is information.
- **Follow:** his SSC Magazine overview (2019), the bit-scalable IMC microprocessor (JSSC 2020), the charge-domain IMC papers, EnCharge's product announcements and any independent benchmark of their silicon.
- **Log:** product claims (EN100 and successors) versus the papers; what got dropped on the way to a product; the precision and accuracy he commits to in public.

**3. Meng-Fan Chang** — National Tsing Hua University, Hsinchu; TSMC · [DBLP](https://dblp.org/search?q=Meng-Fan%20Chang)
- **Why:** the main source of IMC macros at ISSCC. Reading him is how I learn the real interface and constraints of a macro, the part my GVSoC in-memory-accelerator model has to respect.
- **Follow:** every ISSCC and JSSC CIM macro paper since 2018 (ReRAM nvCIM first, then SRAM CIM, then digital CIM), the ISSCC CIM tutorials he co-presents.
- **Log:** macro interface conventions (bit-serial versus bit-parallel, how input and output precision are exposed); how precision, area and TOPS/W targets move year on year.

**4. Marian Verhelst** — KU Leuven MICAS · [MICAS](https://www.esat.kuleuven.be/micas/) · [ZigZag](https://github.com/KULeuven-MICAS/zigzag) · [Stream](https://github.com/KULeuven-MICAS/stream) · [DBLP](https://dblp.org/search?q=Marian%20Verhelst)
- **Why:** ZigZag and Stream are the closest parallel to my tile-mesh SoC modelling and Deeploy work. My most direct competitor-and-collaborator, European, with the judgment frame nearest to my own environment.
- **Follow:** ZigZag (IEEE TC 2021), Stream (IEEE TC 2025), DIANA (ISSCC 2022), the MICAS GitHub organisation, her DATE and ISSCC keynotes.
- **Log:** her stance on layer fusion versus tiling, on where analog IMC fits inside a heterogeneous SoC, and on which DSE abstractions survive contact with silicon.

**5. Joel Emer & Vivienne Sze** — MIT · [Emer](https://people.csail.mit.edu/emer/) · [EEMS group](https://www.rle.mit.edu/eems/) · [Timeloop](https://github.com/NVlabs/timeloop) · [Accelergy](https://github.com/Accelergy-Project/accelergy) · [CiMLoop](https://github.com/mit-emze/cimloop)
- **Why:** Timeloop, Accelergy and CiMLoop define how the field models accelerators and CIM. Emer is one of the people with the best taste in the field; every keynote of his is worth watching in full.
- **Follow:** Timeloop (ISPASS 2019), Accelergy (ICCAD 2019), CiMLoop (ISPASS 2024), the book *Efficient Processing of Deep Neural Networks* (2020), the Eyeriss tutorial material, and the three repositories above.
- **Log:** Emer's framing of what a good model must capture; which abstractions he keeps and which he throws away; any claim about the accuracy ceiling of analytical models.

**6. Tushar Krishna** — Georgia Tech · [home](https://tusharkrishna.ece.gatech.edu/) · [MAESTRO](https://github.com/maestro-project/maestro) · [SCALE-Sim](https://github.com/scalesim-project/scale-sim-v2)
- **Why:** MAESTRO and on-chip interconnect. The data-movement problem of multi-macro and multi-tile systems is studied most deeply by him, and that is exactly the problem of the tile mesh I model.
- **Follow:** the data-centric dataflow paper (MICRO 2019, MAESTRO in IEEE Micro 2020), SCALE-Sim (ISPASS 2020), his NoC and chiplet papers, his ISCA and MICRO tutorials.
- **Log:** his position on NoCs for multi-accelerator and chiplet systems; which interconnect topologies he predicts will win for LLM decoding.

**7. Francesco Conti & Alessio Burrello** — Bologna; Turin · [Conti](https://www.unibo.it/sitoweb/f.conti/en) · [Burrello, DBLP](https://dblp.org/search?q=Alessio%20Burrello) · [Deeploy](https://github.com/pulp-platform/Deeploy) · [DORY](https://github.com/pulp-platform/dory) · [PULP platform](https://pulp-platform.org/)
- **Why:** DORY and Deeploy are PULP's own deployment flow. My tools must talk to theirs, and their roadmap decides which accelerators get first-class support.
- **Follow:** DORY (IEEE TC 2021), Deeploy (IEEE TCAD 2024), XNOR Neural Engine (TCAD 2018), the Siracusa SoC papers, and above all the Deeploy pull requests and release notes.
- **Log:** where Deeploy's tiling and memory allocation go next; which accelerators and which precisions they commit to; what they say about LLM deployment on microcontrollers.

**8. Jonathan Ragan-Kelley** — MIT · [home](https://people.csail.mit.edu/jrk/) · [Halide](https://halide-lang.org/) · [Exo](https://github.com/exo-lang/exo)
- **Why:** Halide and Exo. User-controlled scheduling is the line closest to the IMC mapping problem and to my retrieval + composition thesis in AutoKernel.
- **Follow:** Halide (PLDI 2013), Exocompilation (PLDI 2022), the learned Halide autoscheduler (SIGGRAPH 2019), Exo's commit history and the papers that build on it.
- **Log:** his stance on user-controlled versus automatic scheduling; any claim about how much of accelerator programming can be externalised from the compiler.

**9. Chris Lattner** — Modular · [home](https://nondot.org/sabre/) · [MLIR](https://mlir.llvm.org/) · [Modular blog](https://www.modular.com/blog)
- **Why:** the source of MLIR. His judgment of what compiler infrastructure should look like defines the tools I will end up using, and MLIR is the foundation under xDSL, my comparison baseline.
- **Follow:** the MLIR paper (CGO 2021), his ASPLOS 2021 keynote on the golden age of compiler design, the "Democratizing AI Compute" blog series, Mojo and MAX release notes.
- **Log:** his predictions about who owns the AI software stack and whether a portable compiler stack can break the CUDA moat.

**10. Tianqi Chen** — CMU · [home](https://tqchen.com/) · [TVM](https://tvm.apache.org/) · [MLC-LLM](https://github.com/mlc-ai/mlc-llm)
- **Why:** TVM and MLC-LLM: the complete sample of an academic compiler becoming a product deployment path.
- **Follow:** TVM (OSDI 2018), learning to optimise tensor programs (NeurIPS 2018), TensorIR (ASPLOS 2023), the MLC-LLM releases and the models they claim to run on phones.
- **Log:** how MLC's on-device LLM claims evolve; what he gives up when going to product; which hardware backends he drops.

### Seat 2 · Different interests

**11. Bill Dally** — NVIDIA, chief scientist · [NVIDIA Research](https://research.nvidia.com/person/bill-dally) · [Hot Chips](https://hotchips.org/) · [GTC](https://www.nvidia.com/gtc/)
- **Why:** every public talk of his says the real bottleneck is data movement. That is the first ruler to hold against any accelerator claim, including my own.
- **Follow:** *Domain-specific hardware accelerators* (CACM 2020), his Hot Chips keynotes, his yearly GTC talk, his energy-per-operation tables.
- **Log:** the energy-per-operation numbers he quotes; his view on precision scaling (FP8 to FP4 and below); any statement about what specialised accelerators cannot beat GPUs at.

**12. Jim Keller** — Tenstorrent · [Tenstorrent](https://tenstorrent.com/) · [talks](https://www.youtube.com/results?search_query=Jim+Keller+Tenstorrent+architecture)
- **Why:** watch how he talks about the economics of architecture choices, and about RISC-V as the base of an AI company.
- **Follow:** Tenstorrent architecture talks and documentation, "Moore's Law is not dead" (Berkeley EECS colloquium 2019), long-form interviews.
- **Log:** his claims on RISC-V and open AI hardware economics; Tenstorrent's roadmap versus what ships; his statements on where SRAM-resident inference wins.

**13. Dylan Patel** — SemiAnalysis · [SemiAnalysis](https://semianalysis.com/)
- **Why:** semiconductor economics: what technology actually gets paid for. He is the opposite of a reviewer: he only cares whether it sells.
- **Follow:** the newsletter, especially the pieces on inference economics, HBM and 3D-DRAM supply, and accelerator start-ups.
- **Log:** his calls on which accelerator start-ups get bought or die; his inference cost models; his view of in-memory and near-memory computing as businesses.

**14. Song Han** — MIT · [HAN Lab](https://hanlab.mit.edu/) · [AWQ](https://github.com/mit-han-lab/llm-awq) · [MCUNet](https://mcunet.mit.edu/)
- **Why:** quantisation and model compression. My workload constraints come from him. His incentive is accuracy per bit, not hardware elegance, which is exactly why he sits in this seat rather than in seat 1.
- **Follow:** Deep Compression (ICLR 2016), EIE (ISCA 2016), MCUNet (NeurIPS 2020), SmoothQuant (ICML 2023), AWQ (MLSys 2024), and the HAN Lab GitHub organisation.
- **Log:** the bit-width floor he believes in for LLM weights and activations; which workloads he treats as the edge target; his claims about sparsity versus quantisation.

### Seat 3 · Opposite conclusions

**15. Sara Hooker** — author of *The Hardware Lottery* · [home](https://www.sarahooker.me/) · [The Hardware Lottery, arXiv](https://arxiv.org/abs/2009.06489)
- **Why:** hardware decides which algorithms get to win. A sobering read for anyone building specialised hardware.
- **Follow:** the essay (CACM 2021), her follow-up writing on compute and research incentives, her talks.
- **Log:** her claims about which research directions hardware has suppressed; use as an annual stress test of my own direction.

**Known gap.** The opposite-conclusions seat holds one person. The standing counter-arguments below cover the rest for now. A second person belongs here when I find one with a track record: a GPU-side architect who argues in public against specialisation, or an analog-IMC sceptic whose predictions have already come true once.

## The bench

Candidates to rotate in. Same groups as the fifteen.

**IMC core (same work)**

- **Shimeng Yu**, Georgia Tech · [home](https://shimeng.ece.gatech.edu/) · [NeuroSim](https://github.com/neurosim). Device-to-architecture modelling; my cost model needs to know how the device layer thinks. Follow NeuroSim releases and his CIM review (IEEE CAS Magazine 2021). Log: his device roadmap claims.
- **Daniele Ielmini**, Politecnico di Milano · [home](https://ielmini.faculty.polimi.it/) · [DBLP](https://dblp.org/search?q=Daniele%20Ielmini). RRAM and IMC device physics, local to Europe. Follow *In-memory computing with resistive switching devices* (Nature Electronics 2018) and his IEDM papers. Log: his claims on RRAM endurance and variability limits.
- **Jae-sun Seo**, Cornell · [DBLP](https://dblp.org/search?q=Jae-sun%20Seo). Works on both digital and analog IMC, a balanced view. Follow XNOR-SRAM and C3SRAM (JSSC 2020) and his later digital CIM chips. Log: which side he leans to each year.

**Accelerator architecture and design-space exploration (methodology)**

- **Sophia Shao**, Berkeley · [home](https://people.eecs.berkeley.edu/~ysshao/) · [Gemmini](https://github.com/ucb-bar/gemmini). Gemmini and chiplets; agile hardware and open-source accelerators, a useful contrast to the PULP route. Follow Gemmini (DAC 2021) and her chiplet papers. Log: her claims on how much the agile flow buys.
- **Onur Mutlu**, ETH Zurich · [home](https://people.inf.ethz.ch/omutlu/) · [lectures](https://www.youtube.com/@OnurMutluLectures) · [PIM primer](https://arxiv.org/abs/2012.03112). PIM and memory-centric computing, the cousin of IMC. Calibrates my overall understanding of moving compute next to memory. Follow the primer, the UPMEM benchmarking paper (IEEE Access 2022) and the ISCA memory-centric computing workshop. Log: his predictions on when PIM reaches commodity DRAM.
- **Hadi Esmaeilzadeh**, UC San Diego · [home](https://cseweb.ucsd.edu/~hadi/). Accelerators crossed with ML systems; very good nose for topics. Follow *Dark silicon* (ISCA 2011), Bit Fusion (ISCA 2018) and whatever he picks next. Log: the topic he moves to.

**Compilers and runtime (my other half)**

- **Albert Cohen**, Google · [DBLP](https://dblp.org/search?q=Albert%20Cohen%20Tensor%20Comprehensions). MLIR and polyhedral compilation; European background, the deepest theory of the group. Follow Tensor Comprehensions (2018), the MLIR paper and his CGO and PLDI work. Log: his claims on what polyhedral methods can and cannot schedule.
- **Fredrik Kjolstad**, Stanford · [home](https://fredrikbk.com/) · [TACO](http://tensor-compiler.org/). Sparse compilation. Sparsity is what IMC handles badly; I need to know how the compiler side thinks about it. Follow TACO (OOPSLA 2017) and its successors. Log: his claims on sparse formats and hardware.

**HPC side (different interests)**

- **Torsten Hoefler**, ETH Zurich · [home](https://htor.inf.ethz.ch/) · [SPCL](https://spcl.inf.ethz.ch/). My community's reading stream keeps returning to his group: low-precision emulation of FP64 (the Ozaki scheme line), collectives, and the question of whether GPUs stay indispensable. Follow his arXiv output and SC keynotes. Log: his claims on which precision formats survive.

**Industry reality (different interests)**

- **Chips and Cheese** · [site](https://chipsandcheese.com/). Micro-architecture reverse measurement. Teaches judging by real measurements instead of vendor slides. Follow every deep dive on an inference accelerator. Log: measured versus claimed numbers.
- **Hot Chips, all talks, every year** · [site](https://hotchips.org/). Industry puts what it actually built here. Read against ISCA; the difference is academia's blind spot. Log: which academic ideas appear in silicon and how many years later.
- **d-Matrix** · [site](https://www.d-matrix.ai/), **Axelera AI** · [site](https://www.axelera.ai/), **EnCharge AI** · [site](https://www.encharge.ai/). Three different bets on commercialising IMC: digital SRAM chiplets with 3D-stacked DRAM, digital IMC with RISC-V at the edge, analog charge-domain. Follow technical blogs, funding news, roadmap changes. Log: each roadmap promise with its date.

## Standing counter-arguments

Re-read once a year. After each, write one paragraph on whether my current work survives it.

| Text | Claim against me | Year | Link |
|------|------------------|------|------|
| Sara Hooker, *The Hardware Lottery* | Hardware chooses the winning algorithms; a specialised design may be optimising for a loser | 2020 | [arXiv](https://arxiv.org/abs/2009.06489) |
| Richard Sutton, *The Bitter Lesson* | General compute plus scale beats clever design; IMC is a clever design | 2019 | [essay](http://www.incompleteideas.net/IncIdeas/BitterLesson.html) |
| Fuchs and Wentzlaff, *The Accelerator Wall: Limits of chip specialization*, HPCA | The returns to specialisation have a ceiling | 2019 | [DBLP](https://dblp.org/search?q=The%20Accelerator%20Wall) |
| The analog-IMC commercialisation record, Mythic first | Collect their technical claims from 2018–2021, then read what happened in 2022–2023 (near-shutdown, bridge round, new leadership). The cheapest counter-example material for taste training. | ongoing | [Mythic](https://mythic.ai/) |

## Calibration signals more reliable than people

- **IEEE Micro Top Picks** · [IEEE Micro](https://www.computer.org/csdl/magazine/mi). Each year a dozen papers chosen from all the architecture conferences, a snapshot of the field's collective taste. Write my own Top Picks guess before the list comes out and grade it.
- **Test-of-Time awards** · [ISCA Influential Paper Award](https://www.sigarch.org/benefit/awards/influential-isca-paper-award/) · [MICRO](https://www.microarch.org/). What is still standing ten years later. For each winner ask: could it have been seen at the time, and on what evidence?
- **The IMC sessions at ISSCC and VLSI** · [ISSCC](https://www.isscc.org/) · [VLSI Symposium](https://www.vlsisymposium.org/). Count each year: how many papers, analog versus digital, how area and precision metrics move. The hardest data on IMC trends. Table at the end of this file.
- **Full review records on OpenReview** · [OpenReview](https://openreview.net/) · [MLSys](https://mlsys.org/). How senior reviewers take a paper apart.
- **Keynotes at the main conferences.** What senior people say about "the next five years" exposes their taste better than their papers do. DAC, DATE, ISSCC plenaries, Hot Chips, MLSys, the RISC-V Summit.

## What my community's reading stream focuses on

Derived from the subject lines of a group mailing list I am subscribed to, roughly 130 threads between late May and 20 October 2026 (three sampled windows; about three weeks in late July and early August not sampled; nothing before May). Aggregated by theme. No individual messages, names, internal links or unpublished work are recorded here; only public papers and products that were shared on the list.

**The ten themes, by how often they recur**

1. **LLM inference as a data-movement problem.** KV-cache fabrics on NoCs, prefill/decode disaggregation with near-memory processing, MoE decoding on scratchpad accelerators, edge MoE serving, vector-quantised decoding, software-defined dataflow machines from hyperscalers, "on-device versus datacenter" position pieces, and surveys of AI datacenter hardware. Representative public papers: [MeshKV](https://arxiv.org/abs/2609.19207), [hybrid GPU + processing-near-memory for prefill/decode](https://arxiv.org/abs/2610.26131), [multi-engine MoE decoding on scratchpad accelerators](https://arxiv.org/abs/2609.21137), [a survey on AI datacenter hardware](https://arxiv.org/abs/2609.26829), [CHIPSMORE compute-in-interconnect-and-memory chiplets](https://arxiv.org/abs/2608.30509).
2. **3D integration.** Logic-on-logic "tau scaling", 3D-stacked DRAM on logic for inference, 3D chiplet floorplanning, wafer-to-wafer hybrid bonding pitch, UCIe link analysis, 3D-IC benchmark suites and PDKs, packaging webinars. The explicit comment on the list was that most research plans now have a 3D component.
3. **Low-precision arithmetic formats.** FP8, FP4, MXFP4, NVFP4, the IEEE P3109 format standard, ternary LLMs, INT4 instruction sets, block-size ablations, near-memory dequantisation, and the Ozaki-scheme line that emulates FP64 with INT8 or FP4 tensor cores. Representative: [multi-format systolic array with micro-scaling](https://arxiv.org/abs/2610.19645), [BitNet inference with signed-INT4 instructions](https://arxiv.org/abs/2609.27453), [FP64 from FP4/6/8 via Ozaki scheme II](https://arxiv.org/abs/2609.37693).
4. **Physical AI and embodied workloads as the design driver.** Robotic foundation models, embodied memory for vision-language-action models, JEPA world models, looped and recurrent transformers for robotics, visual-inertial odometry, Kalman filters on edge NPUs, energy characterisation of vision-language models at the edge, and a special session on circuits for agentic AI and embodied robotics. Representative: [π0.7](https://arxiv.org/abs/2604.15483), [LeWAM](https://arxiv.org/abs/2610.12818), [VLM inference energy on edge platforms](https://arxiv.org/abs/2610.20136), [decoding looped transformers](https://arxiv.org/abs/2610.02185).
5. **RISC-V vector and core microarchitecture.** Tiled-ALU grids, long-vector register files, software-managed higher-level cache for vectors, multithreaded RVV, RVV 1.0 HPC benchmarks, out-of-order vector processors, FPGA-optimal minimal cores, memory ordering, precise exceptions, and "how to design an ISA". Representative: [TALU](https://arxiv.org/abs/2610.19277), [SVRF](https://arxiv.org/abs/2610.07078), [CacheFlex](https://arxiv.org/abs/2610.12940), [minimum RISC-V for FPGA](https://arxiv.org/abs/2610.21552), [TEMPO memory ordering](https://arxiv.org/abs/2609.22743).
6. **Interconnect, collectives and multi-engine synchronisation.** Express meshes with deadlock-free adaptive routing, small-world fabrics for neuromorphic multicore, unified xPU interconnection across host domains, orchestration separated from the collective datapath, collective-algorithm synthesisers, barrier-free synchronisation for multi-engine accelerators, co-packaged optics, and a tutorial on NoC exploration with GVSoC. Representative: [Co-Fabric](https://arxiv.org/abs/2609.25560), [Purlin](https://arxiv.org/abs/2609.36954), [small-world fabrics](https://arxiv.org/abs/2608.24351).
7. **Memory-centric computing.** Compiling dynamic programming to 3D-DRAM PIM, hybrid GPU and processing-near-memory, memristive CIM for open-source chips, memory-system simulators, embedded-memory roadmaps, the ISSCC CIM tutorial, and workshops on memory-centric computing. Representative: [semi-ring dynamic programming on tier-aware 3D-DRAM PIM](https://arxiv.org/abs/2610.09156).
8. **AI agents for hardware design and co-design loops.** Conversational RTL design-space exploration, autonomous research loops that mutate a core's microarchitecture, accelerators designed end to end by agents, agentic hardware-software co-optimisation, agentic DSE for heterogeneous edge SoCs, compilers that hardwire an LLM into silicon, open PDKs with open-source flows. Representative: [CRADLE](https://arxiv.org/abs/2508.08709), [SparseCraft](https://arxiv.org/abs/2610.05037), [agentic DSE for heterogeneous edge SoCs](https://arxiv.org/abs/2610.07191).
9. **Reliability and silent data corruption.** Intra-thread instruction checking for defect-induced silent errors, lightweight checksums for CNN inference at the edge, GPU fault resilience, error sensitivity in homomorphic computing, process-induced degradation in 3.5D packages, and a keynote on reliable systems for embodied AI.
10. **Model-side changes that move the hardware target.** Looped transformers, flow reasoning models, online memory for LLMs, state-space versus transformer debates, full-to-sparse attention transfer, on-device neural architecture search, time-series foundation models, function-based extreme weight compression.

**Industry signals the stream watches.** Huawei (3D "tau" scaling papers, Ascend NPU scheduling, an open unified-bus implementation), d-Matrix (3D-stacked DRAM), Tenstorrent (SRAM-resident speculative decoding, a bit-exact full-system simulator), Microsoft Maia, AMD Instinct, Google TPU, OpenAI's inference chip commentary, SK hynix near-memory dequantisation, Meta Reality Labs system modelling for wearables, Intel and SMIC process teardowns, Arm's "AGI" CPU, and NPU-IP start-ups.

**Venues the community actually attends and reports on.** DATE, ISSCC, CICC, ESSERC, AICAS, VLSI-SoC, ESWEEK-CASES, ASAP, DFTS, EUSIPCO, ISCAS, the RISC-V Summit, COINS, Hot Chips, the ISCA memory-centric computing workshop, and ICLR on the ML side.

**What this changes on my radar**

- **3D integration and low-precision formats are missing from my fifteen.** Both are treated by the community as settled directions, not open questions. Watch-themes, not people, for now: follow the Hot Chips and ISSCC 3D-DRAM sessions and the IEEE P3109 working group; add a person when one emerges as the reference.
- **Physical AI is the group's framing, not mine.** My own framing is edge LLM. The two meet at the tile mesh: robot-control workloads are small models with hard latency bounds and heavy data movement, which is exactly what the tile-mesh SoC is being modelled for. I should read the robotics papers for their workload shape, not their algorithms.
- **Agentic co-design loops are the fastest-growing theme and the one closest to AutoKernel.** An agent that proposes a microarchitectural hypothesis, runs it through a simulator and keeps or discards it is my retrieval + composition pipeline with the matcher replaced by a model. This is both a threat to and an argument for the thesis; it belongs in the prediction ledger.
- **Interconnect and collectives are where the community is closest to Tushar Krishna's seat.** My tile-mesh NoC work has more readers in the group than my CIM work does.

## Feeds (not deep follows)

Read these on a schedule, never more than the time box allows.

- Industry: [SemiAnalysis](https://semianalysis.com/), [Chips and Cheese](https://chipsandcheese.com/), [Fabricated Knowledge](https://www.fabricatedknowledge.com/), [The Chip Letter](https://thechipletter.substack.com/), [Asianometry](https://www.asianometry.com/), [The Next Platform](https://www.nextplatform.com/)
- Academic community: [SIGARCH Computer Architecture Today](https://www.sigarch.org/blog/), [MLIR on LLVM Discourse](https://discourse.llvm.org/c/mlir/31), [LLVM Developers' Meeting talks](https://llvm.org/devmtg/), [PyTorch dev-discuss](https://dev-discuss.pytorch.org/)
- AI trends: [Interconnects](https://www.interconnects.ai/), [Import AI](https://importai.substack.com/), [Epoch AI](https://epoch.ai/), [Ahead of AI](https://magazine.sebastianraschka.com/)
- Paper stream: [arXiv cs.AR](https://arxiv.org/list/cs.AR/recent), [arXiv cs.PL](https://arxiv.org/list/cs.PL/recent), filtered on *in-memory computing*, *tiling*, *code generation*, *edge LLM*, *RISC-V accelerator*, *3D-stacked DRAM*, *microscaling*
- Upstream code: [Deeploy](https://github.com/pulp-platform/Deeploy), [GVSoC](https://github.com/gvsoc/gvsoc), [FlooNoC](https://github.com/pulp-platform/FlooNoC), [Snitch cluster](https://github.com/pulp-platform/snitch_cluster)

## Cadence

| When | What | Time box |
|------|------|----------|
| Weekly | One keynote or long talk from the fifteen; two newsletters; one arXiv scan; skim the community reading stream for new themes | 2 h |
| Monthly | Reverse citations on five seed papers (Deeploy, ZigZag, CiMLoop, the 64-core PCM chip, Exo): who cites them now, from which group, asking what | 1 h |
| Quarterly | Write three dated predictions of my own into the ledger; update the theme list above | 30 min |
| Yearly | Re-read the standing counter-arguments; count the ISSCC and VLSI IMC sessions; grade my Top Picks guess; prune the fifteen | half a day |
| Every two years | Grade the prediction ledger, theirs and mine | half a day |

## Prediction ledger

Rules: one row per prediction. Quote or paraphrase closely, name the source and the date, give the horizon the speaker gave, and set a check-by date. Grade only on the check-by date. The first rows are standing theses paraphrased from memory; verify each against the source before grading.

| Logged | Who | Where said | Prediction (paraphrase) | Horizon | Check by | Outcome | What it taught me |
|--------|-----|------------|--------------------------|---------|----------|---------|-------------------|
| 2026-10-20 | Bill Dally | Hot Chips 2023 keynote and later GTC talks | Energy is dominated by data movement, not arithmetic; the next gains come from locality and lower precision, not faster MACs | standing thesis | 2028-10 | open | |
| 2026-10-20 | Naveen Verma / EnCharge AI | company announcements 2025 | Analog charge-domain IMC reaches a shipping client product with competitive TOPS/W at usable accuracy | 2025–2027 | 2028-10 | open | |
| 2026-10-20 | Chris Lattner | Modular's "Democratizing AI Compute" series, 2025 | The CUDA moat is broken by a portable compiler stack, not by a competing chip | 3–5 years | 2028-10 | open | |
| 2026-10-20 | Community reading stream | shared papers, mid 2026 | 3D-stacked DRAM on logic becomes the default memory for inference accelerators announced at Hot Chips | 2–3 years | 2028-10 | open | |
| 2026-10-20 | Me | this file | Tile-level and above integration of digital CIM, with compiler support for its job queues, appears at DAC/DATE as a recognisable sub-topic (three or more papers in one year) | 2 years | 2028-10 | open | |
| 2026-10-20 | Me | this file | An agentic co-design loop (model proposes, simulator scores) outperforms a hand-written kernel library on at least one PULP target in a peer-reviewed paper | 2 years | 2028-10 | open | |
| | | | | | | | |

## IMC session counter

Fill from the ISSCC and VLSI programmes each year.

| Year | ISSCC IMC papers | of which analog | of which digital | VLSI IMC papers | Best reported TOPS/W (precision stated) | Notes |
|------|-----------------:|----------------:|-----------------:|----------------:|-----------------------------------------|-------|
| 2024 | | | | | | |
| 2025 | | | | | | |
| 2026 | | | | | | |
| 2027 | | | | | | |
