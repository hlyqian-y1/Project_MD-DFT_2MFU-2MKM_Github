The supporting materials for this project are as follows:

- MetaDynamics MD simulations (GromacsMD + Plumed)
- Quantum chemistry DFT calculations (ORCA 5.0)
- DFT spectral conversion （Matplotlib）

## The Hierarchy of Project Folders

## 1. `Project_2MFU+2MKM_DFT-ORCA/` —— Quantum Chemistry DFT Ground State and Excited State calculation with ORCA 5.0.4 

```text
Project_2MFU+2MKM_DFT-ORCA/
├──Inputs_ORCA/              # Input files for ORCA, in format of .inp file (plain .txt): 
    ├── 2mfu_8G_3K/                 # QM forcefield, algorithm, structural coordinates, and hydrogen bond constraint distances included.
    ├── 2mfu_11G_3K/                # 
    └── 2mkm_6G_triplex/            # 
    └── .../                        # More systems unspecified
 
## 2. `Project_2MFU+2MKM_DFTspectrum/` —— DFT spectral conversion pipeline, scripts and figures.

```text
Project_DFTSpectrum/
├── Jupyter-Arranged/              # IDE / Jupyter Notebook .ipynb 工作文件
├── Raw-DFT/                       # 原始 DFT 输入文件
├── pdb_structure_DFT_system/      # TDDFT 系统的最终结构 (.pdb)
├── xyz_structure_DFT_system/      # TDDFT 系统的最终结构 (.xyz)
├── Figures/                       # 原始 DFT → 光谱形变过程生成的图像
├── Delta_Eps/                     # 形变过程中生成的 Gaussian / Lorentzian / Voigt 光谱
└── 18Jun2025_2FMU_2M6V_2MKM_DFT -spectrum/    # 整合数据并用于学术级制图（出版用）
    ├── csv_DFT/                   # 光谱转换后的 DFT 数据（出版用）
    ├── Figures/                   # 光谱转换后的制图（出版用）
    └── 18Jun2025_2FMU_2M6V_2MKM_DFT -spectrum.ipynb  # 出版用工作笔记本
