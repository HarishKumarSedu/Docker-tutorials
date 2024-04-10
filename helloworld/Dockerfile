## simple docker commands with the internal port 5000
FROM python:3.7
WORKDIR /app
COPY . /app
#upgrade the pip inside the image 
# RUN python.exe -m pip install --upgrade pip
RUN pip install -r requirements.txt 
ENTRYPOINT [ "python" ]
CMD [ "app/identidock.py" ]

####### we’ve overridden the default CMD instruction that calls the webserver with the
####### whoami command, which returns the name of the running user inside the container.

# FROM python:3.4
# RUN groupadd -r uwsgi && useradd -r -g uwsgi uwsgi

# RUN pip install flask uWSGI
# WORKDIR /app
# COPY app /app
# EXPOSE 9090 9191
# USER uwsgi
# CMD ["uwsgi", "--http", "127.0.0.1:9090", "--wsgi-file", "/app/identidock.py", \
# "--callable", "app", "--stats", "127.0.0.1:9191"]

### Executing through command prompt 
FROM python:3.4
RUN groupadd -r uwsgi && useradd -r -g uwsgi uwsgi
RUN pip install flask uWSGI
WORKDIR /app
COPY app /app
COPY cmd.sh /
EXPOSE 9090 9191
USER uwsgi
CMD ["/cmd.sh"]