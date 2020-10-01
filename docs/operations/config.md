# Configuring Documentum Operations

[[Prerequisites]](#Prerequisites) [[Initializing the connector]](#initializing-the-connector)

## Prerequisites

> NOTE: To work with the Documentum connector, you need to have a Documentum account. 

To use the Documentum connector, add the <documentum.init> element in your configuration before carrying out any other Documentum operation.

This Documentum configuration authenticates with Documentum by specifying the user name, password, and URI of the Documentum instance.


## Compatibility

| Connector version | Supported Documentum REST API version | Supported WSO2 ESB/EI version |
| ------------- | ------------- | ------------- |
| [1.0.0](https://github.com/dilti/WSO2DocumentumConnectorV1/blob/master/Connector/org.wso2.carbon.esb.connector.documentum/target/documentum-connector-1.0.0.zip) | v16.7 | EI 7.0.x, EI 6.6.0, EI 6.5.0, EI 6.4.0 |

### Enable Message Builder and Formatter

Ensure that the following Axis2 configurations are added and enabled in the <ESB_HOME>/repository/conf/axis2/axis2.xml file or in <EI_HOME>/conf/axis2/axis2.xml file.

* Required message formatter

    ```xml
    <messageFormatter contentType="application/vnd.emc.documentum+json" 
                   class="org.wso2.carbon.integrator.core.json.JsonStreamFormatter"/>
 
    <messageFormatter contentType="multipart/form-data"
                        class="org.wso2.carbon.relay.ExpandingMessageFormatter"/>
    ```
* Required message builder

    ```xml
    <messageBuilder contentType="application/vnd.emc.documentum+json" 
                class="org.wso2.carbon.integrator.core.json.JsonStreamBuilder"/>

    <messageBuilder contentType="multipart/form-data"
                        class="org.wso2.carbon.relay.BinaryRelayBuilder"/>
    ```


> NOTE: If you want the connector to perform blocking invocations, you need to add and enable the following builders and formatter in the <ESB_HOME>/repository/conf/axis2/axis2_blocking_client.xml file or in <EI_HOME>/conf/axis2/axis2_blocking_client.xml file.

## Initializing the connector

Add the following <documentum.init>  method in your configuration:
 
#### init
```xml
<documentum.init>
    <username>{$ctx:username}</username>
    <password>{$ctx:password}</password>
    <uri>{$ctx:uri}</uri>
    <blocking>{$ctx:blocking}</blocking>
</documentum.init>
```
**Properties** 

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| username          | The username of the Documentum API | Yes |
| password   | The password of the Documentum API | Yes |
| uri   | The instance URI(Base URL) of Documentum API | Yes |
| blocking   | Set true or false, this property helps the connector perform blocking invocations to Documentum | Optional(Boolean) |


**Related  documentation**

[Working with ACLs in Documentum](acls.md)

[Working with Cabinets in Documentum](cabinet.md)

[Working with Documents in Documentum](document.md)

[Working with Folders in Documentum](folder.md)

[Working with Sys Object of Documentum](sysobject.md)

[Working with Versions of Documentum](versions.md)



