Install virtual environment using venv
``` bash
pip install virtualenv
```

Create a virtual environment in folder:
```
python3.11 -m venv env
```

To activate and then, deactivate the virtual environment
```bash
source env/bin/activate
~ deactivate
```

To check list of packages installed in the virtual environment:
```bash
pip list
```

This will generate a text file listing project dependencies:
```
pip freeze > requirements.txt
```

```bash
 ~ pip install -r requirements.txt
```

