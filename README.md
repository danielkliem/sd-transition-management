# System Dynamics in Transition Management

Participative modelling for transitioning towards a circular construction
material industry.

PhD thesis, University of Bergen, defended 17 December 2021.
Funded by the Swiss National Research Programme NRP73 "Sustainable
economy".

This repository contains the System Dynamics model developed during the
dissertation (CUBIC) and the thesis document itself.

## What this is

A System Dynamics study of the Swiss mineral construction material
industry and the role of public policy in sustaining, or transitioning
away from, a linear extraction-and-disposal regime.

The work combines:
- Six participative modelling workshops with public policy experts
- Seven interviews with extraction, disposal, and recycling companies
- A quantitative simulation model (CUBIC) of the extraction, processing,
  and landfill system, used for virtual policy experiments

## Core finding

The **co-production of extraction and disposal policies** emerges as
the central regime structure that blocks a circular economy: spatial
planning treats quarry permits and landfill volumes as coupled, which
creates an incentive to extract primary resources in order to generate
disposal volume. The resulting oversupply of primary material locks out
secondary resources.

**Leverage point proposed:** cooperative spatial planning between urban
resource consumers and rural hinterlands as resource suppliers, as a
way to increase local secondary-material use without raising
interregional transport.

## On method

The dissertation contributes a "derive-challenge-iterate" cycle as an
artefact-based procedure that makes the evolution of participants'
mental models observable across workshops. A qualitative causal-loop
diagram serves as proof-of-concept for the quantified stock-and-flow
model that follows.

## The CUBIC model

CUBIC is a regionalised stock-and-flow model of mineral construction
material flows in Switzerland over a 75-year horizon (2010 to 2085).
It covers two stylised regions: an urban consumer (Region A) and a
rural hinterland supplier (Region B). It couples primary gravel
extraction, excavation material recovery, and recycled aggregate
production from construction and demolition waste (CDW), driven by
construction activity, settlement pressure, and public policy.

The model goal:
1. Explain the limits of common misperceptions about transition drivers
2. Enable policy experiments grounded in empirical workshop targets
3. Explicate institutional decision-making structures

It is not built to predict.

### Misperceptions the model addresses

These were identified during the participative modelling workshops:

1. "If we just recycle all the waste, we will not need primary
   resources." Without primary extraction there is not sufficient
   disposal volume for excavation material.
2. "If we limit gravel quarries in our region, companies will recycle
   more." On the company level locally yes; in aggregate, gravel
   imports and waste exports rise.
3. "Increasing the costs to access resources increases recycling."
   Introduced locally, financial instruments mainly raise import and
   export volumes.

### Workshop target variables

The participative process did not require agreement on target
variables: inclusion was sufficient if at least one participant
considered a variable significant.

- Imports of gravel should not be favoured over local resources.
- Local value creation is to be strengthened.
- Transport routes are to be minimised.
- Primary gravel resources are to be conserved.

### Three questions

1. How does urban construction activity influence resource management
   in rural areas?
2. What drives the recycling of excavation material?
3. What limits the uptake of recycled aggregates?

## Using the model

