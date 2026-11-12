# ASL-global-and-regional-analysis
From raw 2D ASL to perfusion scores for global WM/GM and 69 other regions

This code was completed on a Windows machine using Ubuntu 22.04.5 LTS (GNU/Linux 6.6.87.2-microsoft-standard-WSL2 x86_64) and is intended to be run through FSL. Code for Mac is unclear but using the none-script version line-by-line and making small adjustments should work.

What this code does: takes the raw 2D ASL and raw fieldmaps and creates GM, WM and whole-brain perfusion scores as well as a list of 69 other regions, their mean perfusion scores, amount of voxel coverage, standard deviation, median, IQR and the precision-weighted means through BASIL's oxford_asl (reference below). All is done in accordance with the ASL white paper (reference below). Preprocessing steps include T1 and standard space registration, motion and distortion correction and calibration. Outputs include GM, WM and whole-brain perfusion scores in standard, structural(T1) and native space & 69 regional scores in native space only. 

PLEASE NOTE: This code does not use partial volume corrcetion based on the amount of other corrections and lower resolution data.

PLEASE CHECK - This code assumes: NIFTI files, a pre-selected M0 image with TR of 10 (if an M0 image is unattainable please follow the No_M0 version), fsl_anat completed, "EffectiveEchoSpacing"(ms)=0.39999, "PhaseEncodingDirection"=-y, 3T field strength, single PLD with 1.8 bolus, slice timing of 0.045 (45 in asl_gui) and the presence of fieldmaps. Of course if any data differs, these values can be easily replaced.


BASIL reference: Woolrich, M. W., Jbabdi, S., Patenaude, B., Chappell, M., Makni, S., Behrens, T., Beckmann, C., Jenkinson, M., & Smith, S. M. (2008). Bayesian analysis of neuroimaging data in FSL. NeuroImage, 45(1), S173–S186. https://doi.org/10.1016/j.neuroimage.2008.10.055



White paper reference: Alsop, D. C., Detre, J. A., Golay, X., Günther, M., Hendrikse, J., Hernandez‐Garcia, L., Lu, H., MacIntosh, B. J., Parkes, L. M., Smits, M., Van Osch, M. J. P., Wang, D. J. J., Wong, E. C., & Zaharchuk, G. (2014). Recommended implementation of arterial spin‐labeled perfusion MRI for clinical applications: A consensus of the ISMRM perfusion study group and the European consortium for ASL in dementia. Magnetic Resonance in Medicine, 73(1), 102–116. https://doi.org/10.1002/mrm.25197
