## The Advanced Computing Center for Research and Education

**Project Overview**
The Advanced Computing Center for Research and Education (ACCRE) operates Vanderbilt University's high-performance computing cluster. Jobs submitted to ACCRE are managed by the [slurm scheduler](https://slurm.schedmd.com/documentation.html), which tracks compute and memory resources.

ACCRE staff have hypothesized that the scheduler sometimes becomes unresponsive because it is processing large bursts of job completions. This especially affects automated job submitters, such as members of the Open Science Grid.

Your goal is to evaluate whether the data supports the hypothesis of bursts of job completions contributing to scheduler unresponsiveness.

You are provided three datasets:  
* fullsample.csv: Contains slurm job records. Job completions correspond to jobs in the "COMPLETED" state with exit code "0:0".  
* slurm_wrapper_ce5.log, slurm_wrapper_ce6.log: These log files contain every slurm command executed by the CE5 and CE6 servers (gateways to the Open Science Grid).  
Unresponsive periods are indicated by "sbatch" commands from user 9204 that have:  
    * return code = 1
    * execution time > 15 seconds

**Phase 1: Explore the Data**  
Objectives:  
* Understand the purpose of each dataset.  
* Inspect column types, sizes, and example rows.  

Notebook Sections:  
* Code: Load each dataset, preview rows, summarize columns.  
* Markdown: Notes on data quality and initial observations.  

**Phase 2: Clean and Transform the Data**  
Objectives:  
* Extract job completions from fullsample.csv.  
* Parse CE5 and CE6 logs to identify unresponsive events.  
* Create analysis-ready features (time windows, completion counts, unresponsiveness indicators).  
* Optionally include other features (currently running jobs or resource usage, time-of-day).  

Notebook Sections:  
* Code: Filtering and transforming datasets.  
* Markdown: Document preprocessing steps and reasoning.  
* Code: Combine datasets into a single dataset suitable for analysis.

**Phase 3: Analyze and Visualize**  
Objectives:  
* Explore the relationship between job completions and unresponsiveness.  
* Create visualizations and basic summary statistics.  

Notebook Sections:  
* Code: Time-series plots, scatterplots, boxplots, summary statistics.
* Markdown: Interpret the visualizations and describe patterns.  
* Code: Fit a simple logistic regression to test the hypothesis.
* Markdown: Summarize the results and draw conclusions from the model.  
* Optional: Explore additional factors (eg. day of week).

**Phase 4: Interpret and Conclude**  
Objectives:  
* Answer the main question: Does the data support the hypothesis that the slurm scheduler is more likely to be unresponsive during bursts of job completions?  
* Summarize findings and limitations.  

Notebook Sections:    
* Markdown: Summarize evidence for or against the hypothesis.  
* Markdown: Provide a clear conclusion.  

**Final Deliverable:**
A single Jupyter notebook that includes:  
1. Introduction & dataset overview  
2. Data exploration & cleaning  
3. Feature engineering  
4. Analysis & visualizations  
5. Interpretation & conclusion

