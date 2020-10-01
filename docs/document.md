# Working with Documents in Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Documents.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Documents, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [createdocument](#documentum_createdocument)    | Creating Document of the Documentum. |
| [finddocuments](#documentum_finddocuments)      | Finding Document of the Documentum.|
| [deletedocument](#documentum_deletedocument)    | Deleting Document of the Documentum. |



### Operation details

Following is more information about these operations.

#### Create information about a Document
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
* repo : The repo of the documentum.
* folderID : The Folder Obeject ID.
* documentname : The Name of Document.
* doctype : The type of Document content.

**Sample request**

Following is a sample request that can be handled by the create document operation.

```json
{
  "repo":"doctest",
  "folderID":"0b0277b68004312a",
  "object":"documents",
  "object_name":"SampleDoc21"
}
```
**Sample response**

Given below is a sample response for the creat document operation.

```json
{
    "name": "document",
    "type": "dm_document",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_document",
    "properties": {
        "object_name": "TestDocument0107",
        "r_object_type": "dm_document",
        "title": "SampleDoc21",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-20T14:27:02.000+00:00",
        "r_modify_date": "2020-07-20T14:27:02.000+00:00",
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
            "0c0277b680000104"
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
        "a_content_type": "",
        "r_page_cnt": 0,
        "r_content_size": 0,
        "a_full_text": true,
        "a_storage_type": "",
        "i_cabinet_id": "0c0277b680000104",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "090277b68005d8e8",
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
        "r_object_id": "090277b68005d8e8"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005d8e8"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005d8e8"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005d8e8"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/parent-links",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/parent-links"
        },
        {
            "rel": "parent",
            "title": "0c0277b680000104",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b680000104"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/cabinet",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b680000104"
        },
        {
            "rel": "contents",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/contents"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/primary-content",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/contents/content"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/checkout",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/lock"
        },
        {
            "rel": "version-history",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/versions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/current-version",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/versions/current"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/relations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/relations?related-object-id=090277b68005d8e8&related-object-role=any"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-aspects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/aspects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permission-set",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/permission-set"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permissions",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/permissions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/virtual-document-conversion",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/vd-nodes"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/comments",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/comments"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/attachable-lifecycles",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/lifecycles?object-id=090277b68005d8e8"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-lifecycle",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005d8e8/lifecycle"
        }
    ]
}
```

#### Find information about a Document

To Find information about a specific Folder.

**finddocuments**
```xml
<documentum.finddocuments>
 <repo>{$ctx:repo}</repo>
 <folderID>{$ctx:folderID}</folderID>
</documentum.finddocuments>
```

**Properties**
* repo : The repo of the documentum.
* folderID : The Object ID of the Folder.

**Sample request**

Following is a sample request that can be handled by the finddocuments operation.

```json
{
 "repo":"doctest",
 "folderID":"0b0277b680043127",
}
```
**Sample response**

Given below is a sample response for the finddocuments operation.

```json
{
    "id": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b680000104/documents",
    "title": "Documents under folder 0c0277b680000104",
    "author": [
        {
            "name": "Open Text Documentum"
        }
    ],
    "updated": "2020-07-20T14:29:17.894+00:00",
    "page": 1,
    "items-per-page": 100,
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b680000104/documents"
        }
    ],
    "entries": [
        {
            "id": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005d8e8",
            "title": "TestDocument0107",
            "author": [
                {
                    "name": "appowner",
                    "uri": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/users/appowner"
                }
            ],
            "summary": "dm_document 090277b68005d8e8",
            "updated": "2020-07-20T14:27:02.000+00:00",
            "published": "2020-07-20T14:27:02.000+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005d8e8"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005d8e8"
            }
        },
        {
            "id": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b6800598ae",
            "title": "TestDocument0107",
            "author": [
                {
                    "name": "appowner",
                    "uri": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/users/appowner"
                }
            ],
            "summary": "dm_document 090277b6800598ae",
            "updated": "2020-07-16T04:54:36.000+00:00",
            "published": "2020-07-16T04:54:36.000+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b6800598ae"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b6800598ae"
            }
        }
    ]
}
```


#### Deleting Document

To Delete information about a specific Document.

**deletedocument**
```xml
<documentum.deletedocument>
 <repo>{$ctx:repo}</repo>
 <docObjID>{$ctx:docObjID}</docObjID>
</documentum.deletedocument>
```
**Properties**
* repo : The repo of the documentum.
* docObjID : The  Object ID of the Document.


**Sample request**

Following is a sample request that can be handled by the deletedocument operation.

```json
{
  "repo":"doctest",
  "documentObjectID":"090277b680047c8e"
}
```
**Sample response**

204 will returned if the document is successfully deleted.



