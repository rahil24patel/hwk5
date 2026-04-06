# Homework 5

This is my Homework #5 submission, by Rahil Patel. I have built all necessary
datasets in hwk5_dataset, and answered all questions in hwk5_analysis. Here is
a brief summary of hwk5_dataset:

- Pulled the cleaned HCRIS panel from hwk4 and extracted state identifiers
  from the first two digits of each hospital's provider number using Medicare
  state codes. Non-50-state rows were dropped.
  
- Extracted uncompensated care from Worksheet S-10 of the raw HCRIS v2010
  files (worksheet S100000, line 3000, column 00100). I used a similar duplication logic in hwk4,
  by preferring final over last over new submissions.
  
- Downloaded Medicaid expansion dates by state from the Kaiser Family
  Foundation, cleaned the CSV, and merged onto HCRIS using a state crosswalk
  mapping postal abbreviations to full state names.

  
- Constructed key variables: uncomp_care_m, expand_ever, treat, post,
  time_to_treat (set to 0 for never-expanders), and time_to_treat_bin
  (clipped at -3 and +5).

  
- Built three analytical samples: a full 50-state panel from 2011-2018, a
  restricted sample of 2014 expanders and never-expanders only, and a 2x2
  subset using only 2012 and 2015.

I have two output files for use in the analysis notebook: hcris_kff_full.csv and hcris_kff_2014.csv.