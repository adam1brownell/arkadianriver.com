---
layout: post
title: "Behavioral Neuroscience III"
excerpt: "Membrane Potential: How do neurons work?"
date: 2019-03-10
categories:
  - edu_bank
background-image: edu_imgs/neuron.jpg
---

## Membrane Potential: How Neurons Work

Neurons communicate by sending signals to each other called Action Potentials. To understand how action potentials work, we need to discuss few fundamental concepts of physics/chemistry  
### Diffusion of Ions
**Diffusion** is the movement of a substance from high concentration to low concentration. Image food coloring being dropped into water—it slowly starts to spread out from area of high concentration (lots of food coloring) to areas with low concentration (no food coloring) until it is evenly distributed. When an **ion**, or charged particle, diffuses, something extra happens. As the charged particle spreads out to areas of low concentration, it starts to create a charge in these new areas. This new charge creates prevents new, similarly charged particles from entering. In a sense, it is diffusion for electricity/charge.

For example, Sodium (Na+) has a positive charge. Imagine a high concentration of Na+ floating around a cell that has no Na+ inside it whatsoever (very low concentration). The moment that cell “allows” Na+ to enter, there is a HUGE rush of Na+ from the outside due to diffusion. As this flow occurs, the new positively-charged Na+ ions have given the cell an overall positive charge now. Remember: In electricity, similar charges repel each other. So, the positive charged cell starts to repel the Na+ outside the cell, and it gets harder and harder for new Na+ to rush inside. This is different than in the food coloring example, where diffusion will only stops once all areas have EQUAL concentrations—the charged particles make it so diffusion will stop prior to this point, leaving the cell with a slightly lower concentration of Na+ than the outside.

Eventually the cell and outside Na+ reach a ceasefire, where the pressure from the charges is too strong and the difference in diffusion is too low for any Na+ to make it inside. To some up with fancier language: The _efflux_ of Na+ due to positive voltage equals the _influx_ of Na+ due to concentration gradient.

This ceasefire, or when the pressure of Na+ inside the cell due to the positive charge equals the strength of the Na+ outside wanting to diffuse, is called the **Equilibrium Potential**, and it is a fundamental way that neuron communication works.


### Equilibrium Potential & Relative Permeability

At Equilibrium Potential, the cell has a charge from all the ions that flooded inside. You can calculate the Equilibrium Potential for each ion with the **Nernst Equation**:

        E=58mV*log⁡((Concentration outside)/(Concentration inside))

\*For the math inclined, you can see that if the concentration inside and outside was the same, the charge would be 0, because the log(1) = 0. But that is never the case due to the voltage within the cell\*


Equilibrium Potentials for different ions found in neurons:
- Sodium (Na+) = +50mV
- Potassium (K+) = -80mV
- Chlorine (Cl-) = -80mV
- Calcium (Ca++) = +134mV

A neuron’s **membrane potential** is the equilibrium potential of the entire neuron taking into account all these ions’ individual equilibrium potentials. The **resting potential**, or membrane potential when the neuron is not firing, is about -70mV.

It is important to know that neurons have a thick membrane called the Phospholipid Bilayer that prevents pretty much anything from getting inside. Only when special, chemical-specific gates are opened can any ions get inside and diffusion take place. The controlling of what materials enter/leave the cell is called **Relative Permeability**.

**Sodium (Na+)** is the most important compound when it comes to our neurons communicating—it is key to triggering action potentials. To get inside the cell, Na+ has to pass through **Sodium Channels**. These channels are **voltage-gated**, which means they only “turn on” when the neuron reaches a certain voltage level. This is crucial to understanding how neurons control the flow of Na+ into the axon.

### Action Potentials

*Picture of resting potential over an action potential*


Prior to an action potential, a neuron is at resting potential. It then receives a signal from a nearby cell, which causes the cell to **depolarize**, or gain a positive charge, ever so slightly. This slight depolarization causes a tiny amount of voltage-gated sodium channels to open, which allows more Na+ ions inside, which causes the cell to depolarize even more. Neurons work on an **All-or-None Activation**, where the neuron either fully triggers an action potential, or doesn’t fire at all—there is not stronger or weaker neuron action potential. What causes a full action potential is if the depolarization from a nearby action potential pushes the cell above the Threshold. The **Threshold**, also called the **Trigger Event**, is the point at which as the cell becomes more depolarized, more sodium channels open, allowing more Na+ to enter, causing the cell to depolarize even further. This **Domino Effect** of depolarization-Sodium Channels-Na+ influx-depolarization pushes the membrane potential very quickly to the Na+ Equilibrium Potential of +50mV—Sodium overwhelms the neuron.

