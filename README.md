# MACE-Osaka24 models
This repository provides the model and training scripts for a multi-domain universal machine learning interatomic potentials (MLIPs), the MACE-Osaka24 models, capable of accurately describing both crystalline and molecular domains.

The MACE-Osaka24 model is a universal MLIP trained on datasets of both crystals and molecules, which were generated using a dataset integration technique called "Total Energy Alignment" that combines first-principles calculations under various conditions. 

Its architecture is based on the first-generation MACE model. To use the models please install the [MACE code](https://github.com/ACEsuit/mace).

## Models

The first generation of models are available in the [MACE-Osaka24](https://github.com/qiqb-osaka/mace-osaka24/releases/tag/v0.0.1).

If you use the models, in addition to citing the original MACE papers, please cite:

```bib
@misc{shiota2024taming,
    title={Taming Multi-Domain, -Fidelity Data: Towards Foundation Models for Atomistic Scale Simulations},
    author={Tomoya Shiota and Kenji Ishihara and Tuan Minh Do and Toshio Mori and Wataru Mizukami},
    year={2024},
    eprint={2412.13088},
    archivePrefix={arXiv},
    primaryClass={physics.chem-ph}
}
```

## Training scripts

We provide training scripts for the models in this repository. The latest training command line is found in [`mace-osaka24/mace-osaka24-large.sh`](mace_osaka24/mace-osaka24-large.sh).

## Training data

The integrated inorganic–organic domain dataset used to train the models—composed of the inorganic MPtrj dataset and the organic SPICE, QMug, water clusters, and Tripeptides (OFF23) datasets—is available at [figshare](). If you use any of these datasets, please cite the following paper.

```bib
@article{deng2023chgnet,
      title={CHGNet: Pretrained universal neural network potential for charge-informed atomistic modeling},
      author={Bowen Deng and Peichen Zhong and KyuJung Jun and Janosh Riebesell and Kevin Han and Christopher J. Bartel and Gerbrand Ceder},
      year={2023},
      eprint={2302.14231},
      archivePrefix={arXiv},
      primaryClass={cond-mat.mtrl-sci}
}

@misc{kovacs2023maceoff23,
      title={MACE-OFF23: Transferable Machine Learning Force Fields for Organic Molecules}, 
      author={Dávid Péter Kovács and J. Harry Moore and Nicholas J. Browning and Ilyes Batatia and Joshua T. Horton and Venkat Kapil and William C. Witt and Ioan-Bogdan Magdău and Daniel J. Cole and Gábor Csányi},
      year={2023},
      eprint={2312.15211},
      archivePrefix={arXiv},
}

@article{eastman2023spice,
  title={Spice, a dataset of drug-like molecules and peptides for training machine learning potentials},
  author={Eastman, Peter and Behara, Pavan Kumar and Dotson, David L and Galvelis, Raimondas and Herr, John E and Horton, Josh T and Mao, Yuezhi and Chodera, John D and Pritchard, Benjamin P and Wang, Yuanqing and others},
  journal={Scientific Data},
  volume={10},
  number={1},
  pages={11},
  year={2023},
  publisher={Nature Publishing Group UK London}
}

@article{donchev2021quantum,
  title={Quantum chemical benchmark databases of gold-standard dimer interaction energies},
  author={Donchev, Alexander G and Taube, Andrew G and Decolvenaere, Elizabeth and Hargus, Cory and McGibbon, Robert T and Law, Ka-Hei and Gregersen, Brent A and Li, Je-Luen and Palmo, Kim and Siva, Karthik and others},
  journal={Scientific data},
  volume={8},
  number={1},
  pages={55},
  year={2021},
  publisher={Nature Publishing Group UK London}
}

@article{isert2022qmugs,
  title={QMugs, quantum mechanical properties of drug-like molecules},
  author={Isert, Clemens and Atz, Kenneth and Jim{\'e}nez-Luna, Jos{\'e} and Schneider, Gisbert},
  journal={Scientific Data},
  volume={9},
  number={1},
  pages={273},
  year={2022},
  publisher={Nature Publishing Group UK London}
}

@misc{shiota2024taming,
    title={Taming Multi-Domain, -Fidelity Data: Towards Foundation Models for Atomistic Scale Simulations},
    author={Tomoya Shiota and Kenji Ishihara and Tuan Minh Do and Toshio Mori and Wataru Mizukami},
    year={2024},
    eprint={2412.13088},
    archivePrefix={arXiv},
    primaryClass={physics.chem-ph}
}
```

## Example

In this example, the energy of a silicon crystal and acetic acid is calculated using universal multi-domain MLIP MACE-Osaka24 and Atomic Simulation Environment (ASE).

```python
from ase.build import bulk
from ase.build import molecule
from mace.calculators import MACECalculator

si = bulk('Si', 'diamond', a=5.43)
calculator = MACECalculator(model_path='/path-to-mace-osaka24/mace-osaka24-large.model', device='cpu')
si.calc = calculator 

energy_si = si.get_potential_energy()
print("Single-point energy of diamond Si:", energy_si)

acid = molecule('CH3COOH')
calculator = MACECalculator(model_path='/path-to-mace-osaka24/mace-osaka24-large.model', device='cpu')
acid.calc = calculator 

energy_acid = acid.get_potential_energy()
print("Single-point energy of acetic acid:", energy_acid)
```

## Contributors
This project was developed by:

- Tomoya Shiota (@TShiotaSS) 
- Kenji Ishihara (@kenji-ishihara-os)  
- Toshio Mori (@forest1040)
- Wataru Mizukami (@wmizukami)
