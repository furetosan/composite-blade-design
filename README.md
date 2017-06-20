
Introduction
====================

| |CN|ENG|   |
|---|----|-----|-----|
|1|`复合材料层合板计算`|[Composite Material Calculation with CLT][CLT]| [Introduction](#composite-material-calculation-with-clt)|
|2|`开闭剖面工程梁计算`|[Engineer Beam Calculation with open or closed profile][CLT] |[Introduction](#engineer-beam-calculation-with-open-or-closed-profile)|

`read the program introduction for more details ` [Here](/doc/pro_introduction.pdf)  
[Running requirements](#running-requirements) | [Installation](#installation) | [License](#license) 
#### MY GRADUATION THESIS IN TUBS,NOT FINISH,ALL RIGHT RESERVE.
********************************
## Composite Material Calculation with CLT
* The main package is a Python composite materials calculation package.
The laminate stresses, strain and failure Criterion based on the Classical Lamination Theory ([CLT](https://en.wikipedia.org/wiki/Composite_laminates)).  

	- You can define the lamina's fibre and matrix's parameters like the Elastic moduli
	![](http://latex.codecogs.com/gif.latex?E_{1},E_{2}),
	 Shear moduli ![](http://latex.codecogs.com/gif.latex?G) and strength, then define lamina's layer angle and thickness in the next step.
		
	- After define the lamina you can get the matrix such as ![A,B,D,Q](http://latex.codecogs.com/gif.latex?A,B,D,Q,\\bar{Q}) and so on by use the ***Laminate class*** or you can define the laminate directly.

	- Use the ***Load class*** and load the force and moment to the laminate to calculate the stress ![](http://latex.codecogs.com/gif.latex?\\sigma) and stain ![](http://latex.codecogs.com/gif.latex?\\epsilon) of each lamina.

	- Use the ***Failure_Cirterion class*** and you can choose different theories to check witch lamina failure or not.

* The *laminate_plugin.py* can plot the stress and strain distribution in the laminate in the COS(xy or 12), print the results in _Excel_ formate and save it in _Excel_.

*****************************************************

## Engineer Beam Calculation with open or closed profile
* You need to distinguish the shape of the profile, open, closed or mixed and choose the right functions to calculate.
	* You can give the coordinate value of the points of the profile in a _Excel_ table, you may also need to add or remove some edges, change the thickness between the edges of the profile generated by the ***read_exe class***

	* Use the ***profile_constant class*** to calculate the profile's engineer constant like the second moment of area 
	![](http://latex.codecogs.com/gif.latex?I_{x},I_{y},I_{xy}) and use the parameters in the next steps, you can also choose whether move the profile to its centroid.

	* If the profile is a open one, you can use the ***open_profile class*** directly, it can calculate the 
	![](http://latex.codecogs.com/gif.latex?S_{x},S_{y}) and the give the _Shear Flow_ distribution under the shear force ![](http://latex.codecogs.com/gif.latex?Q_{x},Q_{y}) along the path you choose and you can get the shear center if need.  
	* If the profile is a close one with more than one close cells, you need to choose cut points to make the profile become a open one, then choose the integrate paths and use the ***open_profile class*** to get the shear flow in the 'open' profile. Last,  use the functions in ***close_profile.py*** to get the shear flow in each close cell, get the shear center, get the twist angle and some more results you need.
	
	![](http://latex.codecogs.com/gif.latex?S_%7Bx%7D%3D%20%5Cint_%7BA%7D%5E%7B%20%7D%20ydA)  
	![](http://latex.codecogs.com/gif.latex?S_%7By%7D%3D%20%5Cint_%7BA%7D%5E%7B%20%7D%20xdA)
	


* There are many different kind of plug-ins you can use to help you plot the results in 2D or 3D.
	![beam at Qx=1](https://github.com/Eacaen/TEMP_TUBS/blob/master/fig/t1.gif 'Shear ceter')
	![close-beam at Qx=1](https://github.com/Eacaen/TEMP_TUBS/blob/master/fig/two_close_cells.gif 'Shear flow')
	![close-beam at Qx=1](https://github.com/Eacaen/TEMP_TUBS/blob/master/fig/two_close_cells_out.gif 'Shear flow')
*****************************************************
### Running requirements
	Python > v2.7
	Numpy
	Scipy
	Sympy
	matplotlib

### Installation         
>Copy the source files in the local directory and add the PATH in the system or copy the files to the Python's "site-packages" folder.  
>Copy the source file in you own file and develop the new function by yourself.

### License
---------------------------------------------------------
[CLT]:https://github.com/Eacaen/composite-blade-design  "CLT"
 
