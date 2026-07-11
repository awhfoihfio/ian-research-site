---
title: "AI Memory and Storage: Structural Demand, Uneven Value Capture"
description: "Why more bits will not eliminate either the memory wall or the memory cycle."
pubDate: 2026-07-11
---
*Why more bits will not eliminate either the memory wall or the memory cycle*

## Thesis

Artificial intelligence is structurally increasing both the quantity and the performance of memory required per unit of compute. Larger models, longer context windows, agentic workflows and rising inference volumes all require more memory capacity, higher bandwidth and greater storage throughput.

That does not mean every part of the memory industry will generate structurally higher returns.

The central investment question is not whether AI will consume more memory. It almost certainly will. The more difficult question is whether current producers can preserve scarcity pricing and elevated margins after supply responds, yields improve and customers qualify additional sources.

In this note, **capacity expansion** refers primarily to growth in industry bit supply and installed memory capacity. That expansion is necessary: without more DRAM, NAND and HBM, shortages and high prices would constrain AI infrastructure deployment. But additional capacity addresses only one part of the system. It does not independently solve limitations involving bandwidth, latency, interconnect performance, power consumption or data movement.

My base case is therefore that the AI memory hierarchy will become larger and more valuable, while value capture across that hierarchy will remain uneven. HBM and other highly integrated technologies may sustain stronger economics because of manufacturing complexity, advanced packaging and customer qualification. Conventional DRAM and NAND remain more exposed to supply growth, average selling price normalization and capital intensity. At the same time, some of the most durable value may accrue to controllers, interconnects, packaging, pooled-memory architectures and software that improves the efficiency of the entire system.

I am bullish on the strategic importance of AI memory, but selective on the equities.

## Structural Demand Is Real

AI accelerators can perform enormous numbers of calculations, but their theoretical compute capacity is useful only when data reaches them quickly enough. If model weights, activations or KV-cache data cannot be supplied at the required rate, expensive accelerators spend more time waiting and less time computing.

Memory is therefore no longer a peripheral input to the AI system. It increasingly determines accelerator utilization and overall system performance.

In its fiscal Q3 2026 prepared remarks, Micron said that AI system performance is architecturally dependent on the performance and capacity of the memory subsystem. The company also reported that data center SSD revenue exceeded $5 billion and more than doubled sequentially, while DRAM and NAND demand continued to exceed industry supply significantly. Management expects supply-demand conditions to remain tight beyond calendar 2027. These are company forecasts rather than independent guarantees, but they illustrate the scale of current demand and the constraints facing suppliers. [Micron]

The demand is also broader than the original training-cluster thesis. Training requires large pools of HBM and high-performance storage, but inference can create an even wider memory footprint. AI agents may retrieve documents, call multiple models, preserve state, use tools and generate intermediate results before answering a single request. CPUs and control-plane servers require DRAM; accelerators require HBM; model files, vector databases and persistent context stores require enterprise SSDs and larger storage systems.

On-device AI adds another layer of demand across smartphones, PCs, vehicles and edge systems. Each workload has a different memory profile, but the common direction is toward more data being stored, accessed and moved throughout the technology stack.

The structural demand thesis is therefore strong. The unresolved question is how much of that demand becomes durable free cash flow for each supplier.

## The Memory Wall Is More Than a Capacity Problem

An AI system is constrained by several related but distinct resources:

| Resource | Core question | Typical constraint |
| --- | --- | --- |
| Compute | How many operations can the system perform? | Accelerator throughput and utilization |
| Memory capacity | How much active data can remain accessible? | Model size, batch size and KV-cache size |
| Memory bandwidth | How quickly can that data be read or written? | Weight and KV-cache movement during inference |
| Latency | How long does each access take? | Time-to-first-token and interactive responsiveness |
| Interconnect | How efficiently can processors exchange data? | GPU-to-GPU, CPU-to-GPU and scale-out communication |
| Storage throughput | How quickly can data enter or leave the active memory hierarchy? | Model loading, retrieval and checkpoint movement |
| Power and cooling | How much useful work can be performed within the power envelope? | Bandwidth per watt and rack-level density |
| Software efficiency | How effectively are the available resources used? | Scheduling, cache management and data placement |

