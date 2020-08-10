Nintendo provides several eShop related services as a SOAP service:

* [`CAS (CatalogingSOAP`)](CAS-Server)
* [`ECS (ECommerceSOAP`)](ECS-Server)
* [`IAS (IdentityAuthenticationSOAP`)](IAS-Server)
* [`NUS (NetUpdateSOAP`)](NUS-Server)

The common client certificate is required to access these servers.

In addition to standard HTTP headers, a `SOAPAction` is included in requests and contains the following string: `urn:{service_code}.wsapi.broadon.com/{method_name}`.

## Request
To call a method, a POST request is sent with the following xml body:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
                   xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"
                   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                   xmlns:xsd="http://www.w3.org/2001/XMLSchema"
                   xmlns:{service_code}="urn:{service_code}.wsapi.broadon.com">
<SOAP-ENV:Body>
<{service_code}:{method_name} xsi:type="{service_code}:{method_name}RequestType">
<{service_code}:Version>{version}</{service_code}:Version>
<{service_code}:MessageId>EC-{device_id}-{random_integer}</{service_code}:MessageId>
{...}
</{service_code}:{method_name}>
</SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

Quick explanation of the fields:

* `service_code`: `ecs`, `ias`, `cas` or `nus`
* `version`: depends on service (`1.0` on nus service, `2.0` on other services)
* `device_id`: this is the device id combined with [device type](#device-type): `device_id | (device_type << 32)`. On Wii U the device id is stored in the OTP and can be retrieved with `MCP_GetDeviceId`.

[Additional parameters](#additional-parameters) depend on the service type and method.

## Response
If the method call was successful the server returns the following response. The server does not send any insignificant whitespace (I added it for readability).

```xml
<?xml version="1.0" encoding="utf-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
                  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <soapenv:Body>
        <{method_name}Response xmlns="urn:{service_code}.wsapi.broadon.com">
            <DeviceId>{device id from request}</DeviceId>
            <MessageId>{message id from request}</MessageId>
            <TimeStamp>{timestamp in milliseconds}</TimeStamp>
            <ErrorCode>0</ErrorCode>
            {...}
        </{method_name}Response>
    </soapenv:Body>
</soapenv:Envelope>
```

If an error occurs, `ErrorCode` is set to a non-zero integer and another `ErrorMessage` tag describes the error message.

## Device Type
| Type | Device |
| --- | --- |
| 1 | Wii |
| 3 | DSi |
| 4 | 3DS |
| 5 | Wii U |
| 7 | vWii |

## Additional Parameters
All parameters are prefixed with the service code.

| Name | Services | Description |
| --- | --- | --- |
| `DeviceId` | `cas`, `ecs`, `ias`, `nus` | Device id, combined with device type |
| `DeviceToken` | `cas`, `ecs`, `ias` | Device token |
| `AccountId` | `cas`, `ecs`, `ias` | Account id |
| `ApplicationId` | `cas`, `ecs` | Application id |
| `TIN` | `cas`, `ecs` | TIN |
| `Region` | `cas`, `ecs`, `ias` | Region (e.g. `EUR`) |
| `RegionId` | `nus` | Region (e.g. `EUR`) |
| `Country` | `cas`, `ecs`, `ias` | Country (e.g. `NL`) |
| `CountryCode` | `nus` | Country (e.g. `NL`) |
| `VirtualDeviceType` | `ecs`, `ias`, `nus` | Virtual device type. This overrides the device type in the device id. |
| `Language` | `cas`, `ecs`, `ias`, `nus` | Language |
| `SerialNo` | `ecs`, `nus` | Serial number |
| `Age` | `cas` | Age |
| `SessionHandle` | `ecs` | Session handle |
| `ServiceTicket` | `ecs` | Service ticket |
| `ServiceId` | `ecs` | Service id |