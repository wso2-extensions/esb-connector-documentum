# Working with Versions of Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Versions.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Versions, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [getcurrentversion](#documentum_getcurrentversion) | Getting the current version of the Documentum. |
| [getallversion](#documentum_getallversion)      | Getting all the Versions of the Documentum.|
| [deleteallversion](#documentum_deleteallversion)    | Deleting all the Versions of the Documentum.|



### Operation details

Following is more information about these operations.

#### Get the current version of the Document
To Get information about a Current Version of the Document, use getcurrentversion and specify the Chronical ID. 

**getcurrentversion**
```xml
<documentum.getcurrentversion>
   <repo>{$ctx:repo}</repo>
   <chronicalId>{$ctx:ChronicalID}</chronicalId>
</documentum.getcurrentversion>
```
**Properties**
* repo : The repo of the documentum.
* chronicalId : The Chronical ID of the Document.


**Sample request**

Following is a sample request that can be handled by the getcurrentversion operation.

```json
{
  "repo":"doctest",
  "chronical_id":"090277b680053e99"
}
```
**Sample response**

Given below is a sample response for the getcurrentversion operation.

```json
{
    "name": "object",
    "type": "dm_document",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_document",
    "properties": {
        "object_name": "Samplefile",
        "r_object_type": "dm_document",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-17T17:51:38.000+00:00",
        "r_modify_date": "2020-07-17T17:53:02.000+00:00",
        "r_modifier": "appowner",
        "r_access_date": "2020-07-20T06:45:52.000+00:00",
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_retention_date": null,
        "a_archive": false,
        "a_compound_architecture": "",
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
        "i_folder_id": [
            "0b0277b6800584f3"
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
        "i_contents_id": "060277b68004f389",
        "a_content_type": "pdf",
        "r_page_cnt": 1,
        "r_content_size": 52493,
        "a_full_text": true,
        "a_storage_type": "filestore_01",
        "i_cabinet_id": "0c0277b68004dbc2",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "090277b68005b444",
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
        "r_full_content_size": 52493.0,
        "a_extended_properties": null,
        "a_is_signed": false,
        "a_last_review_date": null,
        "i_retain_until": null,
        "r_aspect_name": null,
        "i_retainer_id": null,
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 2,
        "r_object_id": "090277b68005b444"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/versions/current"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444"
        },
        {
            "rel": "canonical",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b68005b444"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/parent-links",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/parent-links"
        },
        {
            "rel": "parent",
            "title": "0b0277b6800584f3",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0b0277b6800584f3"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/cabinet",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc2"
        },
        {
            "rel": "contents",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/contents"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/primary-content",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/contents/content"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/checkout",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/lock"
        },
        {
            "rel": "version-history",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/versions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/current-version",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/versions/current"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/virtual-document-conversion",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/vd-nodes"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/relations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/relations?related-object-id=090277b68005b444&related-object-role=any"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-aspects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/aspects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permission-set",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/permission-set"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permissions",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/permissions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/comments",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/comments"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/attachable-lifecycles",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/lifecycles?object-id=090277b68005b444"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-lifecycle",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/lifecycle"
        }
    ]
}
```

#### Get All the Versions of the Document

To Get information about all Versions of the Document, use getallversion and specify the Chronical ID.

**getallversion**
```xml
<documentum.getallversion>
   <repo>{$ctx:repo}</repo>
   <chronicalId>{$ctx:ChronicalID}</chronicalId>
</documentum.getallversion>
```

**Properties**
* repo : The repo of the documentum.
* chronicalId : The Chronical ID of the Document.

**Sample request**

Following is a sample request that can be handled by the getallversion operation.

```json
{
   "repo":"doctest",
   "chronical_id":"090277b680053e99"
}
```
**Sample response**

Given below is a sample response for the getallversion operation.

```json
{
    "id": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68003aa20/versions",
    "title": "All versions of chronicle object 090277b68003aa20",
    "author": [
        {
            "name": "Open Text Documentum"
        }
    ],
    "updated": "2020-07-20T07:46:56.043+00:00",
    "page": 1,
    "items-per-page": 100,
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68003aa20/versions"
        }
    ]
}
```


#### Deleting all the versions of the Document

To Delete information about the Document, use deleteallversion and specify the Chronical ID.

**deleteallversion**
```xml
<documentum.deleteallversion>
  <repo>{$ctx:repo}</repo>
  <chronicalId>{$ctx:ChronicalID}</chronicalId>
</documentum.deleteallversion>
```
**Properties**
* repo : The repo of the documentum.
* chronicalId : The Chronical ID of the Document.


**Sample request**

Following is a sample request that can be handled by the deleteallversion operation.

```json
{
"repo":"doctest",
"chronical_id":"090277b680053e99"
}
```
**Sample response**

204 will returned if the Version is successfully deleted.



