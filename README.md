# Life Cell Logic Design Contest

On June 16, 2022, I announced a design challenge on Twitter, to design the combinatorial logic for one cell of [John Conway's cellular automata "Life"](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), with the objective of using a minimal number of discrete logic chips, with memory chips and programmable logic chips not allowed.

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

The [winning entry](entries/@summivox/summivox.png) was submitted by @summivox on June 18th at 0330 PDT. It is a three chip design using two 74LS283 four-bit adders and a 74HC[T]4067 sixteen-to-one multiplexer.


## Entries

Mulitple entrants came up with three-chip entries, all of which used two four-bit adders (74LS283 or equivalent) and an 8:1 or 16:1 multiplexer. They differ in minor details, but all work in essentially the same way.

I have not validated all of the entries. There were a few more entreis that were
rejected for not meeting the rules or having obvious faults, and I have not listed
those here. Some contestants submitted multiple entries, and I have only listed their
first entry with their lowest chip count.

Thanks to everyone who participated!


| ID                 | date    | time (PDT) | chip count | chips                              |
| ------------------ | ------- | ---------- | ---------- | ---------------------------------- |
| @RCAVictorCo       | June 17 | 1118       | 6          | 3 '283, 1 '06, 1 '08, 1 '4067      |
| @babbageboole      | June 17 | 1136       | 6          | 4 '283, 1 '04, 1 '11               |
| @summivox (winner) | June 18 | 0330       | 3          | 2 '283, 1 '4067                    |
| @GrumpyCat111111   | June 19 | 1802       | 3          | 2 '283, 1 AS250                    |
| @glidingholly      | June 19 | 1858       | 3          | 2 '283, 1 '151                     |
| @ravenslofty       | June 23 | 0858       | 3          | 2 '283, 1 '151                     |
| @pepijndevos       | June 26 | 0148       | 3          | 2 '283, 1 '251                     |
| @Shaos1973         | June 27 | 0433       | 3          | 2 '283, 1 '151                     |
| @xlengineer1       | June 30 | 0640       |            |                                    |
| Larry Fish         | July 1  | 2322       | 9          | 1 '00, 2 '154, 2 '20, 2 '30, 2 '54 |


## My design (not a contest entry)

I started working on a design after I announced the challenge. After I validated my design in a simulator, on June 17th at 1738 MDT I tweeted the ssh256sum of the [schematic PDF](reference/brouhaha.pdf). On July 2nd, after the contest deadline, I tweeted [notes regarding my design](reference/notes.txt). Many of the contestant's designs work similarly.


## Honorable mentions

* @babbageboole proposed the idea of an analog design, right before I updated the rules to disallow it

* @summivox actually degined a [two-chip analog design](honorable_mention/@summivox/summivox-analog.png), in addition to the winning three-chip digital design

* @GrumpyCat111111  has a design using [four identical chips](honorable_mention/@GrumpyCat111111/adders-only.png) ('283 adder)

* @pepijndevos has a design for [four cells using eight chips](honorable_mention/@pepijndevos/four-cell-eight-chip.jpg) (average two per cell)

* @Shaos1973 used a decision tree tool to generate a design using [25 2:1 mulitplexers](honorable_mention/@Shaos1973/mux-only.png)

* Larry Fish for a 13-chip all-SSI design, using 1 '04, 6 '10, 2 '32, 4 '86
