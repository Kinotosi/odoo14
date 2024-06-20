FROM python:3.8.10-slim

RUN mkdir config
RUN mkdir odoo
RUN mkdir extra-addons

COPY requirements.txt .

RUN apt update -y
RUN apt upgrade -y
RUN apt install -y libjpeg62-turbo-dev default-libmysqlclient-dev
RUN apt install -y python-dev python3-dev libxml2-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev build-essential libssl-dev libffi-dev libjpeg-dev libpq-dev liblcms2-dev libblas-dev libatlas-base-dev
RUN apt install -y python3-tk
RUN apt install -y wkhtmltopdf
RUN apt install -y npm
RUN npm install -g less less-plugin-clean-css
RUN apt install -y node-less
RUN apt install -y postgresql

RUN python3 -m pip install --upgrade pip
RUN python3 -m pip install -r requirements.txt

EXPOSE 8069

CMD python3 /odoo/odoo-bin -c /config/odoo.conf