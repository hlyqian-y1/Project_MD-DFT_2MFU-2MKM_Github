# 1 Oct 2025 Updated.
## The supporting materials for this project are as follows:
- MetaDynamics MD simulations (GromacsMD + Plumed)
- Quantum chemistry DFT calculations (ORCA 5.0)
- DFT spectral conversion （Matplotlib, python）

## Coordinator
- Dr. Mateus Webba da Silva. mm.webba-da-silva@ulster.ac.uk
- Yuncheng Qian. Qian-Y1@ulster.ac.uk
  
## Prerequisition
```text
── Python, matplotlib and related packages.
── ORCA 5.0.4
── Gromacs MD 2022.5 or 2023.2 or higher, compiled with Plumed 2.7 or higher.
```

## The Hierarchy of Project Folders
## 1. `Project_2MFU+2MKM_DFT-ORCA/` —— Quantum Chemistry DFT Ground State and Excited State calculation with ORCA 5.0.4 
```text
Project_2MFU+2MKM_DFT-ORCA/
├──Inputs_ORCA/              # Input files for ORCA, in format of .inp file (plain .txt): 
    ├── 2mfu_8G_3K/                 # QM forcefield, algorithm, structural coordinates, and hydrogen bond constraint distances included.
    ├── 2mfu_11G_3K/                # 
    └── 2mkm_6G_triplex/            # 
    └── .../                        # More systems unspecified
```

## 2. `Project_2MFU+2MKM_DFTspectrum/` —— DFT spectral conversion pipeline, scripts and figures, with Python / Matplotlib
```text
Project_2MFU+2MKM_DFTspectrum/
├── Jupyter-Arranged/              # IDE / Jupyter Notebook (.ipynb) Working Files.
├── Raw-DFT/                       # Raw DFT of excited states after ORCA TDDFT calculation 
├── pdb_structure_DFT_system/      # Structures (.pdb) of final TDDFT system 
├── xyz_structure_DFT_system/      # Coordinates (.xyz) of final TDDFT system 
├── Figures/                       # Intermidiate figures and spectra among raw DFT → spectral conversion
    ├── DFT_Species/                       # Finalized DFT spectrum testing
    ├── Dynamic_Width/                     # Dynamics Gaussian width testing
    ├── Fixed_Gaussian/                    # Variety of Fixed Gaussian width
    ├── Fixed_Lorentzian/                  # Variety of Fixed Lorentzian width
    ├── Fixed_Voigt/                       # Variety of Fixed Voigt width
    ├── Output_Spectrum_csv/               # Rescaled spectrum (.csv) fitting experimental range of wavelength 
    ├── Raw_TDDFT/                         # Raw DFT data with 2 CD types (Electronic Dipole & Velocity Dipole) and 2 Absorption types (Electronic & Velocity)
    └── Shifted_Scaled/                    # Figure views how broadening, shirting, rescaling effect.
├── Delta_Eps/                     # Intermidate Gaussian / Lorentzian / Voigt spectrum among spectral conversion for fine-tuning
└── Case_2MFU+2MKM_DFTspectrum/    # One case on 2MFU and 2MKM DFT spectrum. Assembled for publication
    ├── csv_DFT/                   # Raw DFT Electronic Dipole CD (eCD) after ORCA TDDFT calculation 
    ├── Figures/                   # One figure case on DFT spectrum.
    └── Case_2MFU+2MKM_DFTspectrum.ipynb  # IDE / Jupyter Notebook working file case.
```

## 3. `Project_2MFU+2MKM_MetaD-MD/` —— MetaDynamics / Standard MD simulation, with GromacsMD and Plumed
```text
Project_2MFU+2MKM_DFTspectrum/
├── Inputs_GromacsMD/              # Input files for GromacsMD and Plumed, in format of .gro, .mdp, .top, .tpr, .ndx, .dat (plain .txt): 
    ├── 2MFU_MetaDynamics/                  # MetaD for 2MFU in variety of bias and CV
        ├── 2mfu_bf35                       # 2MFU bias 35 with global CV biased.
            ├── Index_gromacs/              # Atom index (.ndx) in Gromacs
            ├── Input_gromacs/              # Inputs files in Gromacs: MD parameter (.mdp), combined input (.tpr), topology (.top), structure (pdb)
            └── Input_plumed/               # Plumed input files and foleder for 3 paraller replicas, in format of .dat
                ├── rep0_nobias             
                ├── rep1_pistacking
                └── rep2_Hoogsteen
        ├── 2mfu_bf40
        ├── 2mfu_bf45
        ├── 2mfu_bf55
        ├── 2mfu_BiasG3-G4_bf45             # (5'-end bias species) 2MFU bias 45 with minimal CV biased on 1st G-strand G3-G4
        ├── 2mfu_BiasG19-G20_bf45           # (3'-end bias species) 2MFU bias 45 with minimal CV biased on 4th G-strand G19-G20
            └── .../
    ├── 2MKM_standardMD/                    # Standard MD for 2MKM in variety of 80 mM, 150 mM, 250 mM salt concentration.
        ├──2mkm_80mMK/
            └── .../
        ├──2mkm_150mMK/
            └── .../
        └──2mkm_250mMK/
            └── .../
    └── 2MFU_standardMD/                    # Standard MD for triplex basin, test only
        └── .../
```

