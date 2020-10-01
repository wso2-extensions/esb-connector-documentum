# Working with Sys Object of Documentum

[[Overview]](#overview)  [[Operation details]](#operation-details)  [[Sample configuration]](#sample-configuration)

### Overview 

The following operations are available for working with Sys Object.Click an operation name to see details on how to use it.
For a sample proxy service that illustrates how to work with Sys Object, see [Sample configuration](#sample-configuration).


| Operation        | Description |
| ------------- |-------------|
| [findsysobject](#documentum_findsysobject) | finding the Sys Object of the Document. |


### Operation details

Following is more information about these operations.

#### Finding Sys Object of the Document
To Finding information about Sys Object of the Document, use findsysobject and specify the Object ID. 

**findsysobject**
```xml
<documentum.findsysobject>
  <repo>{$ctx:repo}</repo>
  <objectID>{$ctx:ObjectID}</objectID>
</documentum.findsysobject>
```
**Properties**
* repo : The repo of the documentum.
* objectID : The Object ID of the Document.


**Sample request**

Following is a sample request that can be handled by the findsysobject operation.

```json
{
  "repo":"doctest",
  "objectID":"090277b680047c89"
}
```
**Sample response**

Given below is a sample response for the findsysobject operation.

```json
{
    "name": "object",
    "type": "dm_document",
    "definition": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/types/dm_document",
    "properties": {
        "object_name": "Samplefile",
        "r_object_type": "dm_document",
        "r_creation_date": "2020-07-17T17:51:38.000+00:00",
        "r_modify_date": "2020-07-17T17:53:02.000+00:00",
        "r_modifier": "appowner",
        "r_access_date": "2020-07-20T06:45:52.000+00:00",
        "a_is_hidden": false,
        "i_is_deleted": false,
        "a_archive": false,
        "a_link_resolved": false,
        "i_reference_cnt": 1,
        "i_has_folder": true,
        "i_folder_id": [
            "0b0277b6800584f3"
        ],
        "r_link_cnt": 0,
        "r_link_high_cnt": 0,
        "r_assembled_from_id": "0000000000000000",
        "r_frzn_assembly_cnt": 0,
        "r_has_frzn_assembly": false,
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
        "r_full_content_size": 52493.0,
        "a_is_signed": false,
        "i_partition": 0,
        "i_is_replica": false,
        "i_vstamp": 2,
        "r_object_id": "090277b68005b444"
    },
    "links": [
        {
            "rel": "self",
            "href": "http://172.28.254.169:8080/documentum-rest-web-16.7.0000.0076/repositories/doctest/objects/090277b68005b444/"
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




