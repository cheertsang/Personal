# Straight singular sedimentation tank for a modular plant

**Team: La Mera Chimba**
- Cheer Tsang (ct542@cornell.edu)
- Kevin Sarmiento (ks2255@cornell.edu)
- Giancarlo Pacenza (gap75@cornell.edu)
- Walter Guardado (wg249@cornell.edu)

## Introduction/Background

The capital cost of a traditional AguaClara plant is fixed at roughly \$100,000, plus an additional \$8,000 per L/s of plant capacity ([Weber-Shirk, 2019](https://github.com/AguaClara/CEE4540_Master/raw/master/Lectures/In%20Class/AguaClara%20Ecosystem.pptx)). This cost is due to the fact that traditional AguaClara plants are constructed of mostly concrete, which require extensive excavation and on-site construction. The higher the plant capacity, the price per L/s decreases. Thus, traditional AguaClara plants are more cost-efficient for larger communities and often not feasible for serving smaller communities that require flow rates of less than 5 L/s. In order to serve this market of smaller communities, AguaClara designed the PF300, a pre-fabricated 1 L/s plant intended to serve a population of 300 ([Buhl et. al, 2016](https://confluence.cornell.edu/pages/viewpage.action?pageId=333352626&preview=/333352626/335435860/Prefab_Final_Report.pdf)).

AguaClara would like to expand its efforts in serving a range of smaller communities. Thus, we would like to design a range of designs that accommodate for flow rates of 1 to 5 L/s ("plantitas"). In particular, we will be focusing on the design of the sedimentation tank. The current design of the PF300 sedimentation tank consists of two sections of a cylindrical corrugated HDPE pipe welded together at a 30 degree angle (Figure 1):

<p align="center">
  <img src="https://github.com/cheertsang/Personal/blob/master/IMG_3748.JPG?raw=True" height=500>
</p>
<p align="center">

**Figure 1:** The fully fabricated PF300 sedimentation tank ([Herrera et. al, 2016](https://www.overleaf.com/read/cnkbrqcsxxfn)).

Like the traditional AguaClara plants, the internal structure of the sedimentation tank consists of sedimentation plates, a floc hopper, an inlet manifold, outlet manifold, base plates, and a jet reverser (Figure 2).

<p align="center">
  <img src="https://github.com/cheertsang/Personal/blob/master/sed_tank_schematic.png?raw=True" height=300>
</p>
<p align="center">

**Figure 2:** Schematic of the internal structure of a PF300 sedimentation tank ([Buhl et. al, 2016](https://confluence.cornell.edu/pages/viewpage.action?pageId=333352626&preview=/333352626/335435860/Prefab_Final_Report.pdf)).

One of the issues with the current design is that welding the two sections of corrugated HDPE pipe together is labor-intensive and difficult to line up precisely. We want to explore altering the design of the sedimentation tank to a single larger diameter tank size to avoid the necessity of welding two sections of pipe. This would allow us to increase the capacity of the PF300 and make it easier to fabricate.

## General Plan/Steps

The steps we will follow to create our final design are as follows:

1. Calculate plant capacity
2. Inlet manifold and diffuser specifications
2. Plate settler specifications (dimensions, spacing)
3. Bottom geometry and jet reverser design

### Important Constraints

As we develop the new design, there are important constraints to keep in mind - namely factors that will determine, in part, the direction of our design. The constraints we are placing on our design are:

  1. **Upflow Velocity** - The main factor we need to keep constant in our sedimentation tank is the upflow velocity. This is because much of the efficacy of the sedimentation tank lies in the ability to suspend flocs. This in turn comes from the upflow velocity. As we modify parameter in the sedimentation tank, we are constrained by the need to maintain an upflow velocity of 1 mm/s. As shown in the AguaClara design, this is a sufficient upflow velocity for ensuring floc suspension. Therefore, we will ensure that our redesigned sedimentation tank maintains the upflow velocity of 1 mm/s.

  2. **Cost** - One of the goals of AguaClara has always been to provide a relatively cheap option. With the modified design, we wish to preserve this goal and ensure that the new design is relatively cheap to manufacture. In particular, we want to ensure that any cost increases are sufficiently justified by overall improvements in the plant. One approach to analyze this (in comparison to the current design) would be to establish a metric of cost per L/s.

  3. **Material/Space** - A slightly more subjective constraint is our use of space. In addition to being cost effective, we want to make sure the plant is space effective. This involves considerations of how much material we are using and what ground surface area the plant is occupying. Part of the application of this constraint would be the subjective evaluation of the space use; that is, intuitively speaking, does the plant seem to warrant the space it is occupying given the benefit it is providing? A more concrete application would be to measure the area occupied by the plant per L/s. This way, we can objectively measure whether or not an increase in space consumed is leading to a proportional increase in capacity.

  4. **Ease of Construction** - One of the main motivations for pursuing a new design was the pursuit of a small plant that is easier to construct. As we concretify the design, we want ot be sure that we are not adding unnecessary complications. This constraint will be evaluated more intuitively by making comparisons between the construction process for hte PF300 and our redesigned version.

### Trade Offs

Given that our proposal is an adaptation of a current design, we must think about what we gain in the context of what we lose. Some improvements our proposal is designed to provide are an increased flow rate and an increased ease of construction. The idea is that a straight structure will be much easier to build than the bent structure. Additionally, this structure will be larger, thus allowign for an increased flow rate.

On the other hand, one benefit of the previous structure was that the plate settlers ran parallel to the upper portion of the tube. This eliminated the little triangle of wasted space by the walls of the tank. With our straight-tank design, we are reintroducing those triangles of space. We must consider the cost of reintroducing this space.

Additionally, we have to consider the fact that placing plate settlers at an angle in an upright tank may be more complicated than placing them parallel to the tank walls. We must analyze whether this potential complexity offsets the added simplicity of a straight tube.

### Operator/User Specifications

An important consideration is the ease of use for the plant operator. The only requirement is

### Major Design Alternatives

Measure of improvement
  - material amount per liter per second
  - area occupied by plant per liter per second
  - difficulty of construction
  - Cost per liter per second

Table Comparing Alternatives

Evaluation of Most viable Alternatives

## Methods

The following packages were used in the calculations below:

```python
import aguaclara
import aguaclara.core.physchem as pc
import aguaclara.core.head_loss as minorloss
import aguaclara.core.pipes as pipes
import aguaclara.design.human_access as ha
import aguaclara.core.constants as con
from aguaclara.core.units import unit_registry as u
import aguaclara.core.utility as ut
import numpy as np
import matplotlib.pyplot as plt
import aguaclara.design.sed_tank as st

```

The new sedimentation tank design will be based on the specifications of a [2710 gallon water storage tank](https://www.plastic-mart.com/product/8591/2500-gallon-enduraplas-vertical-water-tank), which will replace the two sections of corrugated HDPE pipe. The specifications are as follows:

- Tank Volume: 2710 gallons (10258.47 liters)
- Diameter: 90 in (2.286 m)
- Height: 113 in (2.8702 m)
- Material: Polyethylene
- Cost: $1,129.09

```python
volume = (2710*u.gallon).to(u.L)
diam = (90*u.inch).to(u.m)
height = (113*u.inch).to(u.m)
```

### Plant Capacity

The plant capacity was calculated using the required upflow velocity in the sedimentation tank and the diameter of the tank.

Using conservation of mass:
$$ Q = vA $$

where:
- $v$: upflow velocity required for floc blanket suspension
- $A$: cross-sectional area of sedimentation tank

```python
vup = 1*u.mm/u.s
A = pc.area_circle(diam)
Q = (vup*A).to(u.L/u.s)

print('The plant capacity is ' + str(Q))
```
**The plant capacity is 4.104 liter / second**

### Inlet manifold and diffuser specifications

In order to begin to determine the size of the diffusers and the manifolds we first identified the relevant constraints for designing these components. First, the maximum head loss from the diffuser has been set to be 1 cm. This is due to the fact that there is a small energy requirement to keep the floc blanket suspended. Using this we can determine the maximum velocity at which water will leave the diffusers. We use the following head loss equation:

$$H_{Lmax}= \frac{V_{max}^2}{2g}$$

from this we can solve for the maximum velocity
$$V_{max}=\sqrt{2gH_{Lmax}}$$

```python
max_HL = 1*u.centimeter


```

### Plate Settler Specifications

The next design parameters we have to consider are the dimensions of the plate settlers. These dimensions boil down to plate spacing, plate angle, plate length, and number of plates. In particular, we want to consider how, if at all, the new dimensions will deviate from the traditional AguaClara plant dimensions. Our plates will use the same thickness as those used by the traditional AguaClara plants (2 mm).

The first dimension to consider is the spacing between plate settlers. The spacing is ultimately determined by the need to prevent floc rollup. As the plates come closer together, the velocity of water through the plates increases. This is due to the need to compensate for a smaller area and conserve flow. As the velocity of water near the plates increases, the flocs feel a stronger force combating the force of gravity. At the point where gravitational forces and fluid drag forces match, the floc will no longer have the tendency to slide down the plate settler. Unfortunately, we need the flocs to slide off the plate settler and be resuspended in the floc blanket. Therefore, assuming we want to maintain an upflow velocity of 1 mm/s, this point where gravitational forces equal fluid drag forces imposes a limit on how close we can allow the plate settlers to be.

Following with the AguaClara design choices, we assume an upflow velocity of 1 mm/s and a capture velocity of 0.12 mm/s. Given these constraints, we know that we require a minimum plate spacing of 2.5 mm to prevent floc rollup. That being said, the AguaClara design opts for a spacing of 2.5 cm. As explained in the text, this is due to the variability in the type of incoming particle. The initial calculations were made for clay-based flocs; in reality, clay-based flocs are not the only flocs that should be expected. This is the reason for the 2.5 cm spacing. Since our own plant faces similar constraints, we will also opt for a spacing of 2.5 cm.

The next dimension of the plate settlers we care about is the plate angle. In determining the angle, we want to make sure we have an angle that allows the flocs to slide down the plates. Currently, the AguaClara design sets the angle for the plates at 60 degrees. Given that we could not find any explicit rational for this choice and given that it seems to be working well, we decided to keep the plate angle at 60 degrees.

Now that we have the spacing between plates and the angle the plates will be set at, we can calculate what the length of the plate settlers should be using the following equation:

$$\frac{S*((v_{up}/v_c)-1)+(T*v_{up})/v_c}{cos(\alpha)sin(\alpha)}$$

where:
- $S$ is spacing between plates
- $T$ is the thickness of the plates
- $v_{up}$ is the upflow velocity
- $v_c$ is the capture velocity
- $\alpha$ is the angle of the plate settlers

```python
S = 2.5*u.cm
T = 2 *u.mm
vup = 1*u.mm/u.s
vc = 0.12*u.mm/u.s
alpha = 60*u.deg

def L_sed_plate(S, vup, vc, T, angle):
  return ((S*((vup/vc)-1)+T*(vup/vc))/(np.sin(angle)*np.cos(angle))).to(u.m)

length = L_sed_plate(S, vup, vc, T, alpha)

print("The plate settlers need to have a length of " + str(length))
```

**Applying the spacing, thickness, angle, and velocities from above, we get that the plate settlers need to be 0.4619 meters in length.**

The final parameter to calculate is the number of plate settlers we can fit in the sedimentation tank. Given that an increase in plate settlers leads to an increase in performance, we want to find the maximum number of plate settlers we can use. To find this value, we apply the following equation:

$$ n = floor(\frac{L_{cantilevered} * tan(\alpha)}{B} + 1) $$

where:
- $L_{cantilevered}$: the maximum length of sed plate sticking out past module pipes without any additional support
- $B$: calculated as $S+T$.
- $n$: the maximum number of plate settlers

```python
L = 20*u.cm
B = S+T

n = np.floor((L*np.tan(alpha))/B + 1)

print('The maximum number of plate settlers is ' + str(n))
```

**The maximum number of plate settlers is 13 dimensionless**

This gives us the number of plates per standard module in a standard AguaClara sedimentation tank. Given the module has a width of 40 inches, in order to adapt this calculation to our design, we will say that this gives the number of plates per 40 inches of width.





### Proposed Solution Techniques

### Analysis
Explain ALL calculations step by step including why you are doing the calculation.
### Preliminary Design

Equations
Go metric.



The Markdown worksheet should include a method to determine any major design constraints, proposed solution technique(s), analysis, sketches, preliminary design, with extensive documentation. Any equations that you present must be well documented with explanation of how you derived those equations and how you are using those equations.







## References

Herrera, D., Hua, Y., Kim, S., King, S., Yang, F. (Fall 2016). Pre-Fabrication 1 L/s, Fall 2016. Retrieved from https://www.overleaf.com/read/cnkbrqcsxxfn.

Buhl, K., DeVoe, C., Kruskopf, M., Yang, F. (Spring 2016). Prefab 1 L/s, Spring 2016. Retrieved from https://confluence.cornell.edu/pages/viewpage.action?pageId=333352626&preview=/333352626/335435860/Prefab_Final_Report.pdf.

Weber-Shirk, M., Juan, G., Clare, O., William, P., Leonard, L., Yingda, D., & Zoe, M. (2018). AguaClara Textbook. AguaClara Cornell. Retrieved from https://aguaclara.github.io/Textbook/index.htm

Weber-Shirk, M. (2019, February 7). AguaClara Ecosystem.
https://github.com/AguaClara/CEE4540_Master/raw/master/Lectures/In%20Class/AguaClara%20Ecosystem.pptx

2710 Gallon Plastic Water Storage Tank. (n.d.). Retrieved April 19, 2019, from https://www.plastic-mart.com/product/8591/2500-gallon-enduraplas-vertical-water-tank
