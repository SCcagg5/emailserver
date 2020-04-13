# emailserver

#### using poste.io webserver to create a web service in minutes:

to deploy a mail: *contact@<your_domain.com>*


**In your DNS record set:**
```peprl
mail.<your_domain.com>  A      <server_ip>
<your_domain.com>       MX     mail.<your_domain.com>
imap.<your_domain.com>  CNAME  mail.<your_domain.com>
pop.<your_domain.com>   CNAME  mail.<your_domain.com>
smtp.<your_domain.com>  CNAME  mail.<your_domain.com>
```

**On your server:**
```perl
git clone https://github.com/SCcagg5/emailserver/;
cd emailserver
docker-compose up -d
```

It's done you can now acces trought mail.<your_domain.com> webUI !

common issue:
you can't launch de docker, check that all your port are free to use common mistake on debian is to forget top `service exim4 stop`
check your port usage using `lsof -i:<your_port>`
