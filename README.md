# Helm Charts

## TLDR

```console
helm repo add datarobot-oss https://datarobot-oss.github.io/helm-charts
helm search repo datarobot-oss
helm install my-release datarobot-oss/<chart>
```

## Contributing

Contributions are welcome ❤️

This repository has multiple Github Actions to ensure quality is high, these include:

- [chart-testing](https://github.com/helm/chart-testing): lint and install tests
- [helm-docs](https://github.com/norwoodj/helm-docs): check all chart `README.md` have all values documented
- [helm-conftest](https://github.com/instrumenta/helm-conftest): Ensures standard labels are present

All chart `README.md` files are generated from a template. This ensures all values are documented and that formatting is consistent. See [here](https://github.com/norwoodj/helm-docs#valuesyaml-metadata) about how the table of values is produced and how to add descriptions to your chart values.

### Opening a PR

Follow these steps:

1. Fork this repo
2. Make desired changes to the chart
3. Bump the chart version
4. Regenerate the chart `README.md`: `docker run --rm -v "${PWD}:/helm-docs" jnorwood/helm-docs:v1.11.0 --template-files ./ci/README.md.gotmpl`
5. Commit and push changes
6. Open 1 pull request per chart you want to change
7. Set pull request title to `[stable/<chart name>]: <description>`

### Running CI tests locally

All commands to be run from the root of this repo.

`chart-testing`:

  ```console
  brew install chart-testing
  pip3 install yamale yamllint
  ct lint --charts stable/<chart>
  ```

`helm-docs`:

  To generate chart `README.md` files from the [template](ci/README.md.gotmpl):

  ```console
  docker run --rm -v "${PWD}:/helm-docs" jnorwood/helm-docs:v1.11.0 --template-files ./ci/README.md.gotmpl
  ```

`helm-conftest`:

  ```console
  brew tap instrumenta/instrumenta
  brew install conftest
  sh ci/helm-conftest.sh
  ```
