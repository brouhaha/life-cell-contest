# Life Cell Logic Design Contest

On June 16, 2022, I announced a design challenge on Twitter, to design the combinatorial logic for one cell of John Conway's cellular automata "Life", with the objective of using a minimal number of discrete logic chips, with memory chips and programmable logic chips not allowed.

Here is a [compliation of the tweets of the announcement and rules](RULES.txt).

The idea for the contest came about as I was optimizing RTL code for
an FPGA life cell. In FPGAs with 6-input LUTs, a life cell can be
implemented in four LUTs, which I believe is optimal. As I was
thinking about that, it occurred to me that this would be an
interesting challenge for discrete SSI/MSI logic. The Life next-state
logic is not very conducive to optimization using traditional
techniques like Quine-McClusky tabular minimazation, or other methods
that result in a flattened sum-of-products, as that results in 84
product terms.



## Winner

The [winning entry](entries/@summivox/summivox.png) was submitted by @summivox. It is a three chip design using two 74LS283 four-bit adders and a 74HC[T]4067 sixteen-to-one multiplexer.


## Entries

Mulitple entrants came up with three-chip entries, all of which used two four-bit adders (74LS283 or equivalent) and an 8:1 or 16:1 multiplexer. They differ in minor details, but all work in essentially the same way.

As time permits, I'll add some of the other entries here.


## My design (not a contest entry)

I started working on a design after I announced the challenge. After I validated my design in a simulator, on June 17th at 1738 MDT I tweeted the ssh256sum of the [schematic PDF](reference/brouhaha.pdf). On July 2nd, after the contest deadline, I tweeted [notes regarding my design](reference/notes.txt). Many of the contestant's designs work similarly.


## Honorable mentions

* @babbageboole proposed the idea of an analog design, right before I updated the rules to disallow it

* @summivox actually degined a [two-chip analog design](honorable_mention/@summivox/summivox-analog.png), in addition to the winning three-chip digital design

* @GrumpyCat111111  has a design using [four identical chips](@GrumpyCat111111/adders-only.png) ('283 adder)

* @pepijndevos has a design for [four cells using eight chips](honorable_mention/@pepijndevos/four-cell-eight-chip.jpg) (average two per cell)

* @Shaos1973 used a decision tree tool to generate a design using [25 2:1 mulitplexers](honorable_mention/@Shaos1973/mux-only.png)
