---
title: FHPC 2012 Programme, 15 September 2012
layout: page
---

### 9:00-10:30: Compilation technology

#### Welcome and Workshop Opening

_Andrzej Filinski (University of Copenhagen, Denmark); Clemens Grelck
(University of Amsterdam, Netherlands)_

<h4><a name="fhpc16kn"><em>Keynote</em>: Using Domain-Specific Languages and Access-Execute
Descriptors to Expand the Parallel Code Synthesis Design Space</a></h4>

_Paul H J Kelly (Imperial College, UK)_

This talk is about the following idea: can we simultaneously raise the
level at which programmers can reason about code, and also provide the
compiler with a model of the computation that enables it to generate
faster code than you could reasonably write by hand?  We have been
working with three large computational fluid dynamics frameworks, and
I will present some of our experience in building compiler tools at
various levels of abstraction.  Our primary goal is to build tools
that automatically synthesise the best possible implementation.  By
getting the abstraction right, we can capture design choices far
beyond what a conventional compiler can do.

I will illustrate this with examples involving low-level parallel code
generation (eg for GPUs), high-level cross-cutting almost-algorithmic
choices (such as whether to actually build a global sparse system
matrix), and semantic properties (enabling massive common
subexpression elimination in finite-element assembly).  What is the
right code to generate, for a given hardware platform?  How does this
change as problem parameters change?  The key, we believe, is to start
with the right representation of the problem, and to build tools that
can automate the combination of code generation alternatives.

<h4><a name="fhpc06">Parallel Programming in Haskell Almost for Free:<br> 
An Embedding of Intel's Array Building Blocks</a></h4>

_Bo Joel Svensson, Mary Sheeran (Chalmers University of Technology, Sweden)_

Nowadays, performance in processors is increased by adding more cores
or wider vector units, or by combining accelerators like GPUs and
traditional cores on a chip.  Programming for these diverse
architectures is a challenge. We would like to exploit all the
resources at hand without putting too much burden on the
programmer. Ideally, the programmer should be presented with a machine
model abstracted from the specific number of cores, SIMD width or the
existence of a GPU or not. Intel's Array Building Blocks (ArBB) is a
system that takes on these challenges. ArBB is a language for data
parallel and nested data parallel programming, embedded in C++. By
offering a retargetable dynamic compilation framework, it provides
vectorisation and threading to programmers without the need to write
highly architecture specific code.

We aim to bring the same benefits to the Haskell programmer by
implementing a Haskell frontend (embedding) of the ArBB system. We
call this embedding EmbArBB.  We use standard Haskell embedded
language procedures to provide an interface to the ArBB functionality
in Haskell. EmbArBB is work in progress and does not currently support
all of the ArBB functionality.  Some small programming examples
illustrate how the Haskell embedding is used to write programs. ArBB
code is short and to the point in both C++ and Haskell.  Matrix
multiplication has been benchmarked in sequential C++, ArBB in C++,
EmbArBB and the Repa library.  The C++ and the Haskell embeddings have
almost identical performance, showing that the Haskell embedding does
not impose any large extra overheads.  Two image processing algorithms
have also been benchmarked against Repa. In these benchmarks at least,
EmbArBB performance is much better than that of the Repa library,
indicating that building on ArBB may be a cheap and easy approach to
exploiting data parallelism in Haskell.

### 10:30-11:00: _Morning Break_

### 11:00-12:30: Dataflow Programming

<h4><a name="fhpc14">Avalanche: A Fine-Grained Flow Graph Model for
Irregular Applications on Distributed-Memory Systems</a></h4>

_Jeremiah J. Willcock, Ryan R. Newton, Andrew Lumsdaine (Indiana University, USA)_

Flow graph models have recently become increasingly popular as a way
to express parallel computations.  However, most of these models
either require specialized languages and compilers or are
library-based solutions requiring coarse-grained applications to
achieve acceptable performance.  Yet, graph algorithms and other
irregular applications are increasingly important to modern
high-performance computing, and these applications are not amenable to
coarsening without complicating algorithm structure.  One effective
existing approach for these applications relies on active messages.
However, the separation of control flow between the main program and
active message handlers introduces programming difficulties.

