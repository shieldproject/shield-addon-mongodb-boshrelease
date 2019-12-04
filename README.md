# SHIELD MongoDB Add-on

This BOSH release provides add-on tools for augmenting SHIELD
Agents with various versions of the MongoDB command-line utilities
for backup and restore: mongodump, and mongorestore.

## Versions

The following versions are currently available:

 - **3.2.11** via `shield-addon-mongo-tools-3.2`
 - **3.4.1**  via `shield-addon-mongo-tools-3.4`
 - **3.6.9**  via `shield-addon-mongo-tools-3.6`
 - **4.0.13** via `shield-addon-mongo-tools-4.0`
 - **4.2.1**  via `shield-addon-mongo-tools-4.2`

All versions are compiled against golang 1.7.5.

Need a version we don't (yet) support?  Open a [Github Issue][bug]
asking that we package it up.  If possible, supply both the full
version, and a link to the canonical (mongodb.com) download page.

## Using this BOSH Release

**Note:** This BOSH release is not intended to stand on its own.
It exists to augment the `shield-agent` job of the [SHIELD BOSH
Release][1], and only in cases where the mongo* utilities
are missing.

To colocate this BOSH release with your shield-agent instance
group, just add a new job to the group:

```yaml
instance_groups:
  - name: whatever
    jobs:
      # ...
      - name:    shield-addon-mongo-tools-4.2
        release: shield-addon-mongodb
```

That's really all there is to it.

[bug]: https://github.com/shieldproject/shield-addon-mongodb-boshrelease/issues
[1]:   https://github.com/starkandwayne/shield-boshrelease
