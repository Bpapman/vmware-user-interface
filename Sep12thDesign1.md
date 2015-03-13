First meeting in which we pitch potential languages and design aspects of the project.

# Potential Language and Overall Design Risk assessment #
Design/prootype 1 meeting
> Processing Language-
> > Drop down box implementations
> > Zoom ability
> > Node creation dynamic array's
> > File i/o similar to java
> > Auto compile into executable


> 'Tortoise' - overview of goals and implementation
> > Section 1: overview
      * Slow, but safe in redundancy
      * Largest problem: lack of information about input data
> > > > - solution -> pass the project onto another process (black box)



> Section 2: I/O
> > A: Data File: Arranged in 4 sections
> > > i) header: Defines how each data structure is set up
> > > ii) Node info: defines node names and attributes
> > > iii) Edge info: defines edge name and attributes
> > > iv) relationships: defines node-edge relationships

> > Header:
> > > time stamp
> > > geographic map on/off
> > > node attribute 1-n
> > > edge attribute 1-n


> Nodes:
> > Node1
> > > Attribute1
> > > Attribute2-n

> > Node2
> > > Attribute1
> > > Attribute2-n


> Relationships:
> > Node1:
> > > Edge1, neighbor1
> > > Edge2, neighbor2
> > > Edge n, neighbor n

> > Node2: etc.



> - use the internal structure to generate coordinates:
    * f geographic is flagged on
> > > -> use given x-y coordinates
    * f geographic is flagged off
> > > -> blah blah


> Section 3: Image processing
> > -now just a simplematter of drawing circles and lines
> > -set up buttons to display node, edge info.


> To Add:
> > -Change colors of nodes
> > -Can be done in drawing program


> --Make a 'movie' of the network -> later expansion

> Section 4: Output
> > -Node x,y coordinate
> > > edge1 end x,y coordinate
> > > edge2 end x,y coordinate


> Following the structure:
> > travel to each node:
> > > for every edge of that node write the x,y coordinates of the node

Risk Management:
  1. **How do we use VMWare?**

> 2) Graphing abstract Networks
> 3) The actual GUI
> 4) Cannot touch VMWare programming
> > -> everything is built on top of it
-What aren't the risks?-
  1. Storing Node data

> 2) File I/O
> 3) Scale able implementation
> 4) Node searching (for our purposes)
**Solutions**
> 2) longest/shortest first abstract networks
> 3) Processing libraries : guicomponents
> > controlP5


### Next Meeting Goals ###
  1. More in-depth processing research

> 2) Graphing tools
# Details #

Add your content here.  Format your content with:
  * Text in **bold** or _italic_
  * Headings, paragraphs, and lists
  * Automatic links to other wiki pages