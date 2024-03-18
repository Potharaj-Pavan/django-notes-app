# Simple Notes App
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/LondheShubham153/django-notes-app.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`
![image](https://github.com/Potharaj-Pavan/django-notes-app/assets/128611993/6cea02f8-c897-4a25-aaf8-7e921a88380e)

![image](https://github.com/Potharaj-Pavan/django-notes-app/assets/128611993/9a5f970a-bda5-4d99-9c7d-bd2a64c4191e)
