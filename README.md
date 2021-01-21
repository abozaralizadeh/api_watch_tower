![AWT](https://bitbucket.org/m4x4m/apiwatchtower/raw/54061db3311cdc43d7754b24e24cd41a67560601/static/logo.png)

# Api Watch Tower (Demo Version)

AWT is an open-source Django application for deep real-time API monitoring by periodical calls and evaluating the results, not only as a health checker but also for controlling the integrity and getting alerts in case of any unexpected changes to the result payload itself. aimed to use along with other tools like Grafana to Visualise the data and setting alert systems.

To see the demo without applying any configuration, you can use the single container here: [abo0zar/single_awt](https://hub.docker.com/repository/docker/abo0zar/single_awt)
This demo doesn't support all the features and might not be updated in future and should not be used in production environments. 
(To install the official version visit [abo0zar/api_watch_tower:latest](https://hub.docker.com/repository/docker/abo0zar/api_watch_tower))


This container is already active and has all the components (like Postgres, Grafana, configurations, etc) needed to run AWT.
After running the container access to the django admin on **http://localhost/admin** and grafana on **http://localhost/grafana**
and use the default username: admin - password: admin.

## Installation

Use the following configuration:

```yml
# docker-compose.yml

version: '3'

services:
  awt:
    image: abo0zar/single_awt:latest
    restart: always
    command: bash startup_awt
    ports:
      - "80:80"
    environment:
      - AAD_TENANT_ID=xxxOptionalxxx
      - AAD_CLIENT_ID=xxxOptionalxxx
      - HTTPS=off
    volumes:
      - grafanaStorage:/var/lib/grafana
      - postgresData:/var/lib/postgresql/12/main
      - grafanaConfig:/etc/grafana

volumes:
    postgresData:
    grafanaStorage:
    grafanaConfig:

```



## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT License](https://bitbucket.org/m4x4m/apiwatchtower/src/master/LICENSE) 

Copyright (c) 2021 Abozar Alizadeh, All rights reserved

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

![AWT](https://bitbucket.org/m4x4m/apiwatchtower/raw/54061db3311cdc43d7754b24e24cd41a67560601/static/logo.png)
