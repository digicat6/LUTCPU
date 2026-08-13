Monofunction Computing Architecture

I am researching a computational model from which the Monofunction Computing Architecture was derived.

There are many ways to organize computation, but I have always been drawn to mathematical rigor. So I wanted to take a somewhat different path: instead of starting from the traditional processor structure and instruction set, I tried to derive a computing machine architecture directly from a mathematical description of the computational process.

The result is a monofunctional computing architecture in which a wide range of traditional processor operations is reduced to a single principle of execution.

The model is described by a mathematical formula, and the architecture built on it differs substantially from the classical organization of a processor.

Publication

A Canonical Routine Form for Compositional Computation

DOI: Publication on Zenodo Google Scholar profile

Why build a computer

My goal is to get a practical sense of how efficient this computational model actually is.

I could have limited myself to mathematical analysis or a software simulation. But I wanted a far more tangible result: to build an actual computer based on this architecture, measure its characteristics, and compare them with the characteristics of other computers.

The point of the project is not to find out whether the architecture works at all. Its viability follows from the model itself and has already been demonstrated in several earlier hardware implementations.

The current project pursues a different goal: to build a reasonably complete computer under strictly defined historical technological constraints, and see how efficient the computational model itself turns out to be.

Previous implementations

Before this project, I built two hardware implementations of the Monofunction Computing Architecture using 74-series logic.

The first was aimed primarily at minimizing chip count. It used SRAM with a 10 ns access time and comprised roughly 12 chips from the 74-series. The project achieved a basic operation execution time of about 40 ns and produced a 16-color text-mode VGA signal. A custom editor/assembler was also built to work with the architecture.

[Photo of the first prototype]

Prototype I — minimum-chip implementation. Approximately 12 logic ICs, 10 ns SRAM, 40 ns basic operation, 16-color text VGA output.

The second implementation was built using modern high-speed 74-series logic and SRAM with an 8 ns access time. In this implementation, the clock reached 125 MHz. Processor operation was verified in hardware; in particular, an oscilloscope was used to show cyclic execution of a six-instruction sequence. Programming tools were also developed for this implementation.

[Photo of the second prototype / oscilloscope traces]

Prototype II — high-speed implementation. Modern 74-series logic, 8 ns SRAM, operation up to 125 MHz. Oscilloscope demonstration of a six-instruction execution loop.

Both implementations remained experimental prototypes. I never took their software to the level of a complete computer.

At the same time, they had a significant shortcoming for comparative research: the high performance was achieved using modern, very fast SRAM. That inevitably raises the question — how much of the performance comes from the architecture, and how much from memory that wasn't available to the era's computers I would want to compare it against?

That question is what led to the third project.

This time, I want to deliberately give up the advantage of modern memory and build a computer from components that were genuinely available during the chosen historical period.

If the architecture really is efficient, let that advantage come from the architecture itself — not from 8 ns or 10 ns SRAM.

Why a retro-computer?

The choice of period-accurate components is not simply driven by an interest in retro-computing.

Trying to compare a new computing architecture against modern processors quickly puts the experiment out of reach for an individual researcher.

Modern processors contain billions of transistors, are manufactured on process nodes that cannot be replicated by an individual, use multi-level caches, extremely fast memory interfaces, sophisticated out-of-order execution mechanisms, and run at clock speeds that cannot be reproduced in an experimental computer built from discrete chips.

So a direct hardware comparison against modern computers is, by orders of magnitude, beyond the practical scope of this project.

But if the comparison is shifted back roughly forty years, the situation changes completely.

An early-1980s computer can still be physically reproduced at the level of individual chips. Memory, logic, and other components from that same era can be used, placing an alternative computing architecture under roughly the same technological constraints that real designers faced at the time.

That is why 1983 was chosen as the technological boundary of the project.

I did not pick 1983 simply to build "a retro-computer for its own sake."

I am building a retro-computer because the technology level of the early 1980s is still capable of physically realizing an alternative computing architecture and comparing it directly against the industrial computers of that period.

And the historical, nostalgic character of such an experiment only makes the work more enjoyable.

The 1983 rule

The computationally significant part of the project uses only components that actually existed and were commercially available by the chosen date.

This is a hard constraint.

There are plenty of retro-computing projects online that show very high performance on discrete logic, but that quietly rely on modern fast SRAM or other components that appeared long after the computers being compared against.

That approach doesn't work for this project.