Open `CUBIC.stmx` in
[Stella Player](https://www.iseesystems.com/softwares/player/iseeplayer.aspx)
(free).

Recommended initialisation:
- Set "Initiate urban transition" to 1 (loads historic and current
  material flows)
- Set "Initiate incumbent policies" to 1 (loads the current policy set)

This recreates historic patterns of behaviour and matches the workshop 3
configuration described in the thesis. From here you can run the policy
experiments documented in the chapters.

For the iteration on the gravel extraction structure (paper 2): enter
the "Extraction" module and set "Switch GMB structure" to 1.

For alternative construction-activity regimes: set "Initiate urban
transition" to 0 and use the "Customize Material Flows Region A/B"
controls.

## Model background

The model covers the time horizon 2010 to 2085. 75 years is considered
a sufficient time frame to capture the unfolding long-term dynamics of
the construction material industry (Suprun et al. 2019), i.e. twice
the longest adjustment time of the model.

The model is developed from a co-evolutionary, socio-technical
transitions perspective (Foxon 2011), a relatively novel application
for quantitative System Dynamics modelling (Holtz et al. 2015).
Conceptually, it regionalises the approach of the World 6 model,
combining biophysical material flows with market dynamics (Sverdrup,
Koca, and Schlyter 2017).

The biophysical structure focuses on mineral construction material:
aggregates, excavation material, and CDW. Aggregate production includes
extracting primary gravel from quarries, recovering primary gravel
naturally contained in excavation material, and recycling secondary
gravel from CDW.

Empirical input combines existing regional material-flow analysis with
data from a series of group model building workshops and a case study
with eight companies, looking at the consequences of land use for
extraction and disposal on interregional development.

Region A represents an urban area with little remaining undeveloped
land, high population growth, and dynamic construction activity. Land
scarcity creates settlement pressure and triggers the "Not in my back
yard" phenomenon, raising the cost and difficulty of licensing new
gravel quarries.

Region B is a hinterland (Schiller, Bimesmeier, and Pham 2020) without
population growth and with constant construction activity, hence no
settlement pressure.

Public policies (spatial planning, waste management, public
procurement, fiscal) are used to increase recycling rates and reduce
transports. Material flows and associated transports between regions
express the consequences of population development and construction
activity in both regions.

## FAQ

**Does the model predict future developments?**

No. The goal is to increase general understanding of the dynamics
rather than to provide exact predictions.

**Can the model be adjusted to different regions?**

Yes. Most parameters can be tuned. The most relevant adjustments
include stock values in the gravel licensing process, the time required
to allow landscape adjustments, available disposal volumes, and the
estimated current level of experience with recycled aggregates.

**Why is there no third region?**

A closed system makes the relevant interactions between regional
developments easier to see. A third region is technically possible (it
adds a third price for inter-region transport), but the additional
insight is small relative to the added complexity. A high price
increase in one region will eventually trigger resource exchange with a
third region at higher transport cost.

**Is the model representative of all regional developments?**

Two assumptions limit the scope:
1. The structure assumes that gravel extraction creates disposal
   volume. If a region does not follow this practice or has no gravel
   reserves, the structure does not apply.
2. The effect of settlement pressure on regional license costs is a
   phenomenon observed under various names in an increasing number of
   regions.

**Why is the gravel price modelled as a stock with hill-climbing while the disposal price is an auxiliary variable?**

Disposal volume is subject to tight regulation on location, material
quality, and process costs. Without these, "wild" disposal sites become
likely (as observed in the 1960s and 1970s). As an auxiliary variable
the disposal price is less sensitive to market dynamics. This is also
supported by landscape adjustments as a non-market mechanism for
creating volume that influences the disposal price. The disposal price
therefore reflects regional scarcity governed by local authorities.
The gravel price is market driven because gravel must be extracted to
be physically available, and there are no direct interventions from
governing authorities on the gravel price.

**Why does the simulation not show the same material flows as the initial representation?**

The initial representation highlights the ratio between material flows
in the actual region. For analysis it is more useful to operate with
"all else equal" assumptions, so dynamic behaviour can be attributed
to a specific cause rather than to noise from real-world fluctuations.

**Why is the gravel-price indicator not normalised via supply and demand (as in Sterman 2000)?**

The GMB workshops surfaced that local aggregate demand is always
satisfied unless gravel is scarce in both regions. The shipping rate
of the local market is therefore not an adequate proxy for local
shortage. A gap-based formulation is more useful here.

**Why are CDW and excavation material disposed in the same volume?**

In reality the volumes differ. The model uses one for two reasons:
1. CDW disposal is more tightly regulated than excavation material
   (CDW potentially contains non-natural and hazardous waste). CDW
   landfills are kept to a minimum to incentivise recycling. Recycled
   aggregate production in this model therefore depends on price
   attractiveness rather than on local landfill shortage.
2. Excavation material volumes are significantly higher, so aggregate
   recovery contributes large gains to disposal-volume demand. Folding
   the volumes together keeps the focus on the interaction between
   gravel extraction and disposal-volume management.

**Why is the policy "increasing energy costs for transport" so ineffective?**

Energy is only a fraction (about 1/16) of total transport cost per
tonne. The effect on average transport distance becomes visible only
above a tenfold increase. Higher cost is also passed on to the
consumer, which keeps the marginal effect on profitability of import
and export activity small.

**Why does combining a disposal fee with an extraction levy not push recycling to 100%?**

Two reasons. First, even with full recycling about 70% of excavation
material still requires disposal, so companies still extract. Second,
companies pass costs to the consumer, so profitability is only
marginally affected.

**Why can prices fall to zero even when costs are non-zero (e.g. gravel price at 0 CHF/t with extraction levy > 0 CHF/t)?**

Because companies pass costs to the consumer, the connection between
extraction and disposal-volume creation dominates. If one price
approaches zero, the other rises further: companies adjust regionally
available gravel and indirectly influence disposal volume.

**Why do companies not receive revenue from landscape adjustments?**

Landscape adjustments can foreclose disposal volume (when current
coverage exceeds desired) or create additional coverage (when current
coverage is below desired). Additional volume is not necessarily tied
to existing gravel quarries and therefore does not automatically
contribute to company revenue. Examples include adjustments on
agricultural land or noise barriers along highways.

## Contents

- `thesis.pdf` (full dissertation)
- `CUBIC.stmx` (the System Dynamics model, Stella XML format)
- `Equations.txt` (model equations, text export)
- `CUBIC_technical desciption.pdf` (technical description of model
  structure and parameters)

## Citation

Kliem, D. (2021). *System Dynamics in Transition Management:
Participative modeling for transitioning towards a circular construction
material industry.* PhD Thesis, University of Bergen.
Permanent record: https://nva.sikt.no/registration/0198f23a9204-fccbeaa3-1eb6-44ef-bb29-ff1a72925b28

## References

Foxon, Timothy J. 2011. "A coevolutionary framework for analysing a
transition to a sustainable low carbon economy." *Ecological Economics*
70 (12): 2258 to 2267. https://doi.org/10.1016/j.ecolecon.2011.07.014

Holtz, Georg, Floortje Alkemade, Fjalar de Haan, Jonathan Köhler,
Evelina Trutnevyte, Tobias Luthe, Johannes Halbe, et al. 2015.
"Prospects of modelling societal transitions: position paper of an
emerging community." *Environmental Innovation and Societal Transitions*
17: 41 to 58. https://doi.org/10.1016/j.eist.2015.05.006

Schiller, Georg, Tamara Bimesmeier, and Anh T.V. Pham. 2020. "Method
for quantifying supply and demand of construction minerals in urban
regions: a case study of Hanoi and its hinterland." *Sustainability*
12 (11). https://doi.org/10.3390/su12114358

Suprun, Emiliya, Oz Sahin, Rodney Anthony Stewart, and Kriengsak
Panuwatwanich. 2019. "Examining transition pathways to construction
innovation in Russia: a System Dynamics approach." *International
Journal of Construction Management*.
https://doi.org/10.1080/15623599.2019.1637628

Sverdrup, Harald U., Deniz Koca, and Peter Schlyter. 2017. "A simple
System Dynamics model for the global production rate of sand, gravel,
crushed rock and stone, market prices and long-term supply embedded
into the WORLD6 model." *BioPhysical Economics and Resource Quality*
2 (2): 8. https://doi.org/10.1007/s41247-017-0023-2
