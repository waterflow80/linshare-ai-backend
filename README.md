# LinShare-AI-Backend
AI backend for LinShare.


## Setup the project
1. Install `python3.12` (Ubuntu 20.04). Ref: [wiki.crowncloud.net](https://wiki.crowncloud.net/?How_to_Install_Python_3_12_on_Ubuntu_20_04)
```shell
# Update System
apt update -y
apt upgrade -y
# Install Required Dependencies
apt install -y build-essential libssl-dev zlib1g-dev libbz2-dev \
    libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
    xz-utils tk-dev libffi-dev liblzma-dev python-openssl git
# Download Python Source Code
wget https://www.python.org/ftp/python/3.12.0/Python-3.12.0.tgz
tar -xf Python-3.12.0.tgz
cd Python-3.12.0
./configure --enable-optimizations
make -j 8 # Replace 8 with the number of CPU cores you want to allocate for the build process.
make altinstall
```
2. Install `poetry` dependency management tool (Linux):
```shell
curl -sSL https://install.python-poetry.org | python3 -
poetry --version
```
2. Set up the environment
```shell
# Set the virtual environment to be created 
# inside the project directory instead of the default global location.
poetry config virtualenvs.in-project true
# Install dependencies
poetry install

# To add a new package, run:
poetry add <package_name>
```
3. Run the service
```shell
poetry run linshare_ai_backend
# OR
. .venv/bin/activate
linshare_ai_backend
```

## Run tests
```shell
#Run all tests
pytest tests/
```
