# Photoionization-Modeling
## Motivation
This project is part of a research experience (REU) I undertook in the summer of 2021 at the University of Texas at Austin under the mentorship of Danielle Berg and Karla Z. Arellano-Co’rdova, as well as program coordinator Jogee Shardha. My research was funded by the Department of Defense and the National Science Foundation. 
## Introduction
The COS Legacy Archive Spectroscopic SurveY (CLASSY; PI: Berg) marks the construction of the first high quality, high resolution far-UV spectral database of 45 nearby star-forming galaxies. The CLASSY sample of nearby galaxies spans a broad range of properties that pose a challenge to our understanding of how very high ionization emission lines are produced. 

My research goal was to use the photoionization modeling code CLOUDY (Ferland et al. 2013) to model each of the 45 CLASSY
galaxies individually using Binary Population and Spectral Synthesis (BPASS; Eldridge & Stanway 2016) and the measured nebular conditions (Berg et al. 2021) to constrain the intrinsic ionizing continuum and reproduce the observed emission-line spectra.
## Methodology
There are 3 steps we took: 
1) Compiled the CLASSY data and created the grids of cloudy files, 
2) ran the photoionization models and extracted the resulting parameters, and 
3) following the method of Berg et al. (2018), analyzed a test galaxy: J104457.

For the first step, I transformed the input parameters into a Pandas DataFrame. Then, I constrained the parameters using the 3σ error bar to create a grid of galaxy variations. The galaxies variations were stored as a dictionary of data frames, essentially expanding our data from R^2 to R^3. I programmed a function to scan this dictionary and write the input files. Finally, a bash script was used to model the galaxy variations for J1044+0353. **The main source code can be found [here](https://github.com/jat2211/Photoionization-Modeling/blob/main/Galaxy%20Photoionization%20Modeling.ipynb)**, of which I have written in its entirety. The file containing visualizations can be found [here](https://github.com/jat2211/Photoionization-Modeling/blob/main/CLOUDY_GRID_EXAMPLE.ipynb), of which I wrote all cells that create a visualization. These visualizations were created using MatPlotLib.
## Results
The current results of the project show that we can effectively write input data using the necessary constraints to model over 2000 variations of J1044+0353, and we were able to match the observed emission line ratios from several ionization stages to the photoionization models. I presented the results of my research at the University of Texas research symposium. I gave a pop-up talk followed by an hour-long Q&A session. My talk slides can be found [here](https://github.com/jat2211/Photoionization-Modeling/blob/main/Trevino.pptx) and my research poster found [here](https://github.com/jat2211/Photoionization-Modeling/blob/main/photo_modeling.pdf). I've continued communication with my mentors so that I may present my research at the 240th American Astronomical Society (AAS) conference in Pasadena, California, as well as to act as contributing co-author to a published paper.
## Revelant Skills Used
- Python
- Pandas
- NumPy
- MatPlotLib
- **Broader Domains: data science, astronomy, research**
## References
- Stanway 2016; Stanway et al. 2016) single-burst models.
- Eldridge, J. J., & Stanway, E. R. 2016, MNRAS, 462, 3302 
- Ferland, G. J., Porter, R. L., van Hoof, P. A. M., & others. 2013, RMxAA, 49, 137
- Berg, D. A., Erb, D. K., Auger, M. W., Pettini, M., & Brammer, G. B. 2018, ApJ, 859, 164
- Berg, D. A., Chisholm, J., Erb, D. K., et al. 2021, arXiv:2105.12765
