FROM itprojectsllc/odoo-runbot-docker

USER root

RUN true && \
    # configs for saas
    sed -i -e "s/; limit_time_cpu = 60/limit_time_cpu = 600/" /etc/odoo/openerp-server.conf && \
    sed -i -e "s/; limit_time_real = 120/limit_time_real = 1200/" /etc/odoo/openerp-server.conf

ENV BUILD_DATE_CUSTOM=2016_08_05

RUN apt-get install -y libffi-dev libssl-dev

RUN wget -q -O- https://raw.githubusercontent.com/it-projects-llc/misc-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/pos-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/mail-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/rental-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/access-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/website-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/l10n-addons/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/odoo-telegram/8.0/requirements.txt | xargs pip install && \
    wget -q -O- https://raw.githubusercontent.com/it-projects-llc/odoo-saas-tools/8.0/requirements.txt | xargs pip install

USER odoo

