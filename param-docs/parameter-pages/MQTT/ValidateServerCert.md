# Parameter `ValidateServerCert`
Default Value: `true`

!!! Warning
    This is an **Expert Parameter**! Only change it if you understand what it does!

Enable or disable the validation of the server certificate.

If `enabled (true)`, the certificate sent by the server is validated using the configured [Root CA Certificate file](https://jomjol.github.io/AI-on-the-edge-device-docs/Parameters/#parameter-cacert).\
The server name in [uri](https://jomjol.github.io/AI-on-the-edge-device-docs/Parameters/#parameter-uri) is compared with the CN field of the server certificate. A connection will be only established if these match.\
It ensures the origin of the server.

If `disabled (false)`, the origin (CN field) of the server will be not validated.\
If you use public brokers, make sure to set this parameter to "enabled", to avoid potential MITM-Attacks!

!!! Note
    For more information on how to create your own certificate, see: [mosquitto.org](https://mosquitto.org/man/mosquitto-tls-7.html) or [emqx.com](https://www.emqx.com/en/blog/emqx-server-ssl-tls-secure-connection-configuration-guide).

!!! Note
    The certificates are always checked for validity. This cannot be changed and is implemented into the firmware.

!!! Note
    This also means that you might have to change the protocol and port in  to `mqtts://example.com:8883`!
