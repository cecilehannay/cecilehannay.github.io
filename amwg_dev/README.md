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
- **control** version. It is easier to have collaborations and also we can have a gatekeeper and pull requests.
- more **freedom** than with web2mod (we don't have to stick to web2mod standards)
- take advantages of some **github tools** to interact. 

### What would we like to share when we do a simulation? 

For each simulation:  
- **casename** 
- **description**
- **diags**

We can also save:
- **case directory** (especially there is no backup anymore of /glade/p/cesmdata/cseg/runs/cesm2_0)
- **sandbox** (often we don't use cesm/cam tags with a sandbox with different Externals and/or modifications)
- **discussion** of about the simulation into github (instead of a flurry of emails)

### Using archive_metadata to save the case directory information

In this table, 
- I used the tool archive_metadata to collect the information about the **case directory**. This goes in the cesm database.
- The information about the **sandbox** is saved into github in a branch.
- The **diagnostics** are at the usual place on the cgd website.


| Run           | Description   | Sandbox |  Diags |
| ---------     | ------------- | --- | -------|
|[f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2.hf](https://svn-cesm2-expdb.cgd.ucar.edu/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2.hf)    | Control | [cam7_test_0.0.1](https://github.com/cecilehannay/CAM7-dev-simulations/releases/tag/cam7_test_0.0.1) |[diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2.hf/atm/)|
|[f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz0.8.hf](https://svn-cesm2-expdb.cgd.ucar.edu/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz0.8.hf)    | dmpdz = 1->0.8 | [cam7_test_0.02](https://github.com/cecilehannay/CAM7-dev-simulations/releases/tag/cam7_test_0.0.2) | [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz0.8.hf/atm/)|
|[f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz1.2.hf](https://svn-cesm2-expdb.cgd.ucar.edu/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz1.2.hf)    | dmpdz = 1->1.2 | [cam7_test_0.03](https://github.com/cecilehannay/CAM7-dev-simulations/releases/tag/cam7_test_0.0.3) | [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.001_zm2_dmpdz1.2.hf/atm/)|



### Saving case directory as a branch/tag 

This is similar to the previous table except instead of using archive_metadata, we saved the case directories on github in a branch. 


| Run           | Description   |  Diags |
| ---------     | ------------- | -------|
| [f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_zmke_4.hf](https://github.com/cecilehannay/amwg_cases/releases/tag/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_zmke_4.hf)   |    lparcel_dynamic = True and lparcel_pbl = True           |   [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_zmke_4.hf/atm/)     |   
| [f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_detmods_entr4.hf](https://github.com/cecilehannay/amwg_cases/releases/tag/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_detmods_entr4.hf)  |   w/ the detrainment mods + increased entrainment limiter 2E-4 -> 4E-4            |     [diags](https://webext.cgd.ucar.edu/FWscHIST/f.e21.FWscHIST.ne30_L48_BL10_cam6_3_019_plus_CESM2.2.002_zm2_detmods_entr4.hf/atm/)    |   



### Taking advantage of github issues

Instead of having tables, another possibility is to keep track of the simulations are a collection of issues. 

![Screen Shot 2021-11-18 at 11 26 06 AM](https://user-images.githubusercontent.com/9723220/142474809-d89b2e54-0fcd-4baf-a550-ccdf9dcee0ed.png)

Each simulation will correspond to a single **issue**. We will use a **template** to enter the simulations and specify: 
- casename 
- description
- diags

Advantages of issues instead of a table:
- all the developpers can comment on the issue. 
- tags
- searchable


[https://github.com/swrneale/amwg_dev/issues](https://github.com/swrneale/amwg_dev/issues)


# Where will this live ? 

### github.com/NCAR

![Screen Shot 2021-11-18 at 11 16 08 AM](https://user-images.githubusercontent.com/9723220/142473416-24d187e7-f2e2-4f69-84df-b38dedef149a.png)


### Github pages

**Examples**

The ESDS webpage is hosted on github page:
[https://ncar.github.io/esds/](https://ncar.github.io/esds/) 

What I showed here is indeed a github page:
[https://cecilehannay.github.io/amwg_dev/](https://cecilehannay.github.io/amwg_dev/) 

### Github Wiki

**Examples** 

CAM-debugging-techniques:[https://github.com/ESCOMP/CAM/wiki/CAM-debugging-techniques](https://github.com/ESCOMP/CAM/wiki/CAM-debugging-techniques)

ADF wiki: [https://github.com/NCAR/ADF/wiki](https://github.com/NCAR/ADF/wiki)

NB: no pull request on the github wiki. 


# Discussion: What do you think? 

This is how I feel about moving CAM development on github.
![Screen Shot 2021-11-18 at 11 44 49 AM](https://user-images.githubusercontent.com/9723220/142477714-8a15fb1f-2152-45d4-9b66-93108e36a7b5.png)


# THis is an example of webpage:

The is the L58 simulations:
https://github.com/swrneale/amwg_dev/issues?q=is%3Aissue+is%3Aopen+label%3AL58
