Up and running in a few minutes
-------------------------------

You have Docker installed already, right? Good.

```shell
docker run -d -p 3000:3000 \
  --name=grafana \
  -e 'GF_INSTALL_PLUGINS=grafana-simple-json-datasource' \
  grafana/grafana
pip install flask
python index.py
```

Now go to http://localhost:3000 and log into Grafana with admin:admin.

Next create a datasource in Grafana with type="SimpleJson" and URL="http://docker.for.mac.localhost:5000".

The above works with Docker for Mac, if you are using another OS then the hostname will need to be different in
order to access the locally running Flask server.

Now you can create a dashboard with a graph panel, use the simplejson datasource you created, and interact with
the Flask server you started.
