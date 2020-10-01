# Working with ACLs in Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with acls.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with acls, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [createacl](#documentum-createacl)    | Creating ACL of the Documentum. |
| [applyacl](#documentum-applyacl)      | Applying ACL on the Documentum.|
| [deleteacl](#documentum-deleteacl)    | Deleting ACL of the Documentum. |
| [getallacls](#documentum-getallacls)  | Getting the all the acls from the Documentum. |


### Operation details

Following is more information about these operations.

#### documentum-createacl
To Create information about a specific ACL, use createacl and specify the object name. This operation returns a JSON representation of the entire ACL, Object Name, Description, OwnerName and more.

**createacl**
```xml
<documentum.createacl>
  <repo>{$ctx:repo}</repo>
  <objname>{$ctx:objectName}</objname>
  <desc>{$ctx:description}</desc>
  <owner>{$ctx:ownerName}</owner>
</documentum.createacl>
```
**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |
| objectName    | The Object Name of the ACL | Yes |
| description    | The Description of the ACL | Optional |
| ownerName    | The Owner Name  of the ACL | Yes |


**Sample request**

Following is a sample request that can be handled by the create ACL operation.

```json
{
	"repo":"doctest",
	"object_name":"TestACL24",
	"description": "TestaclSample24",
	"owner_name": "appowner"
}
```
**Sample response**

Given below is a sample response for the createacl operation.

```json
{
    "name": "acl",
    "type": "dm_acl",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_acl",
    "properties": {
        "object_name": "TestACL24",
        "description": "TestaclSample24",
        "owner_name": "appowner",
        "r_is_internal": false,
        "r_accessor_name": [
            "dm_world",
            "dm_owner"
        ],
        "r_accessor_permit": [
            3,
            7
        ],
        "r_accessor_xpermit": [
            0,
            0
        ],
        "r_is_group": [
            false,
            false
        ],
        "globally_managed": false,
        "acl_class": 0,
        "r_has_events": false,
        "r_permit_type": [
            0,
            0
        ],
        "r_application_permit": [
            "",
            ""
        ],
        "i_has_required_groups": false,
        "i_has_required_group_set": false,
        "i_has_access_restrictions": false,
        "r_template_id": "0000000000000000",
        "r_alias_set_id": "0000000000000000",
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 0,
        "r_object_id": "450277b680001d92"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680001d92"
        }
    ]
}
```

#### documentum-applyacl

To Apply information about a specific ACL, use applyacl and specify the object id. This operation returns a JSON representation of the entire ACL, Object ID, ACL Name and more.

**applyacl**
```xml
<documentum.applyacl>
   <repo>{$ctx:repo}</repo>
   <objectID>{$ctx:objectID}</objectID>
   <aclname>{$ctx:aclname}</aclname>
</documentum.applyacl>
```

**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |
| objectID    | The Object ID of the ACL | Yes |
| aclname    | The The Name  of the ACL | Yes |

**Sample request**

Following is a sample request that can be handled by the applyacl operation.

```json
{
	"repo":"doctest",
	"objectID":"0b0277b68004e7de",
	"acl_name":"TestACL24"
}
```
**Sample response**

Given below is a sample response for the applyacl operation.

```json
{
    "name": "object",
    "type": "dm_folder",
    "definition": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_folder",
    "properties": {
        "object_name": "TestACL24",
        "r_object_type": "dm_folder",
        "title": "",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-07-02T06:28:39.000+00:00",
        "r_modify_date": "2020-07-02T06:28:39.000+00:00",
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
            "0c0277b68002952c"
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
        "i_cabinet_id": "0c0277b68002952c",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 1,
        "world_permit": 3,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "0b0277b68004e7de",
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
        "acl_name": "TestACL24",
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
        "i_vstamp": 1,
        "r_folder_path": [
            "/WSO2 Connector/TestACL24"
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


#### documentum-deleteacl

To Delete information about a specific ACL, use deleteacl and specify the acl object id.

**deleteacl**
```xml
<documentum.deleteacl>
  <repo>{$ctx:repo}</repo>
  <aclObjID>{$ctx:aclObjID}</aclObjID>
</documentum.deleteacl>
```
**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |
| aclObjectID    | The Object ID of the ACL | Yes |

**Sample request**

Following is a sample request that can be handled by the deleteacl operation.

```json
{
 "repo":"doctest",
 "aclObjectID":"450277b680001d92"
}
```
**Sample response**

204 will be returned if the acl is successfully deleted.



#### documentum-getallacls
To get all the acls .  This operation returns a JSON representation of the acls, including their acl name, ID, and more information.

**getallacls**
```xml
 <documentum.getallacls>
    <repo>{$ctx:repo}</repo>
 </documentum.getallacls>
```
**Properties**

| Parameters    |  Description |  Required  |
|---------------|--------------|------------|
| repo          | The repo of the documentum | Yes |

**Sample request**

Following is a sample request that can be handled by the getallacls operation.

```json
{
  "repo":"doctest"
}
```
**Sample response**

Given below is a sample response for the getallacls operation.

```json
{
    "id": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/",
    "title": "ACLs",
    "author": [
        {
            "name": "Open Text Documentum"
        }
    ],
    "updated": "2020-07-20T04:57:02.815+00:00",
    "page": 1,
    "items-per-page": 100,
    "links": [
        {
            "rel": "self",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/"
        },
        {
            "rel": "next",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/?items-per-page=100&page=2"
        },
        {
            "rel": "first",
            "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/?items-per-page=100&page=1"
        }
    ],
    "entries": [
        {
            "id": "450277b680000100",
            "title": "dm_450277b680000100",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000100"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000100"
            }
        },
        {
            "id": "450277b680000101",
            "title": "dm_450277b680000101",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000101"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://134.27.231.192:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000101"
            }
        }
        
    ]
}

```

