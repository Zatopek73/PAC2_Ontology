# European Medical Device Ontology (MDR-IVDR)

This ontology is part of a PAC2 assignment and focuses on modelling high-risk medical devices (MD) and in vitro diagnostic devices (IVD) under the MDR (EU 2017/745) and IVDR (EU 2017/746) frameworks.
I built it with a fairly practical goal in mind: to take the kind of data that appears in EUDAMED and make it easier to navigate, connect and query. It’s not a full reproduction of the regulation, just a structured approximation of how the domain behaves.

## What I actually tried to model

Instead of overcomplicating things, I focused on the lifecycle of a device and how different pieces of information relate to each other.
So, in simple terms, the ontology links:
devices and their risk classification
the manufacturers responsible for them
post-market events like incidents and corrective actions
One thing that became clear while working on it is that these parts can’t really be separated cleanly. For example, incidents don’t make sense without devices, and devices are always tied to some manufacturer. Because of that, I avoided a strictly modular design.

## Structure (more or less)

There isn’t a strict module system, but you can think of it like this:
Devices / Risk
Covers classification and risk levels based on EU rules. I kept this relatively simple on purpose.
Manufacturers
Includes basic information about the entities involved in design and compliance. This part could definitely be expanded.
Vigilance
Probably the most interesting part. It models incidents and corrective actions (including FSCAs), and connects them back to devices.
## Technical details
Namespace: https://zatopek73.github.io/PAC2_Ontology
Format: OWL (RDF/XML)
Vocabularies: SKOS (for concepts) and VANN (for metadata)

I also added a few SWRL rules. They’re not very complex, but they help avoid manually asserting relationships, especially between incidents and devices.

## Validation (what I checked and why)
I ran a couple of tools mainly to avoid obvious mistakes:
OOPS! → helped catch modelling issues (some domain/range problems showed up early on)
FOOPS! → just to see how well it aligns with FAIR principles
Reasoners: Pellet and HermiT
Both reasoners were useful to check consistency. Pellet is also helpful if you want to see how the SWRL rules behave.

## How to open it
Download PAC2_Parrado_Ontology.owl
Open it in Protégé (I used version 5.6.0)
Run a reasoner
After that, inferred relationships should appear (depending on the reasoner you use).

## Final notes
This isn’t meant to be a complete or production-ready ontology. Some areas are intentionally simplified, and others could be extended quite a bit.
Still, the model is consistent, works with standard tools, and reflects the main relationships in the domain reasonably well.

Author: Pablo Parrado Gamito
Context: UOC, Knowledge Representation PAC2 – 2026
