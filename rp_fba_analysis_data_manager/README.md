# rpFbaAnalysis -- Run OptGene, OptKnock with an heterologous pathway

The open-source software package rpFbaAnalysis is available here : https://github.com/brsynth/rptools/tree/master/rptools/rpFbaAnalysis

## How to run rpFbaAnalysis wrapper tests

In order to execute tests on rpFbaAnalysis wrapper, you need to:

  - Connect to your galaxy instance in interactive mode:

  ```bash
    docker exec -it -u root galaxy_galaxy_1 bash
  ```
  - Copy all the contents of `test-data` folder into your own test-data directory which is located in your local galaxy instance : `/galaxy/test-data`. It contains all the input files and expected output files needed for the tests.

  - Install Planemo:
  You can see here the documentation for Planemo Installation : https://planemo.readthedocs.io/en/latest/installation.html
  Note that they recommand to install Planemo by setting up a virtual environment:

  ```bash
  python3 -m venv planemo
  . planemo/bin/activate
  pip install -U planemo
  ```

  Upgrade pip if needed.

  - run the tests:

  ```bash
  planemo test --conda_channels conda-forge --conda_debug tools/BRSynthTools/rpFbaAnalysis/wrap.xml
  ```

  IMPORTANT: Maybe you will need to remove CONDA from your PATH for the command `planemo test` to run correctly. To do that, you can edit this file `~/.bashrc`, comment this line `PATH="/root/anaconda3/bin:$PATH"` and save changes.

  Planemo will output an html test summary `tool_test_output.html`.
