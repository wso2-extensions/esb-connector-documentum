# Working with Sys Object of Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Sys Object.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Sys Object, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [findsysobject](#documentum-findsysobject) | finding the Sys Object of the Document. |


### Operation details

Following is more information about these operations.

#### documentum-findsysobject
To Finding information about Sys Object of the Document, use findsysobject and specify the Object ID. 

**findsysobject**
```xml
<documentum.findsysobject>
  <repo>{$ctx:repo}</repo>
  <objectID>{$ctx:ObjectID}</objectID>
</documentum.findsysobject>
```
**Properties**

| Parameters    | Description | Required |
| ------------- |-------------| ---------|
| repo | The repo of the documentum | Yes |
| objectID | The Object ID of the Document | Yes |

**Sample request**

Following is a sample request that can be handled by the findsysobject operation.

```json
{
	"repo":"doctest",
	"objectID":"0b0277b68004e7de"
}
```
**Sample response**

Given below is a sample response for the findsysobject operation.

```json
{
    "name": "object",
    "type": "dm_folder",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_folder",
    "properties": {
        "object_name": "Demo",
        "r_object_type": "dm_folder",
        "r_creation_date": "2020-07-02T06:28:39.000+00:00",
        "r_modify_date": "2020-07-02T06:28:39.000+00:00",
        "r_modifier": "appowner",
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_archive": false,
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
        "i_folder_id": [
            "0c0277b68002952c"
        ],
        "r_link_cnt": 0,
        "r_link_high_cnt": 0,
        "r_assembled_from_id": "0000000000000000",
        "r_frzn_assembly_cnt": 0,
        "r_has_frzn_assembly": false,
        "r_is_virtual_doc": 0,
        "i_contents_id": "0000000000000000",
        "r_page_cnt": 0,
        "r_content_size": 0,
        "a_full_text": true,
        "i_cabinet_id": "0c0277b68002952c",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 1,
        "world_permit": 3,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0b0277b68004e7de",
        "i_latest_flag": true,
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
        "acl_name": "TestACL24",
        "i_is_reference": false,
        "r_creator_name": "appowner",
        "r_is_public": true,
        "r_policy_id": "0000000000000000",
        "r_resume_state": 0,
        "r_current_state": 0,
        "r_alias_set_id": "0000000000000000",
        "a_is_template": false,
        "r_full_content_size": 0.0,
        "a_is_signed": false,
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 1,
        "r_folder_path": [
            "/WSO2 Connector/Demo"
        ],
        "i_ancestor_id": [
            "0b0277b68004e7de",
            "0c0277b68002952c"
        ],
        "r_object_id": "0b0277b68004e7de"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0b0277b68004e7de"
        }
    ]
}
```




