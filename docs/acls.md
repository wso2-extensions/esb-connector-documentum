# Working with ACLs in Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with acls.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with acls, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [createacl](#documentum_createacl)    | Creating ACL of the Documentum. |
| [applyacl](#documentum_applyacl)      | Applying ACL on the Documentum.|
| [deleteacl](#documentum_deleteacl)    | Deleting ACL of the Documentum. |
| [getallacls](#documentum_getallacls)  | Getting the all the acls from the Documentum. |


### Operation details

Following is more information about these operations.

#### Create information about a ACL
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
* repo : The repo of the documentum.
* objectName : The Object Name of the ACL.
* description : The Description of the ACL.
* ownerName : The Owner Name  of the ACL.

**Sample request**

Following is a sample request that can be handled by the create ACL operation.

```json
{
  "repo":"doctest",
  "object_name":"Testacl8",
  "description": "TestaclJul8",
  "owner_name": "appowner"
}
```
**Sample response**

Given below is a sample response for the createacl operation.

```json
{
    "name": "acl",
    "type": "dm_acl",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_acl",
    "properties": {
        "object_name": "testACL032",
        "description": "testACL032",
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
        "r_object_id": "450277b680001d91"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680001d91"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/associations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680001d91/associations"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680001d91"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680001d91"
        }
    ]
}
```

#### Apply information about a ACL

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
* repo : The repo of the documentum.
* objectID : The Object ID of the ACL.
* aclname : The Name  of the ACL.

**Sample request**

Following is a sample request that can be handled by the applyacl operation.

```json
{
   "repo":"doctest",
   "objectID":"0b0277b680043127",
   "acl_name":"Testacl8"
}
```
**Sample response**

Given below is a sample response for the applyacl operation.

```json
{
    "name": "object",
    "type": "dm_document",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_document",
    "properties": {
        "object_name": "Newe",
        "r_object_type": "dm_document",
        "title": "Word 2007 / 2010 Document",
        "subject": "",
        "authors": null,
        "keywords": null,
        "a_application_type": "",
        "a_status": "",
        "r_creation_date": "2020-06-24T08:25:33.000+00:00",
        "r_modify_date": "2020-06-24T08:25:33.000+00:00",
        "r_modifier": "appowner",
        "r_access_date": null,
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_retention_date": null,
        "a_archive": false,
        "a_compound_architecture": "",
        "a_link_resolved": false,
        "i_reference_cnt": 2,
        "i_has_folder": true,
        "i_folder_id": [
            "0b0277b680043123",
            "0c0277b680041e73"
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
        "i_contents_id": "060277b68003dae8",
        "a_content_type": "msw12",
        "r_page_cnt": 1,
        "r_content_size": 11280,
        "a_full_text": true,
        "a_storage_type": "filestore_01",
        "i_cabinet_id": "0c0277b680000104",
        "owner_name": "appowner",
        "owner_permit": 7,
        "group_name": "docu",
        "group_permit": 1,
        "world_permit": 3,
        "i_antecedent_id": "0000000000000000",
        "i_chronicle_id": "090277b680047c88",
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
        "acl_name": "testACL032",
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
        "r_full_content_size": 11280.0,
        "a_extended_properties": null,
        "a_is_signed": false,
        "a_last_review_date": null,
        "i_retain_until": null,
        "r_aspect_name": null,
        "i_retainer_id": null,
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 5,
        "r_object_id": "090277b680047c88"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88"
        },
        {
            "rel": "edit",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/delete",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88"
        },
        {
            "rel": "canonical",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/documents/090277b680047c88"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/parent-links",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/parent-links"
        },
        {
            "rel": "parent",
            "title": "0b0277b680043123",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0b0277b680043123"
        },
        {
            "rel": "parent",
            "title": "0c0277b680041e73",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/folders/0c0277b680041e73"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/cabinet",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/cabinets/0c0277b680000104"
        },
        {
            "rel": "contents",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/contents"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/primary-content",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/contents/content"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/checkout",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/lock"
        },
        {
            "rel": "version-history",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/versions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/current-version",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/versions/current"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/virtual-document-conversion",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/vd-nodes"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/relations",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/relations?related-object-id=090277b680047c88&related-object-role=any"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-aspects",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/aspects"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permission-set",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/permission-set"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/permissions",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/permissions"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/comments",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/comments"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/attachable-lifecycles",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/lifecycles?object-id=090277b680047c88"
        },
        {
            "rel": "http://identifiers.emc.com/linkrel/object-lifecycle",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b680047c88/lifecycle"
        }
    ]
}
```


#### Deleting ACL

To Delete information about a specific ACL, use deleteacl and specify the acl object id.

**deleteacl**
```xml
<documentum.deleteacl>
  <repo>{$ctx:repo}</repo>
  <aclObjID>{$ctx:aclObjID}</aclObjID>
</documentum.deleteacl>
```
**Properties**
* repo : The repo of the acl documentum.
* aclObjectID : The  Object ID of the ACL.


**Sample request**

Following is a sample request that can be handled by the deleteacl operation.

```json
{
 "repo":"doctest",
 "aclObjectID":"450277b680001d42"
}
```
**Sample response**

204 will returned if the acl is successfully deleted.



#### Getting All acls of the Documentum
To get all the acls .  This operation returns a JSON representation of the acls, including their acl name, ID, and more information.

**getallacls**
```xml
 <documentum.getallacls>
    <repo>{$ctx:repo}</repo>
 </documentum.getallacls>
```
**Properties**
* repo : The repo of the acl documentum.

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
    "id": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/",
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
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/"
        },
        {
            "rel": "next",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/?items-per-page=100&page=2"
        },
        {
            "rel": "first",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/?items-per-page=100&page=1"
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
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000100"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000100"
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
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000101"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000101"
            }
        },
        {
            "id": "450277b680000102",
            "title": "dm_450277b680000102",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000102"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000102"
            }
        },
        {
            "id": "450277b680000103",
            "title": "dm_450277b680000103",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000103"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000103"
            }
        },
        {
            "id": "450277b680000104",
            "title": "dm_450277b680000104",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000104"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000104"
            }
        },
        {
            "id": "450277b680000105",
            "title": "dm_450277b680000105",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000105"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000105"
            }
        },
        {
            "id": "450277b680000106",
            "title": "dm_450277b680000106",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000106"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000106"
            }
        },
        {
            "id": "450277b680000107",
            "title": "dm_450277b680000107",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000107"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000107"
            }
        },
        {
            "id": "450277b680000108",
            "title": "dm_450277b680000108",
            "updated": "2020-07-20T04:57:02.879+00:00",
            "published": "2020-07-20T04:57:02.879+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000108"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000108"
            }
        },
        {
            "id": "450277b680000109",
            "title": "dm_450277b680000109",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000109"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000109"
            }
        },
        {
            "id": "450277b68000010a",
            "title": "dm_450277b68000010a",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010a"
            }
        },
        {
            "id": "450277b68000010b",
            "title": "dm_450277b68000010b",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010b"
            }
        },
        {
            "id": "450277b68000010c",
            "title": "dm_450277b68000010c",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010c"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010c"
            }
        },
        {
            "id": "450277b68000010d",
            "title": "dm_450277b68000010d",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010d"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010d"
            }
        },
        {
            "id": "450277b68000010e",
            "title": "dm_450277b68000010e",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010e"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010e"
            }
        },
        {
            "id": "450277b68000010f",
            "title": "dm_450277b68000010f",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010f"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000010f"
            }
        },
        {
            "id": "450277b680000110",
            "title": "dm_450277b680000110",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000110"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000110"
            }
        },
        {
            "id": "450277b680000111",
            "title": "dm_450277b680000111",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000111"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000111"
            }
        },
        {
            "id": "450277b680000112",
            "title": "dm_450277b680000112",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000112"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000112"
            }
        },
        {
            "id": "450277b680000113",
            "title": "dm_450277b680000113",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000113"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000113"
            }
        },
        {
            "id": "450277b680000114",
            "title": "dm_450277b680000114",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000114"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000114"
            }
        },
        {
            "id": "450277b680000115",
            "title": "dm_450277b680000115",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000115"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000115"
            }
        },
        {
            "id": "450277b680000116",
            "title": "dm_450277b680000116",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000116"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000116"
            }
        },
        {
            "id": "450277b680000117",
            "title": "dm_450277b680000117",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000117"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000117"
            }
        },
        {
            "id": "450277b680000118",
            "title": "dm_450277b680000118",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000118"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000118"
            }
        },
        {
            "id": "450277b680000119",
            "title": "BOF_acl",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000119"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000119"
            }
        },
        {
            "id": "450277b68000011a",
            "title": "BOF_acl2",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000011a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000011a"
            }
        },
        {
            "id": "450277b68000011b",
            "title": "dm_acl_sysadmin",
            "updated": "2020-07-20T04:57:02.880+00:00",
            "published": "2020-07-20T04:57:02.880+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000011b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000011b"
            }
        },
        {
            "id": "450277b680000123",
            "title": "dm_450277b680000123",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000123"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000123"
            }
        },
        {
            "id": "450277b680000124",
            "title": "dm_450277b680000124",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000124"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000124"
            }
        },
        {
            "id": "450277b680000125",
            "title": "dm_450277b680000125",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000125"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000125"
            }
        },
        {
            "id": "450277b680000126",
            "title": "dm_450277b680000126",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000126"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000126"
            }
        },
        {
            "id": "450277b680000127",
            "title": "dm_450277b680000127",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000127"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000127"
            }
        },
        {
            "id": "450277b680000128",
            "title": "dm_450277b680000128",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000128"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000128"
            }
        },
        {
            "id": "450277b680000129",
            "title": "dm_450277b680000129",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000129"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000129"
            }
        },
        {
            "id": "450277b68000012a",
            "title": "replica_acl_default",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000012a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000012a"
            }
        },
        {
            "id": "450277b680000134",
            "title": "dm_450277b680000134",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000134"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000134"
            }
        },
        {
            "id": "450277b680000135",
            "title": "dm_450277b680000135",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000135"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000135"
            }
        },
        {
            "id": "450277b680000136",
            "title": "desktop_client_acl1",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000136"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000136"
            }
        },
        {
            "id": "450277b680000140",
            "title": "dm_450277b680000140",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000140"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000140"
            }
        },
        {
            "id": "450277b680000141",
            "title": "dm_450277b680000141",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000141"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000141"
            }
        },
        {
            "id": "450277b680000142",
            "title": "dm_450277b680000142",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000142"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000142"
            }
        },
        {
            "id": "450277b680000143",
            "title": "dm_450277b680000143",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000143"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000143"
            }
        },
        {
            "id": "450277b680000144",
            "title": "dm_450277b680000144",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000144"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000144"
            }
        },
        {
            "id": "450277b680000145",
            "title": "dm_450277b680000145",
            "updated": "2020-07-20T04:57:02.881+00:00",
            "published": "2020-07-20T04:57:02.881+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000145"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000145"
            }
        },
        {
            "id": "450277b680000146",
            "title": "dm_450277b680000146",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000146"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000146"
            }
        },
        {
            "id": "450277b680000147",
            "title": "dm_450277b680000147",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000147"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000147"
            }
        },
        {
            "id": "450277b680000148",
            "title": "dm_450277b680000148",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000148"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000148"
            }
        },
        {
            "id": "450277b680000149",
            "title": "dm_450277b680000149",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000149"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000149"
            }
        },
        {
            "id": "450277b68000014a",
            "title": "dm_450277b68000014a",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014a"
            }
        },
        {
            "id": "450277b68000014b",
            "title": "dm_450277b68000014b",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014b"
            }
        },
        {
            "id": "450277b68000014c",
            "title": "dm_450277b68000014c",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014c"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014c"
            }
        },
        {
            "id": "450277b68000014d",
            "title": "dm_450277b68000014d",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014d"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014d"
            }
        },
        {
            "id": "450277b68000014e",
            "title": "dm_450277b68000014e",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014e"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014e"
            }
        },
        {
            "id": "450277b68000014f",
            "title": "dm_450277b68000014f",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014f"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000014f"
            }
        },
        {
            "id": "450277b680000150",
            "title": "dm_450277b680000150",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000150"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000150"
            }
        },
        {
            "id": "450277b680000151",
            "title": "dm_450277b680000151",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000151"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000151"
            }
        },
        {
            "id": "450277b680000152",
            "title": "dm_450277b680000152",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000152"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000152"
            }
        },
        {
            "id": "450277b680000153",
            "title": "dm_450277b680000153",
            "updated": "2020-07-20T04:57:02.882+00:00",
            "published": "2020-07-20T04:57:02.882+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000153"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000153"
            }
        },
        {
            "id": "450277b680000154",
            "title": "dm_450277b680000154",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000154"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000154"
            }
        },
        {
            "id": "450277b680000155",
            "title": "dm_450277b680000155",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000155"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000155"
            }
        },
        {
            "id": "450277b680000156",
            "title": "dm_450277b680000156",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000156"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000156"
            }
        },
        {
            "id": "450277b680000157",
            "title": "dm_450277b680000157",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000157"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000157"
            }
        },
        {
            "id": "450277b680000158",
            "title": "dm_450277b680000158",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000158"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000158"
            }
        },
        {
            "id": "450277b680000159",
            "title": "dm_450277b680000159",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000159"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000159"
            }
        },
        {
            "id": "450277b68000015a",
            "title": "dm_450277b68000015a",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015a"
            }
        },
        {
            "id": "450277b68000015b",
            "title": "dm_450277b68000015b",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015b"
            }
        },
        {
            "id": "450277b68000015c",
            "title": "dm_450277b68000015c",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015c"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015c"
            }
        },
        {
            "id": "450277b68000015d",
            "title": "dm_450277b68000015d",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015d"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015d"
            }
        },
        {
            "id": "450277b68000015e",
            "title": "dm_450277b68000015e",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015e"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015e"
            }
        },
        {
            "id": "450277b68000015f",
            "title": "dm_450277b68000015f",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015f"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000015f"
            }
        },
        {
            "id": "450277b680000160",
            "title": "dm_450277b680000160",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000160"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000160"
            }
        },
        {
            "id": "450277b680000161",
            "title": "dm_450277b680000161",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000161"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000161"
            }
        },
        {
            "id": "450277b680000162",
            "title": "dm_450277b680000162",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000162"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000162"
            }
        },
        {
            "id": "450277b680000163",
            "title": "dm_450277b680000163",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000163"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000163"
            }
        },
        {
            "id": "450277b680000164",
            "title": "dm_450277b680000164",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000164"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000164"
            }
        },
        {
            "id": "450277b680000165",
            "title": "dm_450277b680000165",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000165"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000165"
            }
        },
        {
            "id": "450277b680000166",
            "title": "dm_450277b680000166",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000166"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000166"
            }
        },
        {
            "id": "450277b680000167",
            "title": "dm_450277b680000167",
            "updated": "2020-07-20T04:57:02.883+00:00",
            "published": "2020-07-20T04:57:02.883+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000167"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000167"
            }
        },
        {
            "id": "450277b680000168",
            "title": "dm_450277b680000168",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000168"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000168"
            }
        },
        {
            "id": "450277b680000169",
            "title": "dm_450277b680000169",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000169"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000169"
            }
        },
        {
            "id": "450277b68000016a",
            "title": "dm_450277b68000016a",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016a"
            }
        },
        {
            "id": "450277b68000016b",
            "title": "dm_450277b68000016b",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016b"
            }
        },
        {
            "id": "450277b68000016c",
            "title": "dm_450277b68000016c",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016c"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016c"
            }
        },
        {
            "id": "450277b68000016d",
            "title": "dm_450277b68000016d",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016d"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016d"
            }
        },
        {
            "id": "450277b68000016e",
            "title": "dm_450277b68000016e",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016e"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016e"
            }
        },
        {
            "id": "450277b68000016f",
            "title": "dm_450277b68000016f",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016f"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000016f"
            }
        },
        {
            "id": "450277b680000170",
            "title": "dm_450277b680000170",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000170"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000170"
            }
        },
        {
            "id": "450277b680000171",
            "title": "dm_450277b680000171",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000171"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000171"
            }
        },
        {
            "id": "450277b680000172",
            "title": "dm_450277b680000172",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000172"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000172"
            }
        },
        {
            "id": "450277b680000173",
            "title": "dm_450277b680000173",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000173"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000173"
            }
        },
        {
            "id": "450277b680000174",
            "title": "dm_450277b680000174",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000174"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000174"
            }
        },
        {
            "id": "450277b680000175",
            "title": "dm_450277b680000175",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000175"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000175"
            }
        },
        {
            "id": "450277b680000176",
            "title": "dm_450277b680000176",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000176"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000176"
            }
        },
        {
            "id": "450277b680000177",
            "title": "dm_450277b680000177",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000177"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000177"
            }
        },
        {
            "id": "450277b680000178",
            "title": "dm_450277b680000178",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000178"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000178"
            }
        },
        {
            "id": "450277b680000179",
            "title": "dm_450277b680000179",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000179"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b680000179"
            }
        },
        {
            "id": "450277b68000017a",
            "title": "dm_450277b68000017a",
            "updated": "2020-07-20T04:57:02.884+00:00",
            "published": "2020-07-20T04:57:02.884+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000017a"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000017a"
            }
        },
        {
            "id": "450277b68000017b",
            "title": "dm_450277b68000017b",
            "updated": "2020-07-20T04:57:02.885+00:00",
            "published": "2020-07-20T04:57:02.885+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000017b"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000017b"
            }
        },
        {
            "id": "450277b68000017c",
            "title": "dm_450277b68000017c",
            "updated": "2020-07-20T04:57:02.885+00:00",
            "published": "2020-07-20T04:57:02.885+00:00",
            "links": [
                {
                    "rel": "edit",
                    "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000017c"
                }
            ],
            "content": {
                "type": "application/vnd.emc.documentum+json",
                "src": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/acls/450277b68000017c"
            }
        }
    ]
}
```

