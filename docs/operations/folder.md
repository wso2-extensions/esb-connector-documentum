# Working with Folders in Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Folders.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Folders, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [createfolder](#documentum-createfolder)    | Creating folder of the Documentum. |
| [findfolder](#documentum-findfolder)      | Finding Folder of the Documentum.|
| [deletefolder](#documentum-deletefolder)    | Deleting Folder of the Documentum. |



### Operation details

Following is more information about these operations.

#### documentum-createfolder
To Create information about a specific folder.

**createfolder**
```xml
<documentum.createfolder>
  <repo>{$ctx:repo}</repo>
  <folderID>{$ctx:folderID}</folderID>
  <foldername>{$ctx:foldername}</foldername>
</documentum.createfolder>
```
**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |
| parentfolderID      | The Parent Folder Object ID or Cabinet ID | Yes |
| foldername    | The Name of Folder | Yes |


**Sample request**

Following is a sample request that can be handled by the create folder operation.

```json
{
	"repo":"doctest",
	"parentfolderID":"0c0277b68004dbc2",
	"foldername":"Demo"
}
```
**Sample response**

Given below is a sample response for the creat folder operation.

```json
{
    "name": "folder",
    "type": "dm_folder",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_folder",
    "properties": {
        "object_name": "Demo",
        "r_object_type": "dm_folder",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-24T10:16:55.000+00:00",
        "r_modify_date": "2020-07-24T10:16:55.000+00:00",
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
            "0c0277b68004dbc2"
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
        "i_cabinet_id": "0c0277b68004dbc2",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0b0277b680060faf",
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
        "r_folder_path": [
            "/TestCabinet/Demo"
        ],
        "i_ancestor_id": [
            "0b0277b680060faf",
            "0c0277b68004dbc2"
        ],
        "r_object_id": "0b0277b680060faf"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0b0277b680060faf"
        }
    ]
}
```

#### documentum-findfolder

To Find information about a specific Folder.

**findfolder**
```xml
<documentum.findfolder>
  <repo>{$ctx:repo}</repo>
  <ObjectID>{$ctx:ObjectID}</ObjectID>
</documentum.findfolder>
```

**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |
| folderObjectID    | The Object ID of the Folder | Yes |

**Sample request**

Following is a sample request that can be handled by the findfolder operation.

```json
{
  "repo":"doctest",
  "folderObjectID":"0b0277b680060faf"
}
```
**Sample response**

Given below is a sample response for the findfolder operation.

```json
{
    "name": "folder",
    "type": "dm_folder",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_folder",
    "properties": {
        "object_name": "Demo",
        "r_object_type": "dm_folder",
        "r_creation_date": "2020-07-24T10:16:55.000+00:00",
        "r_modify_date": "2020-07-24T10:16:55.000+00:00",
        "r_modifier": "appowner",
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_archive": false,
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
        "i_folder_id": [
            "0c0277b68004dbc2"
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
        "i_cabinet_id": "0c0277b68004dbc2",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0b0277b680060faf",
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
        "acl_name": "dm_450277b680000101",
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
        "i_vstamp": 0,
        "r_folder_path": [
            "/TestCabinet/Demo"
        ],
        "i_ancestor_id": [
            "0b0277b680060faf",
            "0c0277b68004dbc2"
        ],
        "r_object_id": "0b0277b680060faf"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0b0277b680060faf"
        }
    ]
}
```


#### documentum-deletefolder

To delete particular folder of the given object ID, provided if it’s empty.

**deletefolder**
```xml
<documentum.deletefolder>
  <repo>{$ctx:repo}</repo>
  <ObjectID>{$ctx:ObjectID}</ObjectID>
</documentum.deletefolder>
```
**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |
| folderObjectID    | The Object ID of the Folder | Yes |


**Sample request**

Following is a sample request that can be handled by the deletefolder operation.

```json
{
 "repo":"doctest",
 "folderObjectID":"0b0277b68004e7e2"
}
```
**Sample response**

204 will be returned if the folder is successfully deleted.
