# python_actions_safety
A Github action for running security vulnerability checks on python dependencies with safety.


<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.


Examples:

```
on: [push]

jobs:
  safety:
    runs-on: ubuntu-latest
    name: "safety"
    steps:
      - uses: davidslusser/actions_python_safety@v1.0.0
```
<br/>

```
on: [push]

jobs:
  safety:
    runs-on: ubuntu-latest
    name: "safety"
    steps:
      - uses: davidslusser/actions_python_safety@v1.0.0
        with:
          options: "--debug"
          pip_install_command: "pip install -e .[dev]"
          python_version: "3.9"
```


<br/>

## Inputs
  - **options:** optional flags/parameters used in safety command
  - **pip_install_command:** pip install command (defaults to "`pip install safety`")
   - **python_version:** version of python to run workflow with (defaults to "`3.x`")


<br/>

## References
 - https://pyup.io/safety/
 - https://pypi.org/project/safety/
