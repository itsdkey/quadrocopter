# quadrocopter
zadanie rekrutacyjne quadrocopter

### Local development and project conventions
In this project we have some conventions which are installed via pre-commit.
To use them you need to create a python virtual environment:
```shell
python3.12 -m venv env/
```

Activate the env and set PYTHONPATH:
```shell
source <path_to_env>/bin/activate
```

Install the pre-commit package and necessary hooks:
```shell
pre-commit install
```

Thanks to pre-commit each commit will be checked if it's in accordance with
project's conventions.
More info here: https://pre-commit.com/


### Start the app project using docker compose
This project contains the following containers:
- training - the container which contains an environment that is used by the project

To enter the container use the following command:
```shell
docker compose run --rm training bash
```
This will run an interactive shell inside the provided container. Next you can either run
tests using:
```shell
python -m unittest
```
or execute the main.py module to provide some other inputs and check if the code works:
```shell
python main.py
```

## Debug
You can turn on debug prints if you want to investigate how the code works. To do that
simply add `debug=True` to the intialization of the `Quadrocopter` class in `main.py`:
```python
...
result = Quadrocopter(antennas, start, end, debug=True).calculate()
...
```

## Example how it works
```shell
app@e27f6ef45e73:~$ python main.py 
6
6 11 4
8 17 3
19 19 2
19 11 4
15 7 6
12 19 4
10 19
19 14
bezpieczny przelot jest możliwy
```
