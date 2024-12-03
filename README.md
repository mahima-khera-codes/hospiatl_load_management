# Hospital Management System in Django


## Structures

- app.py
- constants.py
- **scripts**
    - `__init__.py`
    - script_a.py
    - script_b.py
- **data**
    - **csv**
        - a.csv
        - b.csv
        - c.csv
    - **pdf**
        - a.pdf
        - b.pdf
        - c.pdf
    - **html**
        - a.html
        - b.html
        - c.html
    - **logs**
        - script_a.log
        - script_b.log
- **helpers**
    - `__init__.py`
    - `s3.py`
    - `database.py`
    - `logger.py`
    - `api.py`
- **tests**
    - `__init__.py`
- **config**
    - `__init__.py`
    - `constants.py`
    - `sql.py`
    
## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites
1. python3 
2. pip3
3. virtualenvwrapper
4. mysql

Install `python3`
```bash
sudo apt-get install -y python3 
```

Install `pip3`
```bash
sudo apt-get install -y python3-pip
```

Install `virtualenvwrapper`
```bash
sudo pip3 install vitualenvwrapper
```

On your `.zshrc` or `.bashrc`
```bash
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/projects
source /usr/local/bin/virtualenvwrapper.sh
```

```bash
source ~/.bashrc
#or
source ~/.zshrc
```

### Installing

Create a virtualenv

```bash
export PROJECT_NAME='hospital_management_system'
mkvirtualenv $PROJECT_NAME
workon $PROJECT_NAME
```

```

Install the requirements

```bash
pip install -r requirements.txt
```


Install mysql
```bash
sudo apt-get install python3-dev libmysqlclient-dev
```

Change DB Config in `settings.py`
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': '<database-name>',
        'USER': '<database-user>',
        'PASSWORD': '<database-password>',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}

```

## Running the tests

```bash
python -m unittest discover -v
```


## Running the Application

```bash
python manage.py collectstatic --noinput
python manage.py makemigrations
python manage.py migrate
python manage.py runserver 0.0.0.0:8080