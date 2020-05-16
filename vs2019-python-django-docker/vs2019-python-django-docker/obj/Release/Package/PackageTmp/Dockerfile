FROM	python:3.8  
RUN		python -m pip install --upgrade pip 
#RUN		pip install Django==3.0.6
#COPY	. .
COPY	app /home/vs2019_python_django_docker/app
COPY	vs2019_python_django_docker /home/vs2019_python_django_docker/vs2019_python_django_docker
COPY	db.sqlite3 /home/vs2019_python_django_docker/db.sqlite3
COPY	manage.py /home/vs2019_python_django_docker//manage.py
COPY	Django-3.0.6 /tmp/Django-3.0.6 
RUN		/bin/sh -c python /tmp/Django-3.0.6/setup.py install #python /tmp/Django-3.0.6/setup.py install
#COPY    requirements.txt /tmp/
#RUN		pip install -r /tmp/requirements.txt --trusted-host mirrors.aliyun.com \                
		#--index-url https://mirrors.aliyun.com/pypi/simple/ \                
		#&& rm -rf ~/.cache/pip && rm /tmp/requirements.txt \                
		#&& cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime 
EXPOSE  8000
CMD     ["python","manage.py","runserver"]