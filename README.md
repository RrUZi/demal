# DeMal: Module Decomposition of Malware Based on Community Discovery
[![license](https://img.shields.io/badge/license-GPL-brightgreen.svg)](https://github.com/RrUZi/demal/blob/master/LICENSE)
[![version](https://img.shields.io/badge/version-0.0-blue.svg)](https://github.com/RrUZi/demal)

This is the official implementation of **DeMal**, the prototype described in: _[Yuyao Huang](https://github.com/RrUZi) <a href="https://orcid.org/0000-0002-1574-6644"><img src="https://orcid.org/sites/default/files/images/orcid_16x16.png" style="width:1em;margin-right:.5em;" alt="ORCID iD icon"></a>, [Hui Shu](mailto:shuhui123@126.com), and [Fei Kang](mailto:mathswork@163.com)_, "**DeMal: Module Decomposition of Malware Based on Community Discovery**״, will appear in <font color="Black">[Computers & Security](https://www.sciencedirect.com/journal/computers-and-security)</font>, 2022.

Our evaluation dataset and other resources are available [here](https://doi.org/10.5281/zenodo.5637511) (Zenodo). These will be used and further explained next.

📣 Now, enjoy dissecting malware with DeMal!

## Table of Contents

* [Requirements](#requirements)

* [Installation](#installation)
* [Usage](#usage)
* [Dataset](#dataset)
* [Citation](#citation)
* [Contact](#contact)

## Requirements

* [Python 3](https://www.python.org/downloads/)
* [IDA-Pro](https://www.hex-rays.com/products/ida/) (tested with version 7.5).
* A few more python packages described in [requirements.txt](requirements.txt).

## Installation

Run the following command line:

```
pip3 install -r requirements.txt
```

## Usage

### Quick start

Just type **Alt + F7** in IDA and double-click **DeMal.py**, then enjoy the decomposition result :)

_Sample A_

![Sample A](assets/1.gif)

_Sample B_

![Sample B](assets/2.gif)

### Batch mode

⏳ Coming soon.

## Dataset

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5637511.svg)](https://doi.org/10.5281/zenodo.5637511)

This dataset is divided into 3 separate .7z files, denoted **M1**, **B1**, and **M2**, where M1 and B1 contain all the input samples and mapping files, while M2 only gives the output result files and sample hashes for security reasons at present. Detailed descriptions can be found in our publications.

In our paper, we collect three datasets M1, B1, and M2 for experiments. We use M1 to train and evaluate DeMal on the ground truth, which consists of 155 different malwares. We set up another evaluation test on B1 with 1,621 benign programs to illustrate that DeMal can also be applied to general software analysis. We hope it is not limited to malware programs, but also for normal binaries. Finally, we perform a batch analysis on M2 with over 10,000 malicious executables to evaluate the large-scale performance of DeMal.

**M1**: First, in order to train DeMal, the ground truth must to be found for comparison with the predicted decomposition result. The sample with debug information is the only ground truth that reflect the real module structure. However, the new public released malware source code is difficult to obtain. To produce the dataset, we selected repositories from [[50](https://www.usenix.org/conference/raid2020/presentation/omar),[51](https://thezoo.morirt.com/),[52](https://vx-underground.org/),[53](https://github.com/0xjet/malsource)] that meet the following conditions: (i) compilable and non-scripted, (ii) reaching a minimum number of modules consisting of at least two source files, (iii) complete project structure with all necessary files for compiling, and (iv) undering the author's open source license. We wrote configurable compile chain scripts supporting the output of map files during linking. With the debug information contained in these map files, we established the true module boundaries. Finally, we got a total of 155 binaries with debug information as M1.

**B1**: To extend DeMal to general analysis of programs, we fetched normal repositories using the [Github API](https://docs.github.com/en/rest). After performing the same building process, we got dataset B1, with a total of 1,621 target benign programs.

**M2**: We also prepared the malware set M2, which consisted of stripped programs lacking symbolic information to reconstruct the module. M2 contains a large-scale malware sample of 13,251 programs, which were collected by [VirusShare](https://www.virusshare.com/) over a period of six months from November 2019 to April 2020.

## Citation

[DeMal: Module Decomposition of Malware Based on Community Discovery]()

```
@article{
    Huang2022,
    title = {DeMal: Module Decomposition of Malware Based on Community Discovery},
    author = {Yuyao Huang, Hui Shu, and Fei Kang},
    doi = {},
    journal = {Computers & Security},
    number = {},
    title = {{DeMal: Module Decomposition of Malware Based on Community Discovery}},
    volume = {},
    year = {2022}
}
```

## Contact
Contributors welcome! Feel free to issue pull-requests with any new features or improvements you have come up with!
And any questions will be answered promptly.

📧[Hwang](mailto:yyhuang_ieu@163.com)

