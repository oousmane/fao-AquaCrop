# FAO-AquaCrop

<img src="https://github.com/user-attachments/assets/456e0b66-2647-4cb7-96b2-eebc91a77a75" alt="AquaCrop logo" width="160" align="right">
AquaCrop v7.3 is released as open-source Python code, by the Food and Agriculture Organization (FAO) of the United Nations.

The following applications are publicly distributed:

- AquaCrop version-controlled open **python source code** (this GitHub page, and zip-file under [Releases](https://github.com/un-fao/fao-AquaCrop/releases/tag/v7.3))
- AquaCrop standard Windows **graphical user interface** (zip-file under [Releases](https://github.com/un-fao/fao-AquaCrop/releases/tag/v7.3))
- AquaCrop **python standalone executable** (zip-file under [Releases](https://github.com/un-fao/fao-AquaCrop/releases/tag/v7.3)) for
  - Windows
  - Linux
  - macOS

## Documentation

Online documentation and contact information are available at the [FAO website](https://www.fao.org/aquacrop/en/).

## Running AquaCrop

Download the ZIP file with the AquaCrop standalone executable (v7.3) for Windows, Linux or macOS from the [Releases](https://github.com/un-fao/fao-AquaCrop/releases/tag/v7.3) page. Consult the reference manual ([FAO website](https://www.fao.org/aquacrop/en/)) for details about the AquaCrop standalone program.

To work with the Python source code instead, either download the ZIP file with the source code from the [Releases](https://github.com/un-fao/fao-AquaCrop/releases/tag/v7.3) page, or fork the repository and clone your fork locally if you wish to contribute.

## Building a standalone executable

The Python source can be frozen into a single-file executable with [PyInstaller](https://pyinstaller.org/), so that AquaCrop runs on machines without a Python installation. A build recipe is provided in `python_source_code/AquaCrop73_src/aquacrop.spec`.

```bash
pip install pyinstaller
cd python_source_code/AquaCrop73_src
pyinstaller --clean --noconfirm aquacrop.spec
```

The executable is written to `dist/aquacrop` (`dist\aquacrop.exe` on Windows). It is built per platform: run the command on the operating system you are targeting, since PyInstaller does not cross-compile.

At run time, AquaCrop resolves its data directories **next to the executable**, not against the current working directory, so the program can be launched from anywhere. Place the four data directories alongside it:

```
aquacrop            <- the executable
LIST/               <- ListProjects.txt and project files
PARAM/              <- crop, soil and climate parameter files
SIMUL/              <- simulation settings, MaunaLoa.CO2
OUTP/               <- created outputs are written here (must exist)
```

To run from the source tree instead, the same directories are read from `python_source_code/AquaCrop73_src/testcase/`:

```bash
cd python_source_code/AquaCrop73_src
python3 src/aquacrop.py
```

## Citation

A wide range of publications is available to refer to AquaCrop in the GUI or standalone version. The most recent report is "[AquaCrop on the ground. Model applications for sustainable agricultural water management](https://openknowledge.fao.org/items/5ac8b52d-dff2-413e-9068-e3f7163d88bf)".

The users can refer to this publication or any publication of their choice, when using these AquaCrop assets.

## AquaCrop team

**Original authors:**

- Theodore Hsiao (UC Davis)
- Pasquale Steduto (former FAO)
- Elias Fereres (IAS-CSIC & University of Cordoba)
- Dirk Raes (KU Leuven)

**Contributing authors:**

- Maher Salman (FAO)
- Margarita Garcia-Vila (IAS-CSIC, Spain)
- Lee Heng (former IAEA)
- Hanne Van Gaelen (KU Leuven, Belgium)
- Eline Vanuytrecht (KU Leuven, Belgium)

The development of the open source code version in Python (AquaCrop version 7.3), has been carried out under the FAO AquaCrop programme in collaboration with the University of Cordoba.
