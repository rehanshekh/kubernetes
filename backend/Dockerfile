FROM python:3.6
RUN apt-get update
RUN apt-get install --yes python3-pip
RUN useradd -ms /bin/bash ubuntu
USER ubuntu:ubuntu
WORKDIR /new_chatapp/
COPY /new_chatapp/requirements.txt /new_chatapp/
RUN pip3 install -r requirements.txt
RUN pip3 install mysqlclient
EXPOSE 8000
WORKDIR /new_chatapp/fundoo/
COPY /new_chatapp/fundoo/ /new_chatapp/fundoo/
CMD python manage.py migrate
ENTRYPOINT  python3 manage.py runserver 0.0.0.0:8000
