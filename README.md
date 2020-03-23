# SenseCAP-IoTCentral-Bridge
A bridge that forwards SenseCAP's telemetry to Azure IoT Central

#### Download
[Click to download](https://github.com/Seeed-Solution/SenseCAP-IoTCentral-Bridge/releases)

#### How To Use
0. Sign up a sensecap account, and bind devices to it.
0. Create an access key in the portal of sensecap, and record the "organization id" and "access key".
0. Create an azure iot central instance, record the "id scope" and "sas", and import the provided sensecap model of iot central.
0. Download the bridge application, and change the `config/default.yaml` file.
0. Run the application 
```bash
chmod +x sensecap-iotcentral-bridge-linux && ./sensecap-iotcentral-bridge-linux
```

#### Configuration
| Name | Must Change | Description |
| --- | --- | --- |
| sensecap.orgid | Y | change to your sensecap account's organization id |
| sensecap.ak | Y | change to your sensecap account's access key. |
| iotcentral.idscope | Y | ID Scope, from your Azure Iot Central Instance. |
| iotcentral.sas | Y | SaS, from your Azure Iot Central Instance. |
| sensecap.clientid | N | if "none", the bridge will only forward data since it starts. Otherwise, Specify a different clientid string, the bridge will have the "retain" feature of MQTT 3.1.1. |
| sensecap.region | N | "global" or "china", depends on your account. |
| log.level | N | the level of logger |
| whitelist.enable | N | if enabled, the bridge will only forward the aimed devices to iot central. |
| whitelist.euis | N | Only when `whitelist.enable` is `true`, the white list filter. |