Incoming signals come in two forms: EPSPs and IPSPs. **Excitatory Post-synaptic Potentials (EPSPs)** open sodium channels and depolarize the cell, causing “bumps” in the membrane potential. It takes several EPSPs to push the membrane potential over the threshold. This can be done through either **Temporal Summation**, or multiple EPSPs in rapid succession of each other, or **Spatial Summation**, multiple EPSPs from different neighboring neurons. **Inhibitory Post-synaptic Potentials (IPSPs)** open potassium or chlorine channels and hyperpolarize-- to gain more negative charge. IPSPs make EPSPs and depolarizations less effective.

### Refractory Period

After the peak of the action potential, the membrane potential begins to polarize again towards the resting potential. This is caused by several things:

- After long periods of being active, sodium channels naturally start to get tired and turn off, restricting Na+ ability to depolarize the cell and lower the membrane potential.
- As more sodium channels turn off due to inactivity and Na+ begins to leave the cell, even more sodium channels turn off due to the neuron no longer be depolarized enough for them to function
- **Potassium channels** are also activated by depolarization but are slower to open the sodium channels. This influx of K+ ions (which has an Equilibrium Potential of -80mV) continues to push the overall voltage down, causing even more sodium channels to close

The combination of sodium channels closing and potassium channels opening/closing slower causes a huge crash in membrane potential, resulting in a voltage even lower than resting potential. The lower voltage, along with the “exhausted” sodium channels, makes it impossible for the neuron to fire again for a short period of 1 – 2ms. This is called the **Refractory Period**. After a short refractory period, the neuron returns to resting potential

It is interesting to note natural toxins/poisons cause problems with sodium channels. Saxitoxin found in Pufferfish prevents sodium channels from opening up in the first place, and Batrachotoxin found in Dart Frogs prevents sodium channels from closing.

An additional way that a neuron recovers from an action potential is the **Sodium-Potassium Pump**, where the neuron takes in more K+ ions and flushes out Na+ ions to return to resting potential quicker

### Conduction

While we have seen how a neuron depolarizes and then repolarizes, we haven’t discussed how action potential travel to synapses to transmit a signal to other neurons.

The rapid change in membrane potential creates and electrical charge. This charge then travels up the axon from the cell body to the synapses. This is done through **conduction**, in which the Na+ ions that rush in during an action potential depolarize the forward-neighboring patch of axon and cause an action potential to arise there as well. The entering Na+ fails to excite backward patches of the axon, and continues to push the electrical charge forward, because it is in a refractory state.

We said previously that myelin helps signal fire quicker, and that is because it reduces the capacitance, or how much charge is required to change the membrane potential. By wrapping sections of axon in myelin fat, entire sections of axon can be depolarized with only a few Na+ ions. This makes depolarization require less ions, less energy (less ions to remove afterwards), and quicker depolarization. The un-myelinated sections of axons where ions diffuse into the neuron are called Nodes of Ranvier.

### Synapses & Receptors

When the action potential reaches the synaptic terminal at the end of the axon, it opens voltage-gated **calcium (Ca++) channels**. The entering Ca++ triggers the activation of **synaptic vesicles**, bubbles that are filled with thousands of neurotransmitters. These transmitters are then released into the synaptic cleft. As they cross the cleft and reach the neighboring neuron’s dendrites, it binds to nearby receptors, triggering either an EPSP or an IPSP. The neurotransmitters left in the synaptic cleft are cleared away by glia cells, reabsorbed by the synapse, or deteriorate in the synaptic cleft.

There are two kinds of receptors. **Ionotropic Receptors** are both receptors and ion channels, and therefore result in a fast reaction to the neurotransmitter. **Metabotropic receptors** are receptors that can activate a **G-Protein**, which then can then open an ion channel. Metabotropic receptors have a much slower response rate than ionotropic receptors. Studying receptors is quite an active area of research, as it was only recently that we learned that there is a large variety of receptors that can change synaptic behavior.

**Ligands** are objects that bind to receptors to activate or block ion channels.
- **Endogenous**: Neurotransmitters and Hormones
- **Exogenous**: Drugs and toxins from outside the body
- **Agonist**: Ligand that binds to receptors and opens an ion channel
- **Antagonist**: Ligand that bins to receptors and blocks the opening of a channel
    - **Competitive**: Ligand that prevents the opening of a channel by blocking an agonist’s binding site
    - **Non-competitive**: Ligand that binds to a different binding site, but still prevents the opening of a channel

### Recap
1. 	Diffusion is when objects move from high concentration to low concentration. When charged particles diffuse, this creates an electrical current.
2. Neurons fire because the diffusion of positively-charged sodium into the cell causes an electrical charge to travel up the axon.
3. Neurons transfer these signals by sending neurotransmitters to each other, which causes neighboring neurons to allow different ions to diffuse at different rates
4. After each firing, neurons enter a refractory period where they can’t fire for a short time as they recover