The effective performance of the system depends on the interaction among these layers. Improving only one resource can produce diminishing returns if another becomes the bottleneck.

Large-language-model inference provides a clear example. The prefill stage, which processes the input prompt, is generally compute-intensive. The decode stage, which generates subsequent tokens, is often memory-bandwidth-bound, particularly in latency-sensitive serving. During decode, the system repeatedly reads model weights and KV-cache data while performing relatively limited computation for each generated token. Different model architectures, batch sizes and serving configurations can shift the bottleneck, but the underlying distinction is important. [NVIDIA Dynamo]

Longer context windows increase the pressure. In a conventional transformer, KV-cache requirements generally rise with context length, batch size and model dimensions. More capacity allows the system to hold a larger cache, but the cache must still be accessed efficiently. At sufficiently long contexts, attention computation and interconnect traffic can also become material constraints.

NVIDIA's Rubin generation demonstrates how aggressively the industry is responding. Rubin increases HBM bandwidth from approximately 8 TB/s on Blackwell to as much as 22 TB/s and provides up to 288 GB of HBM4 per GPU. Its NVLink bandwidth also doubles to 3.6 TB/s per GPU. These improvements are evidence of technological progress, but they also reveal the severity of the bottleneck: greater compute density requires simultaneous advances in memory and communication. [NVIDIA Rubin]

The memory wall is therefore not a single wall. It is a moving set of constraints involving capacity, bandwidth, latency, interconnects, software and power.

## What Capacity Expansion Can—and Cannot—Solve

More manufacturing capacity can reduce shortages, moderate prices and support a larger installed base of AI systems. It is essential to the industry's growth.

But manufacturing more memory bits is not the same as delivering those bits to an accelerator at the right speed, latency, location and energy cost.

Additional server DRAM or SSD capacity cannot directly replace local HBM. The products occupy different levels of the hierarchy and serve different performance requirements. More HBM supply can increase the amount of high-bandwidth memory available to the industry, but each accelerator package still faces physical, thermal, power, yield and packaging constraints.

Bandwidth improvements may also be absorbed by more demanding workloads. Larger models, longer contexts, mixture-of-experts routing and higher inference concurrency can consume the gains produced by each hardware generation. This does not make the improvements unimportant; it means the target continues to move.

Power creates a further constraint. Moving weights, activations and KV-cache data consumes energy without itself performing the arithmetic that produces an output. As data centers become limited by grid connections and rack-level power density, reducing unnecessary movement and improving bandwidth per watt may become as important as adding nominal capacity.

Capacity expansion solves scarcity. System design determines how efficiently that capacity becomes useful compute.

## A Hierarchy, Not a Single Memory Market

Future AI infrastructure will rely on multiple memory and storage tiers rather than one universal product:

| Tier | Primary role | Main advantage | Main limitation |
| --- | --- | --- | --- |
| HBM | Active model weights, activations and KV cache beside the accelerator | Highest bandwidth and strong energy efficiency | High cost, limited capacity and package constraints |
| Server DRAM / pooled memory | CPU workloads, control planes and capacity extension | Greater capacity and flexibility than HBM | Higher latency and lower bandwidth |
| High-performance flash / enterprise SSD | Model files, retrieval systems, checkpoints and warm data | Large capacity at lower cost | Far slower than DRAM and HBM |
| Bulk storage | Training data, archives and generated content | Lowest cost per bit and largest scale | Highest latency and lowest effective throughput |

These tiers are complements, not direct substitutes. The system-level opportunity lies in placing each piece of data in the cheapest tier that still meets the workload's performance requirements—and moving it as little as possible.

This distinction matters for investors because growth in total AI data does not translate evenly into demand, pricing power or margins at every tier.

