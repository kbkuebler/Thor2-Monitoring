## Use this for Thor2 installations
![Screenshot_20240701_174214](https://github.com/kbkuebler/Monitoring/assets/19337069/cdcb044c-e444-4975-b116-44019b5a155c)

## Hammerspace Monitoring Stack

This should help as a Promhetheus/Grafana quick start for SEs and others that just want to test things out in a non-production environment.
In order to get started, clone this repo and change the values of `prometheus/prometheus.yaml` to what's appropriate for your Hammerspace cluster.

Take a look at `example_scrape_config.yml` for an example where there is HA Anvil configuration and more than one DSX node.



### Note: Replace the IP addresses with your actual IP addresses
 - You can search and replace a.a.a.a with your Cluster IP
 - You can search and replace n.n.n.n with your Anvil IP
 - You can search and replace x.x.x.x with your DSX IP

### Another Note:

You will most likely want to change the default password that Grafana starts with. You can modify the .env file in the root directory with your own information.

The default configuration is:

```shell
GF_SECURITY_ADMIN_USER="admin"
GF_SECURITY_ADMIN_PASSWORD="admin!"
PROMETHEUS_UID="DS_PROMETHEUS"
```

Once that is done, you can run `docker compose up` and monitor the output. If everything has come up and is working as desired, you can `ctrl-c` and then restart with `docker compose up -d` and you should be able to demo and POC.

Note: *It's recommended that you're on the latest version of Hammerspace (Version 5.1.14 or greater).For older versions, please see the Hammerspace documentation.*

1. Edit `prometheus/prometheus.yaml` with the correct ip/hostnames for your environment. There is a sample config for your reference. 

2. SSH into your anvil and enable the Prometheus exporters:
`cluster-update --prometheus-exporters-enable`

3. Once that has been done, go to folder that has the `docker-compose.yaml` file and run `docker compose up` and monitor the output. If everything has come up and is working as desired, you can `ctrl-c` and then restart with `docker compose up -d` and you should be able to demo and POC.

4. You can now go to `yourdockerhost:3000` and you should see the Grafana logo. The default login and password is `admin:admin1`. 

5. Click on 'Dashboards' to see your Hammespace cluster information.

If you need any help, check out the #eng_grafana channel on slack.
