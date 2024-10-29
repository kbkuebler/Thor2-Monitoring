## Use this for Thor1 installations
![Screenshot_20240701_174214](https://github.com/kbkuebler/Monitoring/assets/19337069/cdcb044c-e444-4975-b116-44019b5a155c)

## Hammerspace Monitoring Stack

This should help as a Promhetheus/Grafana quick start for SEs and others that just want to test things out in a non-production environment.
In order to get started, clone this repo and change the values of `prometheus/prometheus.yaml` to what's appropriate for your Hammerspace cluster.

Note: *It's recommended that you're on the latest version of Hammerspace (Version 5.0.7 or greater).For older versions, please see the Hammerspace documentation.*

1. SSH into your anvil and enable the Prometheus exporters:
`cluster-update --prometheus-exporters-enable`

2. Once that has been done, go to folder that has the `docker-compose.yaml` file and run `docker compose up` and monitor the output. If everything has come up and is working as desired, you can `ctrl-c` and then restart with `docker compose up -d` and you should be able to demo and POC.

3. You can now go to `yourdockerhost:3000` and you should see the Grafana logo. The default login and password is `admin:admin1`. 

4. Click on 'Dashboards' to see your Hammespace cluster information.

If you need any help, check out the #eng_grafana channel on slack.
