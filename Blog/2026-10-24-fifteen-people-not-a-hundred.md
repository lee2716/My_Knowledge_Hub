---
title: "Fifteen People, Not a Hundred: How I Try to Keep My Research Taste Honest"
date: 2026-10-24
tags: [research, accelerators, in-memory-computing, compilers, reading]
---

I work on the boundary between hardware and software for small, energy-constrained AI systems: cycle-level simulation of new accelerators on one side, compilers that turn neural networks into bare-metal code on the other. It is a field where the ground moves quickly, and where it is easy to mistake the consensus of one's own lab for the consensus of the world.

This post is about a small practice I started this autumn to guard against that: a short, deliberately balanced list of people whose work I follow closely, a few texts I re-read every year, and a notebook of predictions that I intend to grade against reality. None of it is original. I am writing it down because the act of writing it down is most of the value, and because I would be glad to hear who you would add.

## Why a list, and why a short one

Most of us already follow far more people than we can actually read. The feed does the choosing, and the feed optimises for what is new rather than for what will matter. A list is the opposite move: I choose a small number of people and commit to reading their work properly, including the parts that are inconvenient for my own agenda.

I settled on fifteen. Fifteen is enough to cover the few sub-fields I genuinely need to understand, and small enough that "follow deeply" can mean something concrete: read their major papers end to end, watch their keynotes rather than skim the slides, and write down the predictions they make in public so that I can look back in two years and see who read the future well. Somewhere past twenty, in my experience, a list quietly turns back into a feed.

## Three seats

The part of the list I care most about is its shape. It has three seats, and I try to keep all three filled.

**People doing what I do.** They are the obvious ones: the researchers whose papers I would cite in my own related-work section. They keep me technically honest and show me the current best practice. A list made only of them, however, tends to confirm what my group already believes. I have come to think of this seat as necessary but not sufficient.

**People whose incentives differ from mine.** Engineers at chip companies, people who write about the economics of semiconductors, researchers on the algorithm side who care about accuracy per bit rather than about elegant hardware. They see constraints that are hard to see from inside a university: what ships, what gets paid for, what a model team will actually tolerate. I find their questions bracing in the best sense.

**People whose conclusions differ from mine.** This is the seat I find hardest to fill and most valuable when it is filled. If someone has argued carefully that specialised hardware has diminishing returns, or that hardware tends to decide which algorithms get a fair hearing, then I owe that argument my most careful reading, not my quickest rebuttal. These are the people who show me where my own assumptions need the most care.

## The fifteen

Here is the current list, with a sentence on why each person is on it and what I pay attention to. Pairs who publish as one lab count as a single seat. The links go to home pages where I am sure of them and to DBLP searches where I am not.

### Doing what I do

