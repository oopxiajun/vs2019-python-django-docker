FROM	python:3.8.3-slim #这儿我们只需要 python3.8的一个精简版就能可以了，减少容器开销和镜像大小  
RUN		python -m pip install --upgrade pip 
#RUN		pip install Django==3.0.6
#COPY	. .
COPY	app /home/vs2019_python_django_docker/app
#COPY	static /home/vs2019_python_django_docker/static
COPY	run.sh /home/vs2019_python_django_docker/run.sh
COPY	vs2019_python_django_docker /home/vs2019_python_django_docker/vs2019_python_django_docker
COPY	db.sqlite3 /home/vs2019_python_django_docker/db.sqlite3
COPY	manage.py /home/vs2019_python_django_docker/manage.py
#COPY	Django-3.0.6 /tmp/Django-3.0.6 
ADD		Django-3.0.6.tar.gz /usr/local/src
WORKDIR /usr/local/src/Django-3.0.6
RUN     python setup.py install
WORKDIR /home/vs2019_python_django_docker
#ENV		PATH /usr/bin/python:$PATH
#EXPOSE  8888
CMD		["/bin/bash", "run.sh"]
#RUN		cd /tmp/Django-3.0.6 \
		#&& python setup.py install
#CMD		["/bin/sh","-c","python","/tmp/Django-3.0.6/setup.py","install"] #python /tmp/Django-3.0.6/setup.py install
#COPY    requirements.txt /tmp/
#RUN		pip install -r /tmp/requirements.txt --trusted-host mirrors.aliyun.com \                
		#--index-url https://mirrors.aliyun.com/pypi/simple/ \                
		#&& rm -rf ~/.cache/pip && rm /tmp/requirements.txt \                
		#&& cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime 
#EXPOSE  9999
#CMD     ["/bin/sh","-c","python","/home/vs2019_python_django_docker/manage.py","runserver","0.0.0.0:9999"]
#CMD     ["/bin/sh","-c","while","true;do","sleep","1;done;"]
#RUN		cd /home/vs2019_python_django_docker \
	    #&& python manage.py runserver 0.0.0.0:9999