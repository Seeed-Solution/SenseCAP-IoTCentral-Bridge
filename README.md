# SenseCAP-IoTCentral-Bridge
A bridge that forwards SenseCAP's telemetry to Azure IoT Central

#### Download
[Click to download](https://github.com/Seeed-Solution/SenseCAP-IoTCentral-Bridge/releases)

#### How To Use
0. Sign up a sensecap account, and bind devices to it.
0. Create an access key in the portal of sensecap, and record the "organization id" and "access key".
0. Create an azure iot central instance, record the "id scope" and "sas", and import the provided sensecap model to the iot central instance.
0. Change the `config/default.yaml` file.
0. Run the bridge:
```bash
# for linux
chmod +x sensecap-iotcentral-bridge-linux && ./sensecap-iotcentral-bridge-linux

# for macos
chmod +x sensecap-iotcentral-bridge-macos && ./sensecap-iotcentral-bridge-macos

# for windows
# Run .exe
```

#### Configuration
| Name | Should Be Configured | Description |
| --- | :---: | --- |
| sensecap.orgid | Y | change to your sensecap account's organization id. |
| sensecap.ak | Y | change to your sensecap account's access key. |
| iotcentral.idscope | Y | id scope, from your Azure Iot Central Instance. |
| iotcentral.sas | Y | sas, from your Azure Iot Central Instance. |
| sensecap.clientid | N | if "none", the bridge will only forward data since it starts. Otherwise, config a different clientid string, the bridge will have the "retain" feature of MQTT. Defaults to `(current system milliseconds)`. |
| sensecap.region | N | "global" or "china", depends on your account. Defaults to `global`. |
| log.level | N | the level of the bridge logger. Defaults to `debug`. |
| whitelist.enable | N | if enabled, the bridge will only forward the specified devices to iot central. Defaults to `false`. |
| whitelist.euis | N | only when `whitelist.enable` is `true`, the white list filter. Defaults to `[]`. |