## HBM: Differentiated Growth, but Not Immunity From Competition

HBM currently has the strongest structural case within memory.

By vertically stacking DRAM and integrating it closely with an accelerator, HBM delivers substantially more bandwidth than conventional server memory. It is difficult to manufacture, consumes meaningful wafer capacity, requires advanced packaging and must be qualified with specific accelerator platforms.

SK hynix states that its HBM4 provides 2.54 times the bandwidth of the previous generation and improves power efficiency by more than 40%. The exact realized benefit will vary by system, but the direction is clear: HBM improves performance and energy efficiency, not merely capacity. [SK hynix HBM4]

These characteristics support better economics than undifferentiated commodity memory. Supplier qualifications are demanding, yields matter, packaging availability can constrain output and customers cannot switch products instantly. HBM also has an increasing trade ratio: producing a given quantity of HBM consumes more manufacturing capacity than supplying the same number of conventional DRAM bits, placing additional pressure on total DRAM supply.

However, strong demand does not make HBM permanently immune from the memory cycle.

Suppliers are expanding output, improving yields and qualifying new generations. Accelerator customers have an incentive to develop second sources and reduce dependence on a single vendor. Product standards can broaden over time, while packaging capacity can eventually catch up. Even if HBM volumes continue to grow, the price premium and margin attached to each bit may change.

The investment question is therefore not simply how fast HBM demand will grow. It is whether qualification barriers, packaging constraints and product differentiation will remain strong enough to generate returns above the cost of the capital required to expand supply.

## DRAM and NAND: Structural Volume, Cyclical Economics

Traditional DRAM and NAND should also benefit substantially from AI.

Server DRAM supports CPUs, control systems, databases and inference infrastructure. Enterprise SSDs store models, training data, vector indexes, checkpoints, generated content and persistent context. Micron's fiscal Q3 data center SSD results show that this demand is already economically meaningful, not merely theoretical. [Micron]

Nevertheless, conventional DRAM and NAND remain more exposed to traditional semiconductor economics than leading-edge HBM. When shortages lift average selling prices and margins, producers gain a strong incentive to add wafer capacity, improve yields and migrate toward denser nodes. Because new fabs take years to build, the supply response is delayed rather than absent.

This creates the central tension in the memory thesis:

1. AI can permanently increase the quantity of memory and storage demanded.
2. Permanent demand growth does not guarantee permanent scarcity.
3. Without permanent scarcity or differentiation, today's margins may not be permanent either.

The market can therefore grow substantially while producer returns still cycle. A larger industry is not automatically a better investment if the additional revenue requires proportionately more capital and eventually earns lower margins.

There are valid reasons to think the next cycle could be different. Greenfield fabs are expensive, complex and slow to build. Micron expects some new U.S. facilities to begin wafer output only in 2027 and 2028, and management says it currently lacks clear visibility into when supply will fully catch demand. The company has also signed 16 strategic customer agreements, suggesting that longer-term contracting may reduce some of the industry's historical volatility. [Micron]

Those factors could extend the current shortage and improve the quality of future earnings. They do not yet prove that cyclicality has disappeared.

## System-Level Innovation May Capture More of the Next Dollar

The next stage of the memory opportunity may depend less on maximizing one tier and more on coordinating the entire hierarchy.

### CXL memory pooling

Compute Express Link can expand or pool memory across hosts and devices, reducing the amount of DRAM stranded inside underutilized servers. In selected architectures, CXL-connected capacity can also support KV-cache expansion and disaggregated inference.

Its role is not to replace HBM. CXL-attached memory has higher latency and lower bandwidth than memory located beside the accelerator, and many current GPUs do not natively access CXL memory without additional system support. Its potential value lies in utilization: allocating capacity more flexibly and creating an intermediate tier between local HBM and slower storage.

An XConn demonstration presented through the CXL Consortium reported substantial performance gains over RDMA-based memory sharing for a specific inference configuration. That is encouraging, but it remains a vendor demonstration rather than universal evidence across models, hardware and production environments. [CXL Consortium]

