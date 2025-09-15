## Migrating from previous installation
To import data from an other influxDB installation : 
- Export the data as line-protocol from the previous server ([see wiki](https://docs.influxdata.com/influxdb/v2/write-data/migrate-data/migrate-oss/)) : 
```
influxd inspect export-lp \
  --bucket-id 12ab34cd56ef \
  --engine-path ~/.influxdbv2/engine \
  --output-path path/to/export.lp
  --compress
```
- Add the generated file to `./files`
- Add the file to the `influx_migrate_file` variable in `host_vars/<hostname>/vars.yml`

> Make sure to remove it from the configuration after this initial install otherwise each subsequent update will reupload the data