To ameliorate this problem, we present Avalanche, a flow graph model
for fine-grained applications that automatically generates
active-message handlers.  Avalanche is built as a C++ library on top
of our previously-developed Active Pebbles model; a set of combinators
builds graphs at compile-time, allowing several optimizations to be
applied by the library and a standard C++ compiler.  In particular,
consecutive flow graph nodes can be fused; experimental results show
that flow graphs built from small components can still efficiently
operate on fine-grained data.

<h4><a name="fhpc09">Harnessing Parallelism in FPGAs Using the Hume Language</a></h4>

_Jocelyn Sérot (Blaise Pascal University, France);
Greg Michaelson (Heriot-Watt University, UK)_

We propose to use Hume, a general purpose, functionally inspired,
programming language, initially oriented to resource-aware embedded
applications, to implement fine-grain parallel applications on
FPGAs. We show that the Hume description of programs as a set of
asynchronous boxes connected by wires has a very natural
interpretation in terms of register-transfer level hardware
description, hence leading to efficient implementations on FPGAs. The
paper describes the basic compilation process from a subset of Hume to
synthetisable RTL VHDL and show preliminary experimental results
obtained with a very simple perceptron application.

<h4><a name="fhpc04">Usage of Petri Nets for High Performance Computing</a></h4>

_Stanislav Böhm, Marek B&#283;hálek (V&#352;B&ndash;Technical University of Ostrava, Czech Republic)_

Petri nets are a well established graphical and mathematical modelling
language for a description of concurrent systems. The main scope of
this paper is to present our approach how to use Petri nets for
high-performance computing. They are rarely used in this area. As a
proof of concept, we are developing a tool Kaira. The modelling
language in the tool is based on our extension of Coloured Petri
Nets. The basic concept is to use a visual language to model parallel
behaviour and communication. Sequential parts of a program are written
in C/C++. In contrast to other Petri Nets based tools, Kaira is not
intended only for modelling and simulation, but it can also generate
standalone parallel applications from models. Generated applications
use MPI and threads. This paper also presents new Kaira's features
including modules for computations on structured objects, more
controllable semantics of mapping to MPI processes and a support for
the hybrid computing

### 12:30-14:00: _Lunch Break_

### 14:00-15:30: Performance vs. Abstraction

<h4><a name="fhpc13">Haskell vs. F# vs. Scala: A High-level Language Features and
Parallelism Support Comparison</a></h4>

_Prabhat Totoo, Pantazis Deligiannis, Hans-Wolfgang Loidl (Heriot-Watt University, UK)_

This paper provides a performance and programmability comparison of
high-level parallel programming support in Haskell, F# and Scala.
Developing several parallel versions, we employ skeleton-based,
semi-explicit and explicit approaches to parallelism. We focus on
advanced language features for separating computational and
coordination aspects of the code and tuning performance. We also
assess the impact of functional purity and multi-paradigm design of
the languages on program development and performance.

Basis for these comparisons are several Barnes-Hut implementations of
the n-body problem in all three languages, on both Linux and
Windows. Our performance measurements on state-of-the-art multi-cores
achieve a speedup up to 5.62 (on 8 cores) with a highly-tuned Haskell
version. For comparable implementations in Scala and F# we achieve
speedups of 4.51 (on 8 cores) and 2.28 (on 4 cores), respectively. We
observe that near best speedups are achieved using the highest level
abstraction in these languages.

<h4><a name="fhpc15">Financial Software on GPUs: Between Haskell and Fortran</a></h4>

_Cosmin E. Oancea, Christian Andreetta, Jost Berthold, Fritz
Henglein (University of Copenhagen, Denmark); 
Alain Frisch (LexiFi, France)_

This paper presents a real-world pricing kernel for financial
derivatives and evaluates the language and compiler tool chain that
would allow expressive, hardware-neutral algorithm implementation and
efficient execution on graphics-processing units (GPU).  The language
issues refer to preserving algorithmic invariants, e.g., inherent
parallelism made explicit by map-reduce-scan functional combinators.
Efficient execution is achieved by manually applying a series of
generally-applicable compiler transformations that allows the
generated-OpenCL code to yield speedups as high as 70x and 540x on a
commodity mobile and desktop GPU, respectively.

Apart from the concrete speed-ups attained, our contributions are
twofold: First, from a language perspective, we illustrate that even
state-of-the-art auto-parallelization techniques are incapable of
discovering all the requisite data parallelism when rendering the
functional code in Fortran-style imperative array processing
form. Second, from a performance perspective, we study which compiler
transformations are necessary to map the high-level functional code to
hand-optimized OpenCL code for GPU execution.  We discover a rich
optimization space with nontrivial trade-offs and cost models.  Memory
reuse in map-reduce patterns, strength reduction, branch divergence
optimization, and memory access coalescing, exhibit significant impact
individually. When combined, they enable essentially full utilization
of all GPU cores.

