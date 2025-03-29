# inventory management software
A simple inventory management system built with Django.
Users can add stock item and generate bills. All data is stored in database and are rendered in real time

Use pyenv to create a virtual environment for python 3.11.11
## Fedora Linux
```
sudo dnf install -y git gcc zlib-devel bzip2 bzip2-devel readline-devel \
                    sqlite sqlite-devel openssl-devel libffi-devel \
                    xz-devel make
curl https://pyenv.run | bash
echo -e '\nexport PATH="$HOME/.pyenv/bin:$PATH"\neval "$(pyenv init --path)"\neval "$(pyenv virtualenv-init -)"' >> ~/.zshrc
source ~/.zshrc
pyenv install 3.11.11
pyenv virtualenv 3.11.11 myenv
pyenv activate myenv
pip install -r requirements.txt
```
To run project, run the following commands in the project's directory to create the database. When running the software for the first time, it is necessary to run each command for each app in the project
```
python manage.py makemigrations homepage
python manage.py migrate homepage
python manage.py makemigrations inventory
python manage.py migrate inventory
python manage.py makemigrations transactions
python manage.py migrate transactions
```
After the first time, the following can be run to migrate model changes in any app
```
python manage.py makemigrations
python manage.py migrate
```
Use the following command to run the server
```
python manage.py runserver
```
Use the following command to create an admin user 
```
python manage.py createsuperuser
```
