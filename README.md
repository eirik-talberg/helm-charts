# Taldev Helm Charts

This repo contains my helm charts. You can use them, fork them or just copy them if you'd like. Some configurations are quite specific to my usage and will be more tightly coupled to my [homelab](https://github.com/eirik-talberg/homelab) environment.

## Acknowledgements

I'm not doing much of the heavy lifting here, so I'd like to acknowledge the people who make this project easier.

### bjw-s' Common chart

The charts in this repo will, whenever possible, utilise the great work by [bjw-s](https://github.com/bjw-s) and their library helm chart. These charts have massively simplified creating and managing these charts for my own use case. 

### Onedr0p's containers

Again, wherever possible, I try to use their well-structured and up-to-date container images for my charts. 

[Onedr0p @ GitHub](https://github.com/onedr0p/containers)

## Available charts

| Chart name              | Current version | Application version |
|-------------------------|-----------------|---------------------|
| [sonarr](charts/sonarr) | 0.1.0           | 3.0.10.1567         |


## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add taldev https://eirik-talberg.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
taldev` to see the charts.

To install a chart from this repo:

    helm install <release-name> taldev/<chart-name>

To uninstall the chart:

    helm delete <release-name>