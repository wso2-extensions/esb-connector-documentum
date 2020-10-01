# Working with Versions of Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Versions.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Versions, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [getcurrentversion](#documentum-getcurrentversion) | Getting the current version of the Documentum. |
| [getallversion](#documentum-getallversion)      | Getting all the Versions of the Documentum.|
| [deleteallversion](#documentum-deleteallversion)    | Deleting all the Versions of the Documentum.|



### Operation details

Following is more information about these operations.

#### documentum-getcurrentversion
To Get information about a Current Version of the Document, use getcurrentversion and specify the Chronical ID. 

**getcurrentversion**
```xml
<documentum.getcurrentversion>
   <repo>{$ctx:repo}</repo>
   <chronicalId>{$ctx:ChronicalID}</chronicalId>
</documentum.getcurrentversion>
```
**Properties**

| Parameters    | Description | Required |
| ------------- |-------------| --------  |
| repo | The repo of the documentum | Yes  |
| chronical_id | The Chronical ID of the Document | Yes  |

**Sample request**

Following is a sample request that can be handled by the getcurrentversion operation.

```json
{
	"repo":"doctest",
	"chronical_id":"0b0277b680048998"
}
```
**Sample response**

Given below is a sample response for the getcurrentversion operation.

```json
{
    "name": "object",
    "type": "dm_folder",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_folder",
    "properties": {
        "object_name": "testfolder001",
        "r_object_type": "dm_folder",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-01T08:38:42.000+00:00",
        "r_modify_date": "2020-07-01T08:39:54.000+00:00",
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
        "r_link_cnt": 4,
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
        "i_chronicle_id": "0b0277b680048998",
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
        "i_vstamp": 3,
        "r_folder_path": [
            "/TestConnector/testfolder001"
        ],
        "i_ancestor_id": [
            "0b0277b680048998",
            "0c0277b680000104"
        ],
        "r_object_id": "0b0277b680048998"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0b0277b680048998/versions/current"
        }
    ]
}
```

#### documentum-getallversion

To Get information about all Versions of the Document, use getallversion and specify the Chronical ID.

**getallversion**
```xml
<documentum.getallversion>
   <repo>{$ctx:repo}</repo>
   <chronicalId>{$ctx:ChronicalID}</chronicalId>
</documentum.getallversion>
```

**Properties**

| Parameters    | Description | Required |
| ------------- |-------------| --------  |
| repo | The repo of the documentum | Yes  |
| chronical_id | The Chronical ID of the Document | Yes  |

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
    "id": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68003aa20/versions",
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
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68003aa20/versions"
        }
    ]
}
```


#### documentum-deleteallversion

To Delete information about the Document, use deleteallversion and specify the Chronical ID.

**deleteallversion**
```xml
<documentum.deleteallversion>
  <repo>{$ctx:repo}</repo>
  <chronicalId>{$ctx:ChronicalID}</chronicalId>
</documentum.deleteallversion>
```
**Properties**

| Parameters    | Description | Required |
| ------------- |-------------| --------  |
| repo | The repo of the documentum | Yes  |
| chronical_id | The Chronical ID of the Document | Yes  |

**Sample request**

Following is a sample request that can be handled by the deleteallversion operation.

```json
{
"repo":"doctest",
"chronical_id":"090277b680053e99"
}
```
**Sample response**

204 will be returned if the Version is successfully deleted.



