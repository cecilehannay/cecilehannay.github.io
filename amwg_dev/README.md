# CAM6 development: "The old way"

During CAM6 development, we shared CAM development effort through webpages:

[https://www.cesm.ucar.edu/working_groups/Atmosphere/development/](https://www.cesm.ucar.edu/working_groups/Atmosphere/development/)

**Why not doing that for CAM7?** 
- it is difficult to have several people collaborating on the traditional html webpages. 
- UCAR is imposing new standards (web2mod)
- Moving from html to drupal 


--------------------------------------------------

# CAM7 development: "The 2021 way" 

We explored sharing development on github. 
- control version: it is easier to have collaborations (and also we can have a gatekeeper and pull request)
- more freedom than with web2mod
- take advantages of some github tools to interact. 

### What would we like to share when we do a simulation? 

For each simulation:  
- casename 
- description
- diags

We can also save:
- case directory (no backup anymore)
- sandbox
- discussion of about the simulation

### Using archive_metadata to save the case directory information

In this table, 
- I used the tool archive_metadata to collect the information about the **case directory**. This goes in the cesm database.
- The information about the **sandbox** is saved into github in a branch.
- The **diagnostics** are at the usual place on the cgd website.


| Run           | Description   | Tag |  Diags |
| ---------     | ------------- | --- | -------|
|[f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2.hf](https://svn-cesm2-expdb.cgd.ucar.edu/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2.hf)    | Control | [cam7_test_0.0.1](https://github.com/cecilehannay/CAM7-dev-simulations/releases/tag/cam7_test_0.0.1) |[diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2.hf/atm/)|
|[f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz0.8.hf](https://svn-cesm2-expdb.cgd.ucar.edu/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz0.8.hf)    | dmpdz = 1->0.8 | [cam7_test_0.02](https://github.com/cecilehannay/CAM7-dev-simulations/releases/tag/cam7_test_0.0.2) | [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz0.8.hf/atm/)|
|[f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz1.2.hf](https://svn-cesm2-expdb.cgd.ucar.edu/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz1.2.hf)    | dmpdz = 1->1.2 | [cam7_test_0.03](https://github.com/cecilehannay/CAM7-dev-simulations/releases/tag/cam7_test_0.0.3) | [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz1.2.hf/atm/)|



### Saving case directory as a branch/tag 

This is similar to the previous table except instead of using archive_metadata, we saved the case directories on github in a branch. 


| Run           | Description   |  Diags |
| ---------     | ------------- | -------|
| [f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_zmke_4.hf](https://github.com/cecilehannay/amwg_cases/releases/tag/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_zmke_4.hf)   |               |   [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_zmke_4.hf/atm/)     |   
| [f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_detmods_entr4.hf](https://github.com/cecilehannay/amwg_cases/releases/tag/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_detmods_entr4.hf)  |   w/ the detrainment mods + increased entrainment limiter 2E-4 -> 4E-4            |     [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_detmods_entr4.hf/atm/)    |   

--------------------------------------------------

### Taking advantage of github issues

Instead of having tables, another possibility is to keep track of the simulations are a collection of issues. 
[https://github.com/swrneale/amwg_dev/issues](https://github.com/swrneale/amwg_dev/issues)

Each simulation will correspond to a single issue. We will use a template to enter the simulations and specify: 
- casename 
- description
- diags

The advantage is that all the developpers can comment on the issue. 