- **[Abu Sebastian](https://research.ibm.com/people/abu-sebastian)** (IBM Research Zurich). The leading voice on analog in-memory computing with phase-change memory. I follow the Nature-family chip papers and his invited talks, and I pay particular attention to how he describes the path from a macro to a full system.
- **[Naveen Verma](https://ee.princeton.edu/people/naveen-verma)** (Princeton, founder of [EnCharge AI](https://www.encharge.ai/)). A rare example of in-memory computing travelling from papers to a product. Reading his academic work alongside the company's announcements teaches me what survives the trip.
- **[Meng-Fan Chang](https://dblp.org/search?q=Meng-Fan%20Chang)** (NTHU and TSMC). The most consistent source of compute-in-memory macros at ISSCC. His papers are how I learn what a real macro's interface and constraints look like, which my own simulation models have to respect.
- **[Marian Verhelst](https://www.esat.kuleuven.be/micas/)** (KU Leuven). [ZigZag](https://github.com/KULeuven-MICAS/zigzag) and [Stream](https://github.com/KULeuven-MICAS/stream) are the closest relatives of my own design-space-exploration work, and her group also builds hybrid digital and analog silicon. I follow the repositories as closely as the papers.
- **[Joel Emer](https://people.csail.mit.edu/emer/) and [Vivienne Sze](https://www.rle.mit.edu/eems/)** (MIT). [Timeloop](https://github.com/NVlabs/timeloop), [Accelergy](https://github.com/Accelergy-Project/accelergy) and [CiMLoop](https://github.com/mit-emze/cimloop) define how much of the field models accelerators. Emer's keynotes are, for me, a masterclass in choosing abstractions, and I watch them in full.
- **[Tushar Krishna](https://tusharkrishna.ece.gatech.edu/)** (Georgia Tech). [MAESTRO](https://github.com/maestro-project/maestro), [SCALE-Sim](https://github.com/scalesim-project/scale-sim-v2) and a long line of work on on-chip interconnect. Data movement between many compute tiles is the problem I spend most of my days on, and he has thought about it longer than almost anyone.
- **[Francesco Conti](https://www.unibo.it/sitoweb/f.conti/en) and [Alessio Burrello](https://dblp.org/search?q=Alessio%20Burrello)** (Bologna and Turin). [DORY](https://github.com/pulp-platform/dory) and [Deeploy](https://github.com/pulp-platform/Deeploy) are the deployment flows my own tools must work with. I follow the pull requests as well as the papers, because the roadmap lives in the code.
- **[Jonathan Ragan-Kelley](https://people.csail.mit.edu/jrk/)** (MIT). [Halide](https://halide-lang.org/) and [Exo](https://github.com/exo-lang/exo) make the case that programmers should control the schedule and let the compiler check it. That idea is very close to how I think about kernel generation for accelerators.
- **[Chris Lattner](https://nondot.org/sabre/)** (Modular). [MLIR](https://mlir.llvm.org/) underlies the infrastructure my compiler experiments compare against, and his writing on the [Modular blog](https://www.modular.com/blog) is an unusually candid account of what it takes to build an AI software stack.
- **[Tianqi Chen](https://tqchen.com/)** (CMU). [TVM](https://tvm.apache.org/) and [MLC-LLM](https://github.com/mlc-ai/mlc-llm) are a complete story of an academic compiler becoming something people deploy on their phones. I watch which backends and which claims persist release after release.

### Incentives that differ from mine

- **[Bill Dally](https://research.nvidia.com/person/bill-dally)** (NVIDIA). His talks return, year after year, to the same point: the energy goes into moving data, not into arithmetic. I treat that as the first question to ask of any accelerator proposal, my own included.
- **Jim Keller** ([Tenstorrent](https://tenstorrent.com/)). I listen to him for the economics of architecture decisions and for an industry view of RISC-V as a foundation for AI hardware. He says what he thinks, and he has been right often enough to be worth the time.
- **Dylan Patel** ([SemiAnalysis](https://semianalysis.com/)). His question is never whether a technology is elegant but whether someone will pay for it. For a researcher that is an uncomfortable and extremely useful lens.
- **[Song Han](https://hanlab.mit.edu/)** (MIT). Quantisation and compression research that sets the workload constraints I design against. His group's interests are in accuracy per bit; mine are in what hardware can do with those bits. That difference is exactly why he belongs in this seat.

### Conclusions that differ from mine

- **[Sara Hooker](https://www.sarahooker.me/)**. [*The Hardware Lottery*](https://arxiv.org/abs/2009.06489) argues that hardware has quietly decided which ideas get a fair chance. For anyone building specialised hardware it is a thoughtful, well-argued reminder to check whether we are helping or narrowing the space of ideas.

This seat is still under-filled, and I know it. I would welcome suggestions: an architect who argues in public that general-purpose compute will keep winning, or a thoughtful sceptic of analog in-memory computing whose earlier predictions have held up.

## The bench

A few people I read regularly and would rotate in if a seat opened: [Shimeng Yu](https://shimeng.ece.gatech.edu/) and [Daniele Ielmini](https://ielmini.faculty.polimi.it/) for the device layer under in-memory computing; [Jae-sun Seo](https://dblp.org/search?q=Jae-sun%20Seo) for a balanced view of digital and analog approaches; [Sophia Shao](https://people.eecs.berkeley.edu/~ysshao/) for agile, open hardware; [Onur Mutlu](https://people.inf.ethz.ch/omutlu/) for processing in memory, the close cousin of my own topic; [Hadi Esmaeilzadeh](https://cseweb.ucsd.edu/~hadi/) for a consistently good sense of which problems are about to matter; [Albert Cohen](https://dblp.org/search?q=Albert%20Cohen%20Tensor%20Comprehensions) and [Fredrik Kjolstad](https://fredrikbk.com/) for the deep end of compiler theory; [Torsten Hoefler](https://htor.inf.ethz.ch/) for the HPC view of precision and collectives; and, on the industry side, [Chips and Cheese](https://chipsandcheese.com/) for careful measurement, the full [Hot Chips](https://hotchips.org/) programme every year, and the public roadmaps of [d-Matrix](https://www.d-matrix.ai/), [Axelera AI](https://www.axelera.ai/) and [EnCharge AI](https://www.encharge.ai/), three quite different bets on commercialising in-memory computing.

## Texts I re-read once a year

Some arguments deserve a standing appointment rather than a one-time read. Each year I return to these and write a paragraph on how my current work looks in their light:

- [*The Hardware Lottery*](https://arxiv.org/abs/2009.06489) (Hooker, 2020), on how hardware shapes which ideas succeed.
- [*The Bitter Lesson*](http://www.incompleteideas.net/IncIdeas/BitterLesson.html) (Sutton, 2019), on the long record of general methods plus compute outlasting hand-crafted structure.
- [*The Accelerator Wall*](https://dblp.org/search?q=The%20Accelerator%20Wall) (Fuchs and Wentzlaff, HPCA 2019), on the limits of what specialisation alone can deliver.
- The history of the first wave of analog in-memory computing companies, [Mythic](https://mythic.ai/) among them. Their early technical talks are excellent, and their later years were harder than those talks anticipated. Reading the two side by side is a generous and inexpensive way to learn how much of a roadmap is physics and how much is hope.

## Signals that do not depend on any one person

People are the richest source of judgment, but a few institutional signals are steadier:

- **IEEE Micro Top Picks**, a yearly selection from across the architecture conferences. I write down my own guess before the list appears and grade it afterwards.
- **Test-of-time awards**, such as the [ISCA Influential Paper Award](https://www.sigarch.org/benefit/awards/influential-isca-paper-award/). For each winner I ask: could this have been recognised at the time, and on what evidence?
- **The in-memory computing sessions at [ISSCC](https://www.isscc.org/) and the [VLSI Symposium](https://www.vlsisymposium.org/)**, counted each year: how many papers, how the balance between analog and digital shifts, how the reported metrics move.
- **Public review records on [OpenReview](https://openreview.net/)**, where one can watch experienced reviewers take a paper apart with care.
- **Keynotes.** When senior people describe the next five years, they tend to reveal more of their taste than their papers do.

## What my community keeps returning to

I am fortunate to sit in a research community that shares a steady stream of papers and news. Looking back over roughly five months of what was shared, ten themes recur: large-model inference treated as a data-movement problem; 3D integration, from logic-on-logic stacking to DRAM on logic; low-precision arithmetic formats and the standards forming around them; physical AI and robotics workloads as a design driver; RISC-V vector and core microarchitecture; interconnect, collectives and multi-engine synchronisation; memory-centric computing; AI agents applied to hardware design and co-design loops; reliability and silent data corruption; and the model-side changes, such as looped and recurrent transformers, that quietly move the hardware target.

Two of those themes, 3D integration and low-precision formats, are not represented by a person on my list yet. For now I follow them as topics rather than as people, and I expect one of the two to produce an obvious name for the list within a year.

## The routine

A list is only as good as the habit behind it, so the habit is deliberately modest:

| When | What |
|------|------|
| Weekly, about two hours | One keynote or long talk from the fifteen; two newsletters; a short arXiv scan |
| Monthly, about an hour | Who has newly cited five seed papers I care about, and from which direction |
| Quarterly | Three dated predictions of my own, written down |
| Yearly | Re-read the standing texts, count the ISSCC and VLSI sessions, grade my Top Picks guess, revisit the list |
| Every two years | Grade the prediction notebook, theirs and mine |

The prediction notebook is the piece I am most curious about. Each row records who said what, where, with what time horizon, and when I should check. The first entries are standing theses I have heard repeated in public talks, which I will verify against the original sources before grading: that energy is dominated by data movement rather than arithmetic; that analog in-memory computing will reach a shipping product at competitive efficiency; that a portable compiler stack, rather than a competing chip, is what eventually loosens the hold of a single vendor's software ecosystem. Alongside them are a couple of my own, including a bet that compiler support for in-memory accelerators above the macro level becomes a recognisable sub-topic at the EDA conferences within two years. I would rather be wrong in writing than vaguely right in memory.

## A closing note

I do not think this list is correct, only that it is honest about its own shape. The people on it have taught me a great deal, including the ones whose conclusions I do not share, and perhaps especially those. If you keep a list like this, I would love to compare notes, and if you know who should hold that third seat, please tell me.
