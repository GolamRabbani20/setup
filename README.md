# Basic Setup
Setup for a Web-Project with Python, Serverless Postgres, Node for Tailwindcss

## Required Software
- [Python 3.10](https://www.python.org/downloads/) or newer
- [Node.js 18.15 LTS](https://nodejs.org/) or newer (For Tailwind.CSS)
- [Git](https://git-scm.com/)


## Getting Started

```bash
mkdir dev
cd dev
git clone https://github.com/golamrabbani20/start
cd start
```

To install packages and run various command shortcuts, we use [rav](https://github.com/jmitchel3/rav). Open `rav.yaml` to see the various commands available if you prefer to not use `rav`.

_Windows Users_
```powershell
c:\Python310\python.exe -m venv venv
.\venv\Scripts\activate
python -m pip install pip pip-tools rav --upgrade
rav run windows_installs
rav run win_freeze
```
# .env file
1. Create a .env file in your src directory
2. Go to neon create db and add the db connection string(DATABASE_URL) to the .env file 
3. For django_secret key: from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())

In rav.yaml, you'll see that rav run installs maps to:
1. venv/bin/pip-compile src/requirements/requirements.in -o src/requirements.txt
2. venv/bin/python -m pip install -r src/requirements.txt
3. npm install

# With all the configuration done, here are the main commands you'll run:

rav run server
rav run watch
rav run vendor_pull

rav run server maps to python manage.py runserver in the src folder
rav run watch triggers tailwind to watch the tailwind input file to make the compiled tailwind output file via npx tailwindcss -i <input-path> -o <output-path> --watch
rav run vendor_pull run this occasionally to pull the latest version of Flowbite, HTMX, and any other third party static vendor files you need.

_macOS/Linux Users_
```bash
python3 -m venv venv
source venv/bin/activate
venv/bin/python -m pip install pip pip-tools rav --upgrade
venv/bin/rav run installs
rav run freeze
```


