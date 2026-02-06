Config map is used to store configuration data.

Secret is used to store sensitive data. In this chart Secrets stores an api token defined in values.yaml

Helm Lifecycle:
- helm upgrade --nstall ( Installs a release or upgrades it)
- Each change creates a new version
- helm history ( shows all revisions of a release)
- helm rollback ( restores a previous version)
