# Discription:
This app helps to visualize pO2pts, stalling segments on angiogram and get branch order statistics for that data.

# input:
Angiogram volume <br/>
A file name is provided for a MAT or TIF file that contains the volumetric image of the angiogram. This is generally the angiogram image file and not a segmented angiogram.

Graph file <br/>
A file name is provided for a MAT file that contains the graph information with the following fields: <br/>
Graph.nodes [Nx3] - This is the 3D position of each of the N nodes in the graph <br/>
Graph.edges [Mx2] - This is the list of M edges giving the index for each of the 2 nodes connected by the given edge. <br/>
Graph.diam [Nx1] - This is the diameter at each node in units of micrometers. <br/>
Graph.nodeType [Nx1] - This indicates whether a node is an artery (1), a capillary (2), or a vein(3). This is optional in the input file. <br/>
Graph.segInfo - This is a data structure that contains information about the nodes and edges contained in each vascular segment.

OCT stall data <br/>
This is the output saved from capStallGUI. <br/>
The input has 5 variables: <br/>
Cap [Nx2] - contains 2D coordinates of the capillary stall points in the MIP coordinate system <br/>
Pts [Nx3] - contains 3D coordinates of the capillary stall points in the 3D average volume <br/>
Seg [Nx1]- is a structure data type. <br/>
Seg.pos [MX3]- contains positions of the capillary segment. Note that the number of node points M generally differs for each capillary segment. <br/>
Seg.mask [Px1] - contains a list of indices into the volume image indicating the voxels corresponding to the masked capillary segment. <br/>
Int_ts [N*T] - contains the intensity time series of each segment averaged over the list of Seg.mask voxels for the given segment. <br/>
StallingMatrix [N*T] - is binary matrix with stalls indicated as 1 and non-stalls as 0. This is the famous stall-o-gram. <br/>
N - number of stalling capillary segments <br/>
T - number of images in the time series

pO2 Data <br/>
This is pO2 points information
pO2pts [Nx3] - contains 3D coordinates of pO2 pts in the measured volume.



