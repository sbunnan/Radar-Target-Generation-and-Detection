# Radar-Target-Generation-and-Detection

Implementation steps for the 2D CFAR process.

	1.Pick the number of training cells Tr and Td  for both the dimension(range and doppler). 
	2.Pick the number of guard  call Gr and Gd for both the dimensions. 
	3.Start the sliding window one call at a time across the complete matrix. 
	4.On each step, sum the noise within the lagging training cells in both the dimensions and calculate the average sum of noise in the training cells  to determine the threshold.
	5.Select appropriate offset value to select the threshold.
	6.Compare the signal in CUT(cell under test) with the threshold value,
	7.Depending on the value of the signal compared to threshold value which indicates the detection of an object, update the respective matrix index.  


Selection of Training, Guard cells and offset.
	1.Selection of training cells depends on the environment, if there is dense enviroment, then fever training cells are required. 
	2.Selection of guard cells depend on the reflective property of the target, if the target reflection is strong, then the noise will be distributed to the surrounding bins in such case, we may need biggers guard cells. 
	4.Selection of offset is based on the noise level,if noise level is high, we may need higher threshold to avoid false positive cases. 

Steps taken to suppress the non-thresholded cells at the edges.
	Since the CUT are not located at the edges, since training cells and guard cells occupy the edges, we suppress the edges to zero. 

