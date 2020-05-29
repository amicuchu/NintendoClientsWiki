Nintendo provides several eShop related services as a SOAP service:

* `CAS (CatalogingSOAP`)
* [`NUS (NetUpdateSOAP`)](NUS-Server)
* `IAS (IdentityAuthenticationSOAP`)
* `ECS (ECommerceSOAP`)

The common client certificate is required to access these servers.

In addition to standard HTTP headers, a SOAPAction is included in requests and contains the following string: `urn:{service_code}.wsapi.broadon.com/{method_name}`.

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
* `device_id`: `MCP_GetDeviceId() | (platform_id << 32)`. The platform id is 5 on Wii U.