### High-bandwidth flash

SK hynix and Sandisk are working through the Open Compute Project to standardize high-bandwidth flash, or HBF, as a tier between HBM and SSD. The objective is to provide greater capacity and better power efficiency for inference without attaching expensive HBM to every part of the workload. The companies expect demand for complex memory solutions including HBF to accelerate around 2030. [HBF announcement]

HBF is strategically interesting, particularly for capacity-heavy inference, but it remains an early-stage standardization and commercialization effort. Its eventual performance, adoption rate, pricing and industry structure are uncertain. It should currently be treated as an option rather than a proven earnings stream.

### Software efficiency

Software may be equally important. Quantization reduces the number of bytes required for weights and cache data. Grouped-query and multi-query attention can reduce KV-cache requirements. Paged attention can improve memory utilization, while prefix caching and better scheduling reduce redundant work. Disaggregated serving can place compute-intensive prefill and memory-intensive decode on different hardware.

These techniques can reduce memory traffic per generated token. But lower cost per token can also increase total usage. Cheaper inference makes longer contexts, more agent steps and more applications economically viable. Efficiency may reduce memory intensity per task while increasing aggregate memory demand across the industry.

The most likely outcome is not hardware demand or software efficiency. It is both.

## From Industry Growth to Equity Returns

For investors, value creation can be reduced to four variables:

1. **Demand:** How quickly do AI workloads increase total memory bits, bandwidth and storage traffic?
2. **Supply:** How quickly do new fabs, node transitions, yield improvements and packaging capacity add effective output?
3. **Mix and differentiation:** What percentage of revenue comes from products with durable qualification barriers or system-level value?
4. **Capital intensity:** How much reinvestment is required to deliver the next unit of growth?

The distinction can be summarized simply:

> Industry growth creates revenue. Durable unit economics and capital discipline create shareholder value.

As of the July 10, 2026 U.S. market close, Micron traded at approximately 22 times trailing earnings, while Sandisk traded at roughly 67 times. The figures vary slightly by data provider and should not be compared mechanically: Micron combines DRAM, HBM and NAND exposure, while Sandisk is primarily a flash-memory company, and their trailing earnings reflect different points in their respective cycles. [MU valuation] [SNDK valuation]

Trailing price-to-earnings ratios are particularly weak tools for valuing memory companies. At the top of a cycle, temporarily elevated earnings can make a stock appear deceptively cheap. During a downturn—or during a rapid recovery when trailing results lag current conditions—the same company can appear expensive.

A more useful valuation should normalize:

* DRAM and NAND average selling prices;
* HBM mix, pricing premiums and customer concentration;
* Long-term bit growth and effective wafer additions;
* Yields and advanced-packaging availability;
* Gross margins after supply improves;
* Capital expenditure and working-capital requirements;
* Free cash flow through a full pricing cycle.

I would not interpret the current multiples as proof that either company is overvalued. They show only that a backward-looking earnings number is insufficient. The real question is how much of today's profitability will survive once the current shortage, product mix and capital cycle evolve.

## What Could Make This View Too Cautious

Several developments would support a more bullish conclusion.

First, shortages may last much longer than historical experience suggests. Fab construction, permitting, skilled labor, equipment lead times and energy infrastructure all limit supply growth. If AI demand continues to compound faster than effective output, pricing power could persist well beyond 2027.

Second, strategic customer agreements may change the industry's economics. Longer commitments, prepayments or negotiated capacity arrangements could reduce demand uncertainty and shift some expansion risk from suppliers to customers.

Third, HBM may remain concentrated for longer than expected. If qualification, yield and packaging barriers continue to rise with each generation, leading suppliers could preserve premium margins even as total capacity expands.

Fourth, agentic inference may create much more traffic than conventional forecasts assume. A single user request can generate multiple model calls, retrieval steps, tool executions and persistent context updates. Aggregate token consumption could grow faster than efficiency improves.

