# Overview

A blob of tips, tricks, observations, and techniques I have picked up while learning how to plan, and communicate those plans.

In this documentation, when I say "ideal schematic" it is being used to describe the appropriate implementation of the standards described here.

## Tips and Tricks
### Planar Embedding
Having trouble with keeping a clean flow to your view?
Check if your graph is **planar_embeddable**:
```
E = edges
V = vertices
 
planar_embeddable = E <= 3V-6 
```

**planar_embeddable** graphs have properties that reduce complexity: 
- they can be drawn with zero bends 
- they can be drawn without edges intersecting. 

placing nodes with even lengths of edges makes the first property obvious. 
  ![planar_embeddable graph](https://github.com/MattHirdler/architecture-toolkit/blob/gh-pages/index.assets/planar_graph.jpg?raw=true "planar_embeddable graph")

If the number of nodes is small (another property that reduces complexity) I usually can pretty quickly filter out the edge.
![planar_embeddable graph with diagonal edges](https://github.com/MattHirdler/architecture-toolkit/blob/gh-pages/index.assets/planar_graph_diagonal.jpg?raw=true "planar_embeddable graph with diagonal edges")

Then it seems to be a matter of re-sizing the boxes until every relationship is perpendicular, and voila!
![planar_embeddable graph](https://github.com/MattHirdler/architecture-toolkit/blob/gh-pages/index.assets/planar_embedding.jpg?raw=true "planar_embeddable graph")

Anecdotally the bottom is the clear winner. This alone is far from everything you can/should do. But so far it has proven the most repeatable and impactful.

I would love to find a systematic approach to sizing nodes that would pair with this well (ideally based off some intrinsic property to the design).

### Models
Models should be preferred over pictures.
ArchiMate is a very strong option when it comes to modelling.
It offers the ability to model relationships once, and create many different view.

### Properties of an "Ideal Schematic"
- it must be a planar embeddable graph.
- edges must be straight.
- edges should be perpendicular.
- edges and nodes should be uniform.
- edge labels should be positioned consistently.
- information should be presented literally.
- vertices should be uniformly denser than sparse. 

Remember: Every time you put a kink in an edge, you are adding extra information that rarely represents anything functional.
