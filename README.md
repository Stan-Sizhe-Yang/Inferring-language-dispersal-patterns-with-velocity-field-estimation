# Inferring-language-dispersal-patterns-with-velocity-field-estimation
**R package and tutorial of the language velocity field estimation (LVF) for reconstructing langauge dispersal pattern.**
## I. File description
**This repository contains three files:**

**1.  Supplementary_Materials: Datasets:**
  
&emsp;&emsp;The datasets of four language cases utilized in this study. The detailed information can be found in README within this file.  

**2.  Supplementary_Materials：R_codes_for_validations_and_comparisons_of_LVF:**
  
&emsp;&emsp;The R codes for model validations and comparisons conducted in this study. The detailed information can be found in README within this file.
    
&emsp;&emsp;Note that due to the memory limitation, the file "Supplementary_Materials：R_codes_for_validations_and_comparisons_of_LVF" is zipped into two .rar files: "R_codes_for_validations_and_comparisons_of_LVF.part1" and "R_codes_for_validations_and_comparisons_of_LVF.part2". These two .rar files need to be unzipped together to extract the complete files of Supplementary_Materials：R_codes_for_validations_and_comparisons_of_LVF.  

**3.  Supplementary_Materials:**
  
&emsp;&emsp;R_package_and_tutorial_of_LVF: The R package namely LVF and the tutorial for its implementaion. The detailed information can be found in README within this file.  

## II. Detailed tutorial for applying LVF

&emsp;&emsp;**Here, we will detailly explain each function and its parameters of "LVF" package based on the schematic overview (Figure 1) of the rationale and procedure of LVF.**

![433661_2_figure_8379516_s5by4z_convrt](https://github.com/Stan-Sizhe-Yang/Inferring-language-dispersal-patterns-with-velocity-field-estimation/assets/46415427/1191995a-bfaa-41a2-bc2a-41082104aace)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**Figure 1: Schematic overview of the LVF for inferring the dispersal trajectories and centres of languages.**

### 1. Applying LVF with one function "LVF.run.fun"
&emsp;&emsp;The LVF can be conducted using only one function: LVF.run.fun
```
LVF.res <- LVF.run.fun(data,
  
                       # The parameters below are for plotting the language velocity field.
                         
                       # They should better be chosen depending on the visual scale and geographic range of the figure.
                         
                       grid.smooth.map.sep2 = 2, grid.smooth.sigma = 1, grid.smooth.map.n = 10,
                         
                       PCA.velocity.length = 0.8, map.region = 'world',
                         
                       spatial.map.length = 0.1, spatial.map.cex = 0.3, spatial.map.arrow.cex = 0.03,
                         
                       grid.map.length = 1, grid.map.cex = 1, grid.map.arrow.cex = 0.05, grid.map.n.grid = 4)
```
&emsp;&emsp;The input dataset for parameter "data" should be a data.frame containing these columns:
  
&emsp;&emsp;![image](https://github.com/Stan-Sizhe-Yang/Inferring-language-dispersal-patterns-with-velocity-field-estimation/assets/46415427/281429ec-14b6-460f-862c-f55c0967f2f8)
  
&emsp;&emsp;The first column contains the labels of the language samples and the second colum contains the names of the language samples. These two columns should be at "character" format. The third and fourth columns contains the longitudes and latitudes of the language samples. They should be at the "numeric" format. The rest of the columns contains the values of the binary-coded lingusitic traits and they should be at "numeric" format.

### 2. Decomposing function "LVF.run.fun"


