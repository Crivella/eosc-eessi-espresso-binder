# Files to run ESPResSo on an EESSI-enabled Binder environment

## EOSC (European Open Science Cloud) Binder service

- Ensure you have an account that can login tied to resources: https://open-science-cloud.ec.europa.eu/dashboard
- Ensure notebooks are enabled in your account: https://open-science-cloud.ec.europa.eu/dashboard/notebooks
- Start the binder instance: https://binder.eu-2.notebooks.open-science-cloud.ec.europa.eu/v2/gh/Crivella/eosc-eessi-espresso-binder/HEAD

## Locally

Requires EESSI to be available on the system: https://www.eessi.io/docs/getting_access/native_installation/

- Install [jupyter-repo2docker](https://pypi.org/project/jupyter-repo2docker/):


  ```bash
  # Optionally create a virtual environment
  python3 -m venv venv
  source venv/bin/activate

  pip install jupyter-repo2docker
  ```

- Run repo2docker to build the docker image and run it:

  ```bash
  git clone https://github.com/Crivella/eosc-eessi-espresso-binder.git binder-repo
  cd binder-repo
  jupyter-repo2docker -v /cvmfs/software.eessi.io/:/cvmfs/software.eessi.io/  .
  ```

- Watch the output for the URL to access the notebook server, e.g. `http://127.0.0.1:<PORT>/?token=<TOKEN>`.
  Eventually replace `/tree?` with `/lab?` in the URL to access JupyterLab instead of the classic notebook interface.
- Open the URL in your browser
