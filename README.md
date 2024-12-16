# MACE_Osaka24 models
This repository provides the model and training scripts for a multi-domain universal machine learning interatomic potentials (MLIPs), the MACE-Osaka24 models, capable of accurately describing both crystalline and molecular domains.

The MACE-Osaka24 model is a universal MLIP trained on datasets of both crystals and molecules, which were generated using a dataset integration technique called "Total Energy Alignment" that combines first-principles calculations under various conditions. 

Its architecture is based on the first-generation MACE model. To use the models please install the [MACE code](https://github.com/ACEsuit/mace).

## Models

The first generation of models are available in the [MACE_Osaka24](https://github.com/TShiotaSS/mace_osaka24/releases/tag/v0.0.1).

If you use the models please cite

```bib
@article{batatia2023foundation,
      title={A foundation model for atomistic materials chemistry},
      author={Ilyes Batatia and Philipp Benner and Yuan Chiang and Alin M. Elena and Dávid P. Kovács and Janosh Riebesell and Xavier R. Advincula and Mark Asta and William J. Baldwin and Noam Bernstein and Arghya Bhowmik and Samuel M. Blau and Vlad Cărare and James P. Darby and Sandip De and Flaviano Della Pia and Volker L. Deringer and Rokas Elijošius and Zakariya El-Machachi and Edvin Fako and Andrea C. Ferrari and Annalena Genreith-Schriever and Janine George and Rhys E. A. Goodall and Clare P. Grey and Shuang Han and Will Handley and Hendrik H. Heenen and Kersti Hermansson and Christian Holm and Jad Jaafar and Stephan Hofmann and Konstantin S. Jakob and Hyunwook Jung and Venkat Kapil and Aaron D. Kaplan and Nima Karimitari and Namu Kroupa and Jolla Kullgren and Matthew C. Kuner and Domantas Kuryla and Guoda Liepuoniute and Johannes T. Margraf and Ioan-Bogdan Magdău and Angelos Michaelides and J. Harry Moore and Aakash A. Naik and Samuel P. Niblett and Sam Walton Norwood and Niamh O'Neill and Christoph Ortner and Kristin A. Persson and Karsten Reuter and Andrew S. Rosen and Lars L. Schaaf and Christoph Schran and Eric Sivonxay and Tamás K. Stenczel and Viktor Svahn and Christopher Sutton and Cas van der Oord and Eszter Varga-Umbrich and Tejs Vegge and Martin Vondrák and Yangshuai Wang and William C. Witt and Fabian Zills and Gábor Csányi},
      year={2023},
      eprint={2401.00096},
      archivePrefix={arXiv},
      primaryClass={physics.chem-ph}
}

@article{deng2023chgnet,
      title={CHGNet: Pretrained universal neural network potential for charge-informed atomistic modeling},
      author={Bowen Deng and Peichen Zhong and KyuJung Jun and Janosh Riebesell and Kevin Han and Christopher J. Bartel and Gerbrand Ceder},
      year={2023},
      eprint={2302.14231},
      archivePrefix={arXiv},
      primaryClass={cond-mat.mtrl-sci}
}

@inproceedings{NEURIPS2022_4a36c3c5,
 author = {Batatia, Ilyes and Kovacs, David P and Simm, Gregor and Ortner, Christoph and Csanyi, Gabor},
 booktitle = {Advances in Neural Information Processing Systems},
 editor = {S. Koyejo and S. Mohamed and A. Agarwal and D. Belgrave and K. Cho and A. Oh},
 pages = {11423--11436},
 publisher = {Curran Associates, Inc.},
 title = {MACE: Higher Order Equivariant Message Passing Neural Networks for Fast and Accurate Force Fields},
 url = {https://proceedings.neurips.cc/paper_files/paper/2022/file/4a36c3c51af11ed9f34615b81edb5bbc-Paper-Conference.pdf},
 volume = {35},
 year = {2022}
}
```

## Training scripts

We provide training scripts for the models in this repository. The latest training command line is found in [`mace_osaka24/mace-osaka24-large.sh`](mace_osaka24/mace-osaka24-large.sh).

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
