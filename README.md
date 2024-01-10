## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    helm repo add <alias> https://agalliani.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve the latest versions of the packages.
You can then run `helm search repo<alias>` to see the charts.

To install the `<chart-name>` chart:

    helm install `my-<chart-name> <alias>/<chart-name>`

To uninstall the chart:

    helm delete my-<chart-name>


## Development trick

When you want to test the template rendering, but not actually install anything, you can use 

    helm install --debug --dry-run goodly-guppy ./mychart

This will render the templates. But instead of installing the chart, it will return the rendered template to you so you can see the output
Using `--dry-run` will make it easier to test your code, but it won't ensure that Kubernetes itself will accept the templates you generate. It's best not to assume that your chart will install just because `--dry-run` works.

## Access to the index.yaml 

Visit the page: [https://agalliani.github.io/helm-charts/index.yaml](https://agalliani.github.io/helm-charts/index.yaml)
