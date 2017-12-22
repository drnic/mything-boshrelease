# BOSH release for mything

This BOSH release and deployment manifest deploy a cluster of mything.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=mything
git clone https://github.com/cloudfoundry-community/mything-boshrelease.git
bosh deploy mything-boshrelease/manifests/mything.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `mything-boshrelease` are released the `manifests/mything.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=mything
cd mything-boshrelease
git pull
cd -
bosh deploy mything-boshrelease/manifests/mything.yml
```
