# Working with Documents in Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Documents.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Documents, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [createdocument](#documentum-createdocument)    | Creating Document of the Documentum. |
| [finddocuments](#documentum-finddocuments)      | Finding Document of the Documentum.|
| [deletedocument](#documentum-deletedocument)    | Deleting Document of the Documentum. |
| [addcontenttodocument](#documentum-addcontenttodocument)    | Adding Content to the Document. |
| [createcontentfuldocument](#documentum-createcontentfuldocument)    | Creating the content full Document. |
| [getdocumentcontent](#documentum-getdocumentcontent)    | Getting the content of Document. |



### Operation details

Following is more information about these operations.

#### documentum-createdocument
To Create information about a specific Document.

**createdocument**
```xml
<documentum.createdocument>
  <repo>{$ctx:repo}</repo>
  <folderID>{$ctx:folderID}</folderID>
  <documentname>{$ctx:documentname}</documentname>
  <doctype>{$ctx:doctype}</doctype>
</documentum.createdocument>
```
**Properties**

| Parameters    | Description | Required |
| ------------- |-------------|----------|
| repo | The repo of the documentum | Yes |
| folderID | The Folder Object ID | Yes |
| object_name | The Name of Document | Yes |
| a_content_type | The type of Document content | Yes |

**Sample request**

Following is a sample request that can be handled by the create document operation.

```json
{
	"repo":"doctest",
	"folderID":"0b0277b68004e7de",
	"object_name":"Testing",
	"a_content_type":"pdf"
}
```
**Sample response**

Given below is a sample response for the create document operation.

```json
{
    "name": "document",
    "type": "dm_document",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_document",
    "properties": {
        "object_name": "Testing",
        "r_object_type": "dm_document",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-24T13:50:18.000+00:00",
        "r_modify_date": "2020-07-24T13:50:18.000+00:00",
        "r_modifier": "appowner",
        "r_access_date": null,
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_retention_date": null,
        "a_archive": false,
        "a_compound_architecture": "",
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
        "i_folder_id": [
            "0b0277b68004e7de"
        ],
        "r_composite_id": null,
        "r_composite_label": null,
        "r_component_label": null,
        "r_order_no": null,
        "r_link_cnt": 0,
        "r_link_high_cnt": 0,
        "r_assembled_from_id": "0000000000000000",
        "r_frzn_assembly_cnt": 0,
        "r_has_frzn_assembly": false,
        "resolution_label": "",
        "r_is_virtual_doc": 0,
        "i_contents_id": "0000000000000000",
        "a_content_type": "pdf",
        "r_page_cnt": 0,
        "r_content_size": 0,
        "a_full_text": true,
        "a_storage_type": "",
        "i_cabinet_id": "0c0277b68002952c",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "090277b6800610e6",
        "i_latest_flag": true,
        "r_lock_owner": "",
        "r_lock_date": null,
        "r_lock_machine": "",
        "log_entry": "",
        "r_version_label": [
            "1.0",
            "CURRENT"
        ],
        "i_branch_cnt": 0,
        "i_direct_dsc": false,
        "r_immutable_flag": false,
        "r_frozen_flag": false,
        "r_has_events": false,
        "acl_domain": "appowner",
        "acl_name": "dm_450277b680000101",
        "a_special_app": "",
        "i_is_reference": false,
        "r_creator_name": "appowner",
        "r_is_public": true,
        "r_policy_id": "0000000000000000",
        "r_resume_state": 0,
        "r_current_state": 0,
        "r_alias_set_id": "0000000000000000",
        "a_effective_date": null,
        "a_expiration_date": null,
        "a_publish_formats": null,
        "a_effective_label": null,
        "a_effective_flag": null,
        "a_category": "",
        "language_code": "",
        "a_is_template": false,
        "a_controlling_app": "",
        "r_full_content_size": 0.0,
        "a_extended_properties": null,
        "a_is_signed": false,
        "a_last_review_date": null,
        "i_retain_until": null,
        "r_aspect_name": null,
        "i_retainer_id": null,
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 0,
        "r_object_id": "090277b6800610e6"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b6800610e6"
        }
    ]
}
```

#### documentum-finddocuments

To find all documents under specific folder.

**finddocuments**
```xml
<documentum.finddocuments>
 <repo>{$ctx:repo}</repo>
 <folderID>{$ctx:folderID}</folderID>
</documentum.finddocuments>
```

**Properties**

| Parameters    | Description | Required |
| ------------- |-------------|----------|
| repo | The repo of the documentum | Yes |
| folderID | The Object ID of the Folder | Yes |

**Sample request**

Following is a sample request that can be handled by the finddocuments operation.

```json
{
	"repo":"doctest",
	"folderID":"0b0277b68004f741"
}
```
**Sample response**

Given below is a sample response for the finddocuments operation.

```json
{
    "id": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0b0277b68004f741/documents",
    "title": "Documents under folder 0b0277b68004f741",
    "author": [
        {
            "name": "Open Text Documentum"
        }
    ],
    "updated": "2020-07-24T10:27:43.399+00:00",
    "page": 1,
    "items-per-page": 100,
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0b0277b68004f741/documents"
        }
    ],
    "entries": [
        {
            "id": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b680053e9b",
            "title": "SampleDoc",
            "author": [
                {
                    "name": "appowner",
                    "uri": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/users/appowner"
                }
            ],
            "summary": "dm_document 090277b680053e9b",
            "updated": "2020-07-13T09:59:22.000+00:00",
            "published": "2020-07-13T09:59:22.000+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b680053e9b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b680053e9b"
            }
        }
    ]
}
```


#### documentum-deletedocument

To Delete information about a specific Document.

**deletedocument**
```xml
<documentum.deletedocument>
 <repo>{$ctx:repo}</repo>
 <docObjID>{$ctx:docObjID}</docObjID>
</documentum.deletedocument>
```
**Properties**

| Parameters    | Description | Required |
| ------------- |-------------|----------|
| repo | The repo of the documentum | Yes |
| documentObjectID | The Object ID of the Document | Yes |

**Sample request**

Following is a sample request that can be handled by the deletedocument operation.

```json
{
  "repo":"doctest",
  "documentObjectID":"090277b680047c8e"
}
```
**Sample response**

204 will be returned if the document is successfully deleted.

#### documentum-addcontenttodocument
To Add Content information about a specific Document.

**addcontenttodocument**
```xml
<documentum.addcontenttodocument>
  <repo>{$ctx:repo}</repo>
  <objectID>{$ctx:objectID}</objectID>
  <format>{$ctx:format}</format>
  <overwrite>{$ctx:overwrite}</overwrite>
</documentum.addcontenttodocument>
```
**Properties**

| Parameters    | Description | Required | Remarks |
| ------------- |-------------|----------| ------- |
| repo | The repo of the documentum | Yes | URL Query Param |
| objectID | The Object ID of the Document | Yes | URL Query Param |
| format | The Format of the Document Content | Yes | URL Query Param |
| overwrite | Enter “true or false” for overwriting condition | Optional(Boolean) | URL Query Param |



**Sample request**

Following is a sample request that can be handled by the add content to document operation.

click form data in postman and enter key value as below and attach the file to be uploaded.

| KEY       | VALUE |
| ------------- |-------------|
| request  -------     [File] |  file123.pdf |


**Sample response**

Given below is a sample response for the add content to document operation.


```json
{
    "name": "content",
    "properties": {
        "r_object_id": "060277b6800549b0",
        "rendition": 0,
        "parent_count": 1,
        "content_size": 1319894,
        "full_format": "pdf",
        "format": "270277b68000019f",
        "encoding": "",
        "set_time": "2020-07-24T13:56:06.000+00:00",
        "full_content_size": 1319894.0,
        "is_archived": 0,
        "is_offline": 0,
        "resolution": 0,
        "x_range": 0,
        "y_range": 0,
        "z_range": 0,
        "parent_id": [
            "090277b6800610e6"
        ],
        "page": [
            0
        ],
        "page_modifier": [
            ""
        ],
        "r_content_hash": "",
        "i_vstamp": 0,
        "i_position": [
            -1
        ]
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b6800610e6/contents/content?format=pdf&modifier=&page=0"
        }
    ]
}
```
#### documentum-createcontentfuldocument

To create the document along with content in a single API call.

**createcontentfuldocument**

```xml
<documentum.createcontentfuldocument>
  <repo>{$ctx:repo}</repo>
  <objectID>{$ctx:objectID}</objectID>
  <format>{$ctx:format}</format>
  <count>{$ctx:count}</count>
  <primary>{$ctx:primary}</primary>
</documentum.createcontentfuldocument>
```
**Properties**

| Parameters    | Description | Required | Remarks |
| ------------- |-------------|----------| ------- |
| repo | The repo of the documentum | Yes | URL Query Param |
| objectID | The Object ID of the Document | Yes | URL Query Param |
| format | The Format of the Document Content | Yes | URL Query Param |
| count | The Count of the Documents | Yes | URL Query Param |
| primary | The condition to set all-primary as true or false | Optional(Boolean) | URL Query Param |

**Sample request**

Following is a sample request that can be handled by the create content full document operation.

click form data in postman and enter key values as below and attach the file to be uploaded.

| KEY       | VALUE |
| ------------- |-------------|
| objects   -------      [Text] |  {"properties":{"r_object_type": "dm_document","object_name": "TestDoc"}}|
| content1  -------      [File] |  Document.pdf (can be one or many)|


**Sample response**

Given below is a sample response for the create content full document operation.

```json
{
    "name": "document",
    "type": "dm_document",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_document",
    "properties": {
        "object_name": "TestDoc",
        "r_object_type": "dm_document",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-24T14:13:52.000+00:00",
        "r_modify_date": "2020-07-24T14:13:52.000+00:00",
        "r_modifier": "appowner",
        "r_access_date": null,
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_retention_date": null,
        "a_archive": false,
        "a_compound_architecture": "",
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
        "i_folder_id": [
            "0b0277b68004e7de"
        ],
        "r_composite_id": null,
        "r_composite_label": null,
        "r_component_label": null,
        "r_order_no": null,
        "r_link_cnt": 0,
        "r_link_high_cnt": 0,
        "r_assembled_from_id": "0000000000000000",
        "r_frzn_assembly_cnt": 0,
        "r_has_frzn_assembly": false,
        "resolution_label": "",
        "r_is_virtual_doc": 0,
        "i_contents_id": "060277b680054a9c",
        "a_content_type": "pdf",
        "r_page_cnt": 2,
        "r_content_size": 539300,
        "a_full_text": true,
        "a_storage_type": "filestore_01",
        "i_cabinet_id": "0c0277b68002952c",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "090277b6800610eb",
        "i_latest_flag": true,
        "r_lock_owner": "",
        "r_lock_date": null,
        "r_lock_machine": "",
        "log_entry": "",
        "r_version_label": [
            "1.0",
            "CURRENT"
        ],
        "i_branch_cnt": 0,
        "i_direct_dsc": false,
        "r_immutable_flag": false,
        "r_frozen_flag": false,
        "r_has_events": false,
        "acl_domain": "appowner",
        "acl_name": "dm_450277b680000101",
        "a_special_app": "",
        "i_is_reference": false,
        "r_creator_name": "appowner",
        "r_is_public": true,
        "r_policy_id": "0000000000000000",
        "r_resume_state": 0,
        "r_current_state": 0,
        "r_alias_set_id": "0000000000000000",
        "a_effective_date": null,
        "a_expiration_date": null,
        "a_publish_formats": null,
        "a_effective_label": null,
        "a_effective_flag": null,
        "a_category": "",
        "language_code": "",
        "a_is_template": false,
        "a_controlling_app": "",
        "r_full_content_size": 539300.0,
        "a_extended_properties": null,
        "a_is_signed": false,
        "a_last_review_date": null,
        "i_retain_until": null,
        "r_aspect_name": null,
        "i_retainer_id": null,
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 0,
        "r_object_id": "090277b6800610eb"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b6800610eb"
        }  
    ]
}
```
#### documentum-getdocumentcontent

To Getting content information about a specific Document.

**getdocumentcontent**
```xml
<documentum.getdocumentcontent>
 <repo>{$ctx:repo}</repo>
 <objectID>{$ctx:objectID}</objectID>
</documentum.getdocumentcontent>
```
**Properties**

| Parameters    | Description | Required |
| ------------- |-------------|----------|
| repo | The repo of the documentum | Yes |
| documentObjectID | The  Object ID of the Document | Yes |

**Sample request**

Following is a sample request that can be handled by the getdocumentcontent operation.

```json
{
  "repo":"doctest",
  "documentObjectID":"090277b6800600a3"
}
```
**Sample response**

Given below is a sample response for the get document content operation.

```json
{
    "name": "content",
    "properties": {
        "object_name": "sample",
        "r_object_id": "060277b680053dce",
        "rendition": 0,
        "full_format": "pdf",
        "format": "270277b68000019f",
        "full_content_size": 9689.0,
        "set_time": "2020-07-23T12:52:46.000+00:00",
        "r_content_hash": "",
        "i_vstamp": 0,
        "mime_type": "application/pdf",
        "dos_extension": "pdf",
        "format_name": "pdf",
        "parent_id": [
            "090277b6800600a3"
        ],
        "page": [
            0
        ],
        "page_modifier": [
            null
        ]
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b6800600a3/contents/content"
        },
        {
            "rel": "enclosure",
            "title": "ACS",
            "href": "http://IDFBAVM0231.googlecom:9080/ACS/servlet/ACS?command=read&version=2.3&docbaseid=0277b6&basepath=C%3A%5CDocumentum%5Cdata%5Cdoctest%5Ccontent_storage_01%5C000277b6&filepath=80%5C04%5C55%5Cf5.pdf&objectid=090277b6800600a3&cacheid=dAAEAgA%3D%3D9VUEgA%3D%3D&format=pdf&pagenum=0&signature=dW9snm%2BgQj6BEp0eDpuYq0MzpM0JwJiDrQ4lUdkQy9OC%2FUU3BPpWM8ZP4j2GF%2FKjUJhwpM46alaZiyEJb8je4rI90t3Z%2BQfsgDf9JqDQ0AEwIGcDzhqCH1A%2Fki44dsY%2FoMrD5GpnxSZFNEyRw1%2BB4R%2BR4fdt7opfLf5K2yqHzXY%3D&servername=INFBAVM0331ACS1&mode=1&timestamp=1596018462&length=9689&mime_type=application%2Fpdf&parallel_streaming=true&expire_delta=360"
        }
    ]
}
```

**Read Document Content**

Click on "enclosure" href link from the getdocumentcontent operation response.
Link will open the another tab. Here Click on Save Response choose Save to a file.
The file will be save in your local machine, go to the file read the document content.
