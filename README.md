# P2D2SU2, by Mauro MINERVINO


This consists in a set of two elementary codes that perform grid coarsening and conversion to **SU2** native format, from a **PLOT2D** file generated by the program [*CONSTRUCT2D*](https://sourceforge.net/projects/construct2d/).


[*CONSTRUCT2D*](https://sourceforge.net/projects/construct2d/) is a convenient tool to generate two-dimensional structured meshes around aerofoils.
A common case is the C-grid mesh, for aerofoils with zero-thickness trailing edge.


The first code (**<ins>COARSEN_P2D</ins>**) reads in the **PLOT3D** file containing the mesh (as generated by [*CONSTRUCT2D*](https://sourceforge.net/projects/construct2d/)) and a second integer argument ($n>=1$) that specified the number of grid nodes to be skipped along each block direction from the original mesh file.
The code then provides, as an output, a new **PLOT3D** grid file, containing the coarsened mesh. This is useful in performing mesh sensitivities studies, generating coarser grid levels from a reference fine mesh.
Usage is as follows:

`COARSEN_P2D input_file n`


The second code (**<ins>CONVERT2SU2</ins>**) reads in the **PLOT3D** file containing the mesh (it can be either a direct output from [*CONSTRUCT2D*](https://sourceforge.net/projects/construct2d/) or a coarsened mesh file from **<ins>COARSEN_P2D</ins>**) and a second real argument (*scale_f*) that specifies the grid scaling to be applied to the output.
The code then provides, as an output, a new grid file in the native format used by the [Stanford University Unstructured (SU2) suite](https://su2code.github.io/), which can be used for example to simulate the flow-field around the selected aerofoil using its flow solver module (**SU2_CFD**).
Usage is as follows:

`CONVERT2SU2 input_file scale_f`



<ins>Contacts</ins>:
***Mauro MINERVINO***
*Senior Researcher, Italian Aerospace Research Centre (CIRA S.C.p.A.)*
m.minervino@cira.it