Finally, producer discipline may be stronger than in earlier cycles. If the major suppliers prioritize returns over market share, structural demand could translate into a less volatile and more profitable industry.

## What I Am Watching

The indicators that matter most are not simply quarterly revenue growth or management references to AI. I would monitor:

* DRAM and NAND bit-demand growth relative to effective bit-supply growth;
* New wafer capacity, greenfield fab schedules and equipment orders;
* HBM contract duration, customer concentration, pricing and supplier qualification;
* HBM yields and advanced-packaging capacity;
* Enterprise SSD pricing, inventory and data center mix;
* Capital expenditure as a percentage of revenue and through-cycle free cash flow;
* Memory capacity and bandwidth per accelerator relative to compute growth;
* Real-world adoption of CXL, HBF and disaggregated inference;
* Memory required per token versus total tokens generated across AI systems.

These indicators would help distinguish a genuine structural improvement in industry economics from a powerful but ultimately cyclical shortage.

## Current View

AI memory and storage are structurally attractive industries. They are essential to accelerator utilization, inference economics and the broader development of agentic systems. The memory wall is real, and solving it requires continuing advances in capacity, bandwidth, interconnects, packaging, power efficiency and software.

But a strategic industry is not automatically an attractive equity at every price.

I would not short the sector simply because expectations are high. Supply could remain constrained for years, HBM barriers may prove more durable than expected and agentic inference may create demand that current forecasts still underestimate.

Nor would I treat the entire sector as a simple structural-growth trade. Conventional memory remains capital-intensive, and today's scarcity does not guarantee tomorrow's margins. I would prefer companies with defensible product differentiation, system-level integration or enabling technologies whose economics do not depend entirely on temporary supply tightness.

For memory producers, I would require either a meaningful discount to normalized free cash flow or stronger evidence that long-term contracting, product mix and capital discipline have changed the cycle. Until then, I prefer to watch the sector and use volatility selectively rather than chase the current enthusiasm.

The most likely outcome is not that memory becomes less important. It is that memory becomes more important while the distribution of value becomes more selective.

Nothing in this note constitutes investment advice. All views are personal and provided solely for research discussion and educational purposes.

## Sources

* [Micron Technology, Fiscal Q3 2026 Earnings Call Prepared Remarks][Micron]
* [NVIDIA, Introducing NVIDIA Dynamo][NVIDIA Dynamo]
* [NVIDIA, Inside the Vera Rubin Platform][NVIDIA Rubin]
* [SK hynix, HBM4 at MWC 2026][SK hynix HBM4]
* [Compute Express Link Consortium, CXL Memory Pooling Demonstration][CXL Consortium]
* [SK hynix and Sandisk, HBF Standardization Announcement][HBF announcement]
* [GuruFocus, Micron Trailing P/E][MU valuation]
* [MarketWatch, Sandisk Market Data][SNDK valuation]

[Micron]: https://investors.micron.com/static-files/631b1a32-5537-46ae-8f40-82e42fc79dfe
[NVIDIA Dynamo]: https://developer.nvidia.com/blog/introducing-nvidia-dynamo-a-low-latency-distributed-inference-framework-for-scaling-reasoning-ai-models/
[NVIDIA Rubin]: https://developer.nvidia.com/blog/inside-the-nvidia-rubin-platform-six-new-chips-one-ai-supercomputer/
[SK hynix HBM4]: https://news.skhynix.com/mwc-2026/
[CXL Consortium]: https://computeexpresslink.org/blog/overcoming-the-ai-memory-wall-how-cxl-memory-pooling-powers-the-next-leap-in-scalable-ai-computing-4267/
[HBF announcement]: https://news.skhynix.com/sk-hynix-and-sandisk-begin-global-standardization-ofnext-generation-memory-hbf/
[MU valuation]: https://www.gurufocus.com/term/pettm/MU
[SNDK valuation]: https://www.marketwatch.com/investing/stock/sndk