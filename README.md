# hockeyapp-upload-buildkite-plugin

A [Buildkite](https://buildkite.com/) plugin to upload iOS app builds to [HockeyApp](https://hockeyapp.net/).

## Example

```yml
steps:
  - name: ":package:"
    command: .ci-scripts/build-and-archive.sh
    env:
      HOCKEYAPP_APP_ID: 123456789abcdef
    plugins:
      - hockeyapp-upload:
          path-ipa: .ci-artifacts/Xyzzy.ipa
          path-dsym-zip: .ci-artifacts/Xyzzy.app.dSYM.zip
          notify: true
```

## Configuring

### `HOCKEYAPP_API_TOKEN`

## Options

### `api-token`

Specifies the HockeyApp API token

### `api-token-from`

Specifies the environment variable containing the HockeyApp API token

Default: `HOCKEYAPP_API_TOKEN`

### `app-id`

Specifies the HockeyApp Application ID

### `app-id-from`

Specifies the environment variable containing the HockeyApp Application ID

Default: `HOCKEYAPP_APP_ID`

### `path-ipa`

Specifies the path to the .ipa to upload

### `path-dsym-zip` (optional)

Specifies the path to a .dSYM.zip to upload

### `notify`

Whether or not to send notifications regarding the uploaded build

## License

MPL 2.0 (see [LICENSE](LICENSE))
