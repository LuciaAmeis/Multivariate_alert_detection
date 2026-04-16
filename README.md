#######################################################
Source Code and data for the manuscript
"Estimating effect thresholds and beyond:                   
A flexible framework for multivariate alert detection" ,
by L. Ameis, N. Hagemann and K. Moellenhoff.
arXiv:2604.13264
#######################################################

For questions, comments or details please contact L. Ameis at the Univeristy of Cologne: 
lucia.ameis@uni-koeln.de

The code is grouped into multiple .R files. All can be run via the master_TDR.R file or individually, 
after running the library in the master_TDR.R file. Please always start with setting the working directory 
to the folder containing the master_TDR.R file, e.g. by altering line 82 in the master.R file.
A complete description of the contents of the individual .R files can be found in the master_TDR.R file.

Most of the code was run on R version 4.5.0. The simulation runs were conducted on a HPC-cluster employing R
version 4.4.1. For details on the session info see the master_TDR.R from line 202.

To handle large white edges when creating 2D plots from 3D plotly files, plots are temporarily saved
as a pdf in the folder plots_tables/tmp_plots before loading into the working directory as a ggplot
object. If the pdf files are automatically deleted. This can be stopped by setting
clean_tmp_file <- F
in line 95 of the master file.
In general, tables and plots are automatically stored in the folder 'plots_tables'.

The data presented in the case study are openly available in Archives of Toxicology at 
10.1007/s00204-018-2302-0 or included in the R package td2pLL. 

Here, only the code to reproduce the results shown in the manuscript is provided. 
However, running the simulation study is very time consuming. We recommend running it externally on a
server. On our server, it was not possible to install the package td2pLL which is necessary for simulation 
Scenario 1. A workaround is described in detail in the file Simulation/scenario1_run_simulation_TDR from line
23. 

To save the plotly generated 3D plots, a Python (313) installation is necessary. Please adjust 
line 14 in the file ./plot_generation/plot_generation_function_TDR.R to the save Location on 
your computer. Note the versions of the imported Python packages "kaleido" (0.1.0.post1) and  "plotly"
(5.3.1).

REGARDING PARALLELIZATION:
Parallelization on Windows was utilized generating the results. The following packages were used:
parallel,foreach,doParallel,doSNOW
Users may want to adapt to their own setup (e.g. FORK instead of PSOCK). The cluster is generted in lines 71-75 in the master_TDR.R file. Precisely, find  type="PSOCK" in line 74. The cluster is registered in line 257 in base_TDR.R and in line 201 in base_TDR_cytotox.R, and stopped in lines 316 and 280, respectively.
 
