# Working with Cabinets in Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Cabinets.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Cabinets, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [createcabinet](#documentum_createcabinet)    | Creating Cabinet of the Documentum. |
| [findcabinet](#documentum_findcabinet)      | Finding Cabinet of the Documentum.|
| [deletecabinet](#documentum_deletecabinet)    | Deleting Cabinet of the Documentum. |
| [getcabinets](#documentum_getcabinets)  | Getting the all the Cabinets from the Documentum. |


### Operation details

Following is more information about these operations.

#### Create information about a Cabinet
To Create information about a specific Cabinet, use createcabinet and specify the Cabinet name. 

**createcabinet**
```xml
<documentum.createcabinet>
  <repo>{$ctx:repo}</repo>
  <cabinetname>{$ctx:cabinetname}</cabinetname>
</documentum.createcabinet>
```
**Properties**
* repo : The repo of the documentum.
* cabinetname : The Cabinet Name of the Documentum.

**Sample request**

Following is a sample request that can be handled by the create cabinet operation.

```json
{
"repo":"doctest",
"object_name":"TestCabinet789"
}
```
**Sample response**

Given below is a sample response for the createacl operation.

```json
{
    "name": "cabinet",
    "type": "dm_cabinet",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_cabinet",
    "properties": {
        "object_name": "TestCabinet789",
        "r_object_type": "dm_cabinet",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-20T14:14:44.000+00:00",
        "r_modify_date": "2020-07-20T14:14:44.000+00:00",
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
        "i_folder_id": null,
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
        "i_cabinet_id": "0c0277b68004dbc6",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0c0277b68004dbc6",
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
            "/TestCabinet789"
        ],
        "i_ancestor_id": [
            "0c0277b68004dbc6"
        ],
        "is_private": false,
        "r_object_id": "0c0277b68004dbc6"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/folders",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/folders"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/documents",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/documents"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/objects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/objects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/child-links",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/child-links"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/relations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/relations?related-object-id=0c0277b68004dbc6&related-object-role=any"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-aspects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/aspects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permission-set",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/permission-set"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permissions",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/permissions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/attachable-lifecycles",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/lifecycles?object-id=0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-lifecycle",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/lifecycle"
        }
    ]
}
```

#### Find information about a Cabinet

To Find information about a specific Cabinet, use findcabinet and specify the object id. 
**findcabinet**
```xml
<documentum.findcabinet>
  <repo>{$ctx:repo}</repo>
  <ObjectID>{$ctx:ObjectID}</ObjectID>
</documentum.findcabinet>
```

**Properties**
* repo : The repo of the documentum.
* objectID : The Object ID of the Cabinet.

**Sample request**

Following is a sample request that can be handled by the findcabinet operation.

```json
{
 "repo":"doctest",
 "cabinateObjectID":"0c0277b68004dbc1"
}
```
**Sample response**

Given below is a sample response for the findcabinet operation.

```json
{
    "name": "cabinet",
    "type": "dm_cabinet",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_cabinet",
    "properties": {
        "object_name": "TestCabinet789",
        "r_object_type": "dm_cabinet",
        "r_creation_date": "2020-07-20T14:14:44.000+00:00",
        "r_modify_date": "2020-07-20T14:14:44.000+00:00",
        "r_modifier": "appowner",
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_archive": false,
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
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
        "i_cabinet_id": "0c0277b68004dbc6",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0c0277b68004dbc6",
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
            "/TestCabinet789"
        ],
        "i_ancestor_id": [
            "0c0277b68004dbc6"
        ],
        "is_private": false,
        "r_object_id": "0c0277b68004dbc6"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/folders",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/folders"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/documents",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/documents"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/objects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/objects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/child-links",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/child-links"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/relations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/relations?related-object-id=0c0277b68004dbc6&related-object-role=any"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-aspects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/aspects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permission-set",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/permission-set"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permissions",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/permissions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/attachable-lifecycles",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/lifecycles?object-id=0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-lifecycle",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/lifecycle"
        }
    ]
}
```


#### Deleting Cabinet

To Delete information about a specific Cabinet, use deletecabinet and specify the acl object id.

**deletecabinet**
```xml
<documentum.deletecabinet>
 <repo>{$ctx:repo}</repo>
 <ObjectID>{$ctx:ObjectID}</ObjectID>
</documentum.deletecabinet>
```
**Properties**
* repo : The repo of the documentum.
* ObjectID : The  Object ID of the Cabinet.


**Sample request**

Following is a sample request that can be handled by the deletecabinet operation.

```json
{
  "repo":"doctest",
  "cabinateObjectID":"0c0277b68004dbc1"
}
```
**Sample response**

204 will returned if the Cabinet is successfully deleted.



#### Getting Cabinets of the Documentum
To get Cabinets.  This operation returns a JSON representation of the cabinets.

**getcabinets**
```xml
<documentum.getcabinets>
  <repo>{$ctx:repo}</repo>
</documentum.getcabinets>
```
**Properties**
* repo : The repo of the documentum.

**Sample request**

Following is a sample request that can be handled by the getcabinets operation.

```json
{
  "repo":"doctest"
}
```
**Sample response**

Given below is a sample response for the getcabinets operation.

```json
{
    "name": "cabinet",
    "type": "dm_cabinet",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_cabinet",
    "properties": {
        "object_name": "TestCabinet789",
        "r_object_type": "dm_cabinet",
        "r_creation_date": "2020-07-20T14:14:44.000+00:00",
        "r_modify_date": "2020-07-20T14:14:44.000+00:00",
        "r_modifier": "appowner",
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_archive": false,
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
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
        "i_cabinet_id": "0c0277b68004dbc6",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 5,
        "world_permit": 4,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0c0277b68004dbc6",
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
            "/TestCabinet789"
        ],
        "i_ancestor_id": [
            "0c0277b68004dbc6"
        ],
        "is_private": false,
        "r_object_id": "0c0277b68004dbc6"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/folders",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/folders"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/documents",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/documents"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/objects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/objects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/child-links",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b68004dbc6/child-links"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/relations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/relations?related-object-id=0c0277b68004dbc6&related-object-role=any"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-aspects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/aspects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permission-set",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/permission-set"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permissions",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/permissions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/attachable-lifecycles",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/lifecycles?object-id=0c0277b68004dbc6"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-lifecycle",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/0c0277b68004dbc6/lifecycle"
        }
    ]
}
```

