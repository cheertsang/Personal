# Straight singular sedimentation tank for a modular plant

**Team: La Mera Chimba**
- Cheer Tsang (ct542@cornell.edu)
- Kevin Sarmiento (ks2255@cornell.edu)
- Giancarlo Pacenza (gap75@cornell.edu)
- Walter Guardado (wg249@cornell.edu)


[Wow! This is a very impressive start! You have clearly connected to the motivation that the world needs better sedimentation tanks! And this analysis makes it clear that there are so many opportunities to make improvements. Add your thought process for selecting the tank that you chose. We need prices urgently to help guide this design process. We need to be absolutely sure that it make sense to build larger diameter prefab sed tanks. I suspect this will be economically favorable, but it isn't clear yet! Perhaps include additional reflections on the tradeoffs of having multiple different sizes of sed tanks versus using a modular system where you vary the number of sed tanks depending on demand.]:#

## Introduction/Background

The capital cost of a traditional AguaClara plant is fixed at roughly \$100,000, plus an additional \$8,000 per L/s of plant capacity ([Weber-Shirk, 2019](https://github.com/AguaClara/CEE4540_Master/raw/master/Lectures/In%20Class/AguaClara%20Ecosystem.pptx)). This cost is due to the fact that traditional AguaClara plants are constructed of mostly concrete, which require extensive excavation and on-site construction. The higher the plant capacity, the price per L/s decreases. Thus, traditional AguaClara plants are more cost-efficient for larger communities and often not feasible for serving smaller communities that require flow rates of less than 5 L/s. In order to serve this market of smaller communities, AguaClara designed the PF300, a pre-fabricated 1 L/s plant intended to serve a population of 300 ([Buhl et. al, 2016](https://confluence.cornell.edu/pages/viewpage.action?pageId=333352626&preview=/333352626/335435860/Prefab_Final_Report.pdf)).

AguaClara would like to expand its efforts in serving a range of smaller communities. Thus, we would like to design a range of designs that accommodate for flow rates of 1 to 5 L/s ("plantitas"). In particular, we will be focusing on the design of the sedimentation tank. The current design of the PF300 sedimentation tank consists of two sections of a cylindrical corrugated HDPE pipe welded together at a 30 degree angle (Figure 1):

<p align="center">
  <img src="https://github.com/cheertsang/Personal/blob/master/IMG_3748.JPG?raw=True" height=500>
</p>
<p align="center">

**Figure 1:** The fully fabricated PF300 plant. The sedimentation tank is housed in the teal HDPE corrugated pipe ([Herrera et. al, 2016](https://www.overleaf.com/read/cnkbrqcsxxfn)).

Like the traditional AguaClara plants, the internal structure of the sedimentation tank consists of sedimentation plates, a floc hopper, an inlet manifold, outlet manifold, base plates, and a jet reverser (Figure 2).

<p align="center">
  <img src="https://github.com/cheertsang/Personal/blob/master/sed_tank_schematic.png?raw=True" height=300>
</p>
<p align="center">

**Figure 2:** Schematic of the internal structure of a PF300 sedimentation tank ([Buhl et. al, 2016](https://confluence.cornell.edu/pages/viewpage.action?pageId=333352626&preview=/333352626/335435860/Prefab_Final_Report.pdf)).




One of the issues with the current design is that welding the two sections of corrugated HDPE pipe together is labor-intensive and difficult to line up precisely. We want to explore altering the design of the sedimentation tank to a single larger diameter tank size to avoid the necessity of welding two sections of pipe. This would allow us to increase the capacity of the PF300 and make it easier to fabricate.

[Why did the first version of PF300 have a sloped upper section? ]:#

Because of this we are looking to build a sedimentation tank out of this premade Rotoplast.

<p align="center">
  <img src="https://www.plastic-mart.com/db_images/pm/enduraplas_2500_gallon_water_tank.jpg" height=500>
</p>
<p align="center">

**Figure 3:** a 1500 liter Rotoplast tank that we will be using as a sedimentation tank.

[Note that below you are using a much larger tank.]:#

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

[Right. Space matters because a building enclosure will be required and because land will need to be purchased.]

  4. **Ease of Construction** - One of the main motivations for pursuing a new design was the pursuit of a small plant that is easier to construct. As we concretify [cool word concretificacion???... perhaps use "develop"] the design, we want ot [to... check spelling!] be sure that we are not adding unnecessary complications. This constraint will be evaluated more intuitively by making comparisons between the construction process for *hte* PF300 and our redesigned version.

### Trade Offs

Given that our proposal is an adaptation of a current design, we must think about what we gain in the context of what we lose. Some improvements our proposal is designed to provide are an increased flow rate and an increased ease of construction. The idea is that a straight structure will be much easier to build than the bent structure. Additionally, this structure will be larger, thus *allowign* for an increased flow rate.

On the other hand, one benefit of the previous structure was that the plate settlers ran parallel to the upper portion of the tube. This eliminated the little triangle of wasted space by the walls of the tank. With our straight-tank design, we are reintroducing those triangles of space. We must consider the cost of reintroducing this space.

Additionally, we have to consider the fact that placing plate settlers at an angle in an upright tank may be more complicated than placing them parallel to the tank walls. We must analyze whether this potential complexity offsets the added simplicity of a straight tube.

[The wasted triangles go crazy for small sed tanks with long plate settlers. You can reduce the "triangle" problem by making a bigger sed tank AND by using plate settlers or tube settlers that have a reduced spacing. That is why we are purchasing a honeycomb tube settler system with 3/8" tubes.]

### Operator/User Specifications

An important consideration is the ease of use for the plant operator. The new sedimentation tank will be operated in the same way as the current design, so the new design will not require any additional user specifications.

### Major Design Alternatives

A comparison could be made between using the following design options:
  1. Using one larger capacity plantita (new design)
  2. Using multiple plantitas in conjunction (current design)

In order to evaluate which design would be more practical, the following indicators can be analyzed:
  - Amount of material required per liter per second
  - Area occupied by plant per liter per second
  - Difficulty of construction
  - Cost per liter per second

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
#import aguaclara.design.sed_tank as st
#there is an error in importing the sed tank package

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

[Start with the big picture. Can you build a single valley with jet reverser in this large diameter tank? How much of the tank volume will be lost beneath the sloped walls? Would it make sense to have multiple valleys? How would you set the optimal number of valleys? Take this to the extremes to see what fails. By the way, this is similar to the question of how would you convert a big traditional horizontal sed tank into an AguaClara sed tank? Where will the floc hopper be located? Before we go too far, what are the costs of the different sizes of tanks? Is the cost per L/s treated better for small diameter tanks or large diameter tanks? Or is the tank selection driven by the need to find a tank that has the right height?]:#

In order to begin to determine the size of the diffusers and the manifolds we first identified the relevant constraints for designing these components. First, the maximum head loss from the diffuser has been set to be 1 cm. This is due to the fact that there is a small energy requirement to keep the floc blanket suspended. Using this we can determine the maximum velocity at which water will leave the diffusers. We use the following head loss equation:

$$H_{Lmax}= \frac{V_{max}^2}{2g}$$

from this we can solve for the maximum velocity
$$V_{max}=\sqrt{2gH_{Lmax}}$$

This is an important parameter because it helps us determine the minimum diffuser width that we need to have for our plant. This is determined by the following equation:
$$W_{diff max} = \frac{V_{sed up}}{V_{diff max}}W_{sed} $$
where the $V_{sed up}$ describes the upflow velocity in the active floc blanket region of the sedimentation tank, $V_{diffmax}$ is the maximum diffuser velocity and $W_{sed}$ is the width of the sedimentation tank. We already have the upflow velocity which is 1 $\frac{mm}{s}$ which is the required velocity to keep the floc blanket in suspension. However, finding the width of the sed tank in a circular tank is not as straightforward as the rectangular tanks in larger AguaClara plants. To do this we found an effective tank width by taking into account the floorplan area of the plant and the diameter.
$$\frac{Total Area}{Diameter} = Effective Width$$
$$W_{effective}= \frac{\pi D}{4}$$

Now we can calculate the minimum diffuser width that we can use. That is described by using the following equation:
$$W_{min}=\frac{V_{sed up}W_{effective}}{V_{diffmin}}$$



```python
max_HL = 1*u.centimeter
max_diffuser_vel = ((2*con.GRAVITY*max_HL)**(0.5)).to(u.m/u.s)
W_effective_sedtank = (np.pi * diam) / 4
print('The effective sed tank width is ' + str(W_effective))

W_min_diffuser = ((vup * W_effective_sedtank)/max_diffuser_vel).to(u.millimeter)
print ('The minimum diffuser width is ' +str(W_min_diffuser))

max = (0.5*u.inches).to(u.millimeter)
interval = (1*u.inches/8).to(u.millimeter)
mold_sizes = np.arange(0, max*(1/u.millimeter) , interval*(1/u.millimeter))

print('The range of available mold sizes available to make the diffusers in Honduras are as follows in units of mm '+ str(mold_sizes))

print ('Based on the required minimum width and the width of the diffuser molds available, we will be using a diffuser with a width of 6.35 mm')

diffuser_ND = 1*u.inches
diffuser_SDR = 26
diffuser_ID = pipes.ID_SDR(diffuser_ND, diffuser_SDR)
diffuser_OD = pipes.OD(diffuser_ND)
diffuser_inner_circumferance = diffuser_ID * np.pi
diffuser_thickness = diffuser_OD - diffuser_ID

# after heating and molding the dimensions will change as follows
stretch_ratio = 1/1.2
diffuser_thickness_stretched = diffuser_thickness * stretch_ratio
diffuser_inner_circ_stretch = diffuser_inner_circumferance / stretch_ratio

# If we assume that the corners of our diffuser are perfect squares then we can determine its length and width after molding.

w_diffuser_inside = 6.35*u.millimeter
w_diffuser_outside = w_diffuser_inside + 2*diffuser_thickness_stretched
interior_length_diffuser = ((diffuser_inner_circ_stretch - 2*w_diffuser)).to(u.centimeter)
exterior_length_diffuser = (interior_length_diffuser + 2*diffuser_thickness_stretched).to(u.centimeter)

print ('The diffusers have an inner width of '+str(w_diffuser_inside))
print ('The diffusers have an outer width of '+str(w_diffuser_outside ))
print('The diffusers have an inner length of '+str(interior_length_diffuser))
print('The diffusers have an outer length of '+str(exterior_length_diffuser))

# To determine the number of diffusers that can fit into the sedimentation tank we need to take the diameter of the tank and divide it by the exterior length of one diffuser. We will also take into account that there will be some small spacing between the diffusers during assembly.

spacing_btw_diffusers = 2*u.millimeter
length_per_diffuser = spacing_btw_diffusers*2 + exterior_length_diffuser
num_diffusers = round(diam/length_per_diffuser.to(u.meter))
print ('The total number of diffusers that fit into the sedimentation tank of this plant is '+str(num_diffusers))

#The next task is to calculate the size of the manifold needed to for the required flow rate. These calculations are yet to be completed and will be done soon.

```

### Plate Settler Specifications

The next design parameters we have to consider are the dimensions of the plate settlers. These dimensions boil down to plate spacing, plate angle, plate length, and number of plates. In particular, we want to consider how, if at all, the new dimensions will deviate from the traditional AguaClara plant dimensions. Our plates will use the same thickness as those used by the traditional AguaClara plants (2 mm).

The first dimension to consider is the spacing between plate settlers. The spacing is ultimately determined by the need to prevent floc rollup. As the plates come closer together, the velocity of water through the plates increases. This is due to the need to compensate for a smaller area and conserve flow. As the velocity of water near the plates increases, the flocs feel a stronger force combating the force of gravity. At the point where gravitational forces and fluid drag forces match, the floc will no longer have the tendency to slide down the plate settler. Unfortunately, we need the flocs to slide off the plate settler and be resuspended in the floc blanket. Therefore, assuming we want to maintain an upflow velocity of 1 mm/s, this point where gravitational forces equal fluid drag forces imposes a limit on how close we can allow the plate settlers to be.

Following with the AguaClara design choices, we assume an upflow velocity of 1 mm/s and a capture velocity of 0.12 mm/s. Given these constraints, we know that we require a minimum plate spacing of 2.5 mm to prevent floc rollup. That being said, the AguaClara design opts for a spacing of 2.5 cm. As explained in the text, this is due to the variability in the type of incoming particle. The initial calculations were made for clay-based flocs; in reality, clay-based flocs are not the only flocs that should be expected. This is the reason for the 2.5 cm spacing. Since our own plant faces similar constraints, we will also opt for a spacing of 2.5 cm.

[To be perfectly clear. The 2.5 cm spacing is arbitrary. I pulled it out of the air. I said... Well, 5 cm works. I bet it is conservative. Let's try 2.5 cm. So now we can see that 2.5 cm is the traditional AguaClara design. Time to change this because there could be a significant opportunity to make a more compact sedimentation system if we use a smaller spacing.]:#

The next dimension of the plate settlers we care about is the plate angle. In determining the angle, we want to make sure we have an angle that allows the flocs to slide down the plates. Currently, the AguaClara design sets the angle for the plates at 60 degrees. Given that we could not find any explicit rational for this choice and given that it seems to be working well, we decided to keep the plate angle at 60 degrees.

[Good. I'd add that there isn't a huge advantage to changing this to 50 degrees. ]

Now that we have the spacing between plates and the angle the plates will be set at, we can calculate what the length of the plate settlers should be using the following equation:

$$L = \frac{S*((v_{up}/v_c)-1)+(T*v_{up})/v_c}{cos(\alpha)sin(\alpha)}$$

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
[This doesn't take into account the lost triangle. The lost triangles make the analysis more complicated and suggest using iteration to find the solution. This is because the plates have to get longer to account for plates that are lost in the triangle. The longer plates increase the size of the triangel and lose more plates. If you aren't careful the system blows up and there is not solution! (Ha... That is why the top of the PF300 is sloped!)]:#
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

print('The maximum number of plate settlers per module is ' + str(n))
```

**The maximum number of plate settlers per module is 13 dimensionless**

This gives us the number of plates per standard module in a standard AguaClara sedimentation tank. Given the module has a width of 40 inches, in order to adapt this calculation to our design, we will say that this gives the number of plates per 40 inches of width.

[Our version of plate settlers in your round tank are going to get messy. You will need a support system for each row of plates. UGH. You will need 3 rows of plates. UGH. The width of each plate will be different because of the curved tank. UGH. The width of each plate will vary from bottom to top of the plate. UGH.  ]:#

### Bottom Geometry and Jet Reverser

The bottom geometry and jet reverser are based on the current design. The base plates of the sedimentation tank are placed at a 60 degree angle from each other ([Herrera et. al, 2016](https://www.overleaf.com/read/cnkbrqcsxxfn)). The dimensions of the base plates are calculated using the equation for an ellipse:

$$Minor Axis = Diameter $$
$$\theta = 60 \degree$$
$$Major Axis = \frac{Diameter}{\cos \theta} $$

The jet reverser is fabricated from a PVC pipe cut in half sectionally. The diameter of this half-pipe is 7.5 cm ([Weber-Shirk, 2019](https://github.com/AguaClara/CEE4540_Master/raw/master/Lectures/In%20Class/Sedimentation.pptx)). The length of the half-pipe is equal to the diameter of the sedimentation tank, 2.286 m.

[Analyze options for 1 to n valleys in the sed tank.]:#

specifications of ellipses

energy dissipation rate for flow leaving jet reverser

The calculations below are adapted from [Sedimentation Design Challenge](https://aguaclara.github.io/Textbook/Sedimentation/Sed_Design_Solution.html):

```python
#Calculate the thickness of the jet when it leaves the diffuser. B_diff = S_diff

W_jet_reversed = W_sed * V_sed_up / V_diffuser

#Calculate the maximum energy dissipation rate

EDR_inlet_jet = Pi_jet_plane *((( V_diffuser)**3)
                        / W_jet_reversed).to(u.mW / u.kg)


print('The energy dissipation rate for inlet jet is', EDR_inlet_jet)
```


### Design Comparison

#### Amount of Material Required


#### Area Occupied by Plant


#### Cost Analysis

Table 1:



## Proposed Solution Techniques

Table Comparing Alternatives

Evaluation of Most viable Alternatives

### Analysis
Explain ALL calculations step by step including why you are doing the calculation.
### Preliminary Design

Equations
Go metric.



The Markdown worksheet should include a method to determine any major design constraints, proposed solution technique(s), analysis, sketches, preliminary design, with extensive documentation. Any equations that you present must be well documented with explanation of how you derived those equations and how you are using those equations.

## References

Herrera, D., Hua, Y., Kim, S., King, S., Yang, F. (Fall 2016). Pre-Fabrication 1 L/s, Fall 2016. Retrieved from https://www.overleaf.com/read/cnkbrqcsxxfn.

Buhl, K., DeVoe, C., Kruskopf, M., Yang, F. (Spring 2016). Prefab 1 L/s, Spring 2016. Retrieved from https://confluence.cornell.edu/pages/viewpage.action?pageId=333352626&preview=/333352626/335435860/Prefab_Final_Report.pdf.

Weber-Shirk, M., Juan, G., Clare, O., William, P., Leonard, L., Yingda, D., & Zoe, M. (2018). AguaClara Textbook. AguaClara Cornell. Retrieved from https://aguaclara.github.io/Textbook/index.htm.

Weber-Shirk, M. (2019, February 7). AguaClara Ecosystem.
https://github.com/AguaClara/CEE4540_Master/raw/master/Lectures/In%20Class/AguaClara%20Ecosystem.pptx.

Weber-Shirk, M. (2019, March 12). Sedimentation.
https://github.com/AguaClara/CEE4540_Master/raw/master/Lectures/In%20Class/Sedimentation.pptx.

2710 Gallon Plastic Water Storage Tank. (n.d.). Retrieved April 19, 2019, from https://www.plastic-mart.com/product/8591/2500-gallon-enduraplas-vertical-water-tank.