Functional programming has played a crucial double role in our case
study: Capturing the naturally data-parallel structure of the pricing
algorithm in a transparent, reusable and entirely hardware-independent
fashion; and supporting the correctness of the subsequent compiler
transformations to a hardware-oriented target language by a rich class
of universally valid equational properties.  Given the observed
difficulty of automatically parallelizing imperative sequential code
and the inherent labor of porting hardware-oriented and -optimized
programs, our case study suggests that functional programming
technology can facilitate high-level expression of leading-edge
performant portable high-performance systems for massively parallel
hardware architectures.

<h4><a name="fhpc05">Seeing the Futures: Profiling Shared-Memory Parallel Racket</a></h4>

_James Swaine, Burke Fetscher, Robert Bruce Findler (Northwestern University, USA);
Vincent St-Amour (Northeastern University, USA); 
Matthew Flatt (University of Utah, USA)_

This paper presents the latest chapter in our adventures coping with a
large, sequentially-tuned, legacy runtime system in today's parallel
world. Specifically, this paper introduces our new graphical
visualizer that helps programmers understand how to program in
parallel with Racket's futures and, to some extent, what performs
well in sequential Racket.

Overall, our experience with parallelism in Racket is that we can
achieve reasonable parallel performance in Racket without sacri-
ficing the most important property of functional programming lan-
guage implementations, namely safety. That is, Racket programmers are
guaranteed that every Racket primitive (and thus all functions built
using Racket primitives) will either behave properly, or it will
signal an error explaining what went wrong.

That said, however, it is challenging to understand how to best use
futures to achieve interesting speedups, and the visualizer is our
attempt to more widely disseminate key performance details of the
runtime system in order to help Racket programmers maximize
performance.

### 15:30-16:00: _Afternoon Break_

### 16:00-17:00: Domain-Specific Middleware

<h4><a name="fhpc01">Parallel Discrete Event Simulation with Erlang</a></h4>

_Luca Toscano, Gabriele D'Angelo, Moreno Marzolla (University of Bologna, Italy)_

Discrete Event Simulation (DES) is a widely used technique in which
the state of the simulator is updated by events happening at discrete
points in time (hence the name). DES is used to model and analyze many
kinds of systems, including computer architectures, communication
networks, street traffic, and others. Parallel and Distributed
Simulation (PADS) aims at improving the efficiency of DES by
partitioning the simulation model across multiple processing elements,
in order to enable larger and/or more detailed studies to be carried
out. The interest on PADS is increasing since the widespread
availability of multicore processors and affordable high performance
computing clusters. However, designing parallel simulation models
requires considerable expertise, the result being that PADS techniques
are not as widespread as they could be.

In this paper we describe
ErlangTW, a parallel simulation middleware based on the Time Warp
synchronization protocol. ErlangTW is entirely written in Erlang, a
concurrent, functional programming language specifically targeted at
building distributed systems. We argue that writing parallel
simulation models in Erlang is considerably easier than using
conventional programming languages. Moreover, ErlangTW allows
simulation models to be executed either on single-core, multicore and
distributed computing architectures. We describe the design and
prototype implementation of ErlangTW, and report some preliminary
performance results on multicore and distributed architectures using
the well known PHOLD benchmark.</p>

<h4><a name="fhpc11">An Embedded DSL for Stochastic Processes</a></h4>

_Michael Flænø Werk, Joakim Ahnfelt-Rønne, Ken Friis Larsen (University of Copenhagen, Denmark)_

We present a domain specific language embedded in Haskell for
specifying stochastic processes, called <i>SPL</i>. It is designed
with the goal of matching the notation used in mathematical finance,
where the price of a financial contract is specified using stochastic
processes and distributions.

_SPL_ is declarative in the sense that it is agnostic of the
choice of discretization and of the computational model. We provide an
implementation of _SPL_ that performs Monte Carlo simulation
using GPGPU, and we present data indicating that this gives a 100x
speedup compared to hand-written sequential C, and that the speedup
scales linearly with the number of available cores.

### 17:00-17:10: _Closing_





