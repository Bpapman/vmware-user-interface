Second meeting in which we further explore specific languages and design aspects of the GUI.

Specific Language and GUI Design & Risk assessment
Design/prototype 2 meeting

> Processing Language-
> > Drop down box implementations
> > Zoom ability
> > Node creation dynamic array's
> > File i/o similar to java
> > Auto compile into executable


> 'Ideal User Interface' - overview of goals and implementation
> > Section 1: overview
      * Designed as a script ran from VMWare
      * Has either intervals of updates or specific 'refresh' calls for the information and graphical display



> Section 2: I/O
> > A: Initial Data File from VMWare: READ ONLY Arranged in 4 sections
> > > i) header: Defines how each data structure is set up
> > > ii) Node info: Defines node type, location, optional name, and other attributes
> > > iii) Edge info: defines edge name and attributes
> > > iv) relationships: defines node-edge relationships


> B:
> Header:
> > time stamp
> > geographic map on/off
> > node attribute 1-n
> > edge attribute 1-n


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


#### Re-Visioned Program Design ####

  1. Get Information from VMware using VMperl Scripting.
  1. Pass that Information to a standard file format that we will     define.
  1. Pass information from our file to a processing program that will be the host of our information to use for the GUI
  1. The GUI should be able to call upon methods from the processing program to display information to the user in a meaningful way.