If the architecture turns out to have an advantage, I want that advantage to come from how computation is organized — not from using memory or other technology that wasn't available to designers of the era being compared.

So for every critical component, I try to verify not just the chip's introduction date, but its actual commercial availability — via historical catalogs, price lists, and manufacturer documentation.

Current project — a 1983 computer

The computer being designed has the following baseline configuration:

4 KB instruction memory;
4 KB operand and data memory;
64 KB DRAM video memory;
8-bit architecture;
512×200 color raster display;
16 colors;
a processor built from 74-series discrete logic.

Modern FPGAs and microcontrollers are not used to implement the computing architecture.

The computer is meant not to be an imitation of an early-1980s machine, but a machine that could, in principle, have been built from the components that actually existed then.

Memory

Choosing the memory is especially important, since its speed directly limits what the computing system can do.

The reference components are ones whose availability and pricing are confirmed by historical price lists from the early 1980s:

Chip	Organization	Speed	Price
DRAM 4116	16K×1 bit	200 ns	$1.50
DRAM 4164	64K×1 bit	200 ns	$7.95
SRAM HM6116	2048×8 bit	150 ns	$8.25

The prices aren't there to squeeze out the cheapest possible machine at any cost.

They let me judge how realistic a given technical choice would have been for its time, and later let me compare the cost of the experimental machine against the cost of other computers of the period.

What I want to get out of this

Once the computer is finished, I want to run a series of comparisons against real personal computers from the same period.

I'm not interested in one hand-picked competitor or a single metric.

As far as possible, the comparison will cover:

execution time of individual operations;
execution time of identical program tasks;
memory bandwidth;
graphics capabilities;
resolution and number of simultaneously displayed colors;
amount of memory;
hardware complexity;
chip count;
cost of the component base at historical prices;
how efficiently the available hardware resources are used.

It's especially important to distinguish between the execution time of one architectural operation and the time needed to solve a complete task.

A Monofunction Computing Architecture operation is not directly equivalent to an instruction on a 6502, Z80, 8088, or 68000. So a plain comparison of nanoseconds-per-instruction isn't meaningful on its own.

For a more meaningful comparison, I'll use identical end tasks: block-memory operations, computational algorithms, graphics work, and other programs where the same final result can be produced on different architectures.

That way it becomes possible to compare not just individual hardware cycles, but the actual amount of work a computer completes in a given time.

What this experiment is meant to show

A comparison like this is not an exhaustive mathematical proof of the computational model's efficiency.

It's deliberately a much simpler method.

But it lets me put different architectural ideas under roughly the same technological constraints and see the result in physical form.

If the resulting machine turns out to outperform some computers of its notional era, that's an interesting result.

If any advantage shows up only for certain kinds of tasks, that's a result too.

If some feature of the architecture turns out to be inefficient once it's actually built in hardware, that matters just as much.

Ultimately, the question behind the project is a simple one:

What could this computing model have delivered if a computer based on it had actually been built in 1983?

I like this method of testing precisely because of its simplicity.

Instead of yet another simulation, you get an actual computer built from chips of its own era. You can assemble it, power it on, plug it into a monitor, write programs for it, measure its real timing — and put the results next to the specs of computers that genuinely existed at the time.

Why the project is public before it's finished

The project is still in development.

The core computational model and architectural principles are already defined, but a complete computer still requires a substantial amount of engineering work: finishing individual circuit blocks, verifying timing diagrams, designing PCBs, building and debugging boards, and writing software.

So I decided not to wait until the computer is fully finished, and instead publish the project as it develops.

This repository will host:

description of the computational model;
the mathematical formula;
architecture description;
schematics;
timing diagrams;
PCB files;
bills of materials;
historical sources for the component base;
software;
test and measurement results;
final comparisons with computers from the same era.

I'd welcome contributions from anyone interested in digital logic, retro-computing, DRAM, circuit design, PCB layout, video signals, or low-level programming.

Independent review of the schematics and calculations is especially valuable. If there's a mistake somewhere, or a solution that could be implemented more simply or better within the chosen component base, I'd like to know before the final boards are made.

My main area of interest in this project is the computational model itself and the architecture that follows from it. So help from people who enjoy the practical engineering side of building it could significantly speed up getting a physical machine built.

The project is open not because the outcome is already known.

The architecture works. But how efficient it turns out to be compared to real computers of its notional era — that's exactly what I want to find out.
