### /v1/visualization/customQuery/
payload:
```
{
  "index": "sp-raym-1",
  "discover": true,
  "query": {
    "sort": [
      {
        "i_dont": {
          "order": "desc",
          "unmapped_type": "boolean"
        }
      },
      {
        "i_dont": {
          "order": "desc",
          "unmapped_type": "boolean"
        }
      }
    ],
    "aggs": {
      "2": {
        "date_histogram": {
          "field": "i_dont",
          "interval": "1y",
          "time_zone": "Asia/Kolkata",
          "min_doc_count": 1
        }
      }
    },
    "query": {
      "bool": {
        "must": [
          {
            "match_phrase": {
              "access_detail_write_email": {
                "query": "renz.monterola@gmail.com"
              }
            }
          }
        ],
        "filter": [
          {
            "bool": {
              "filter": []
            }
          }
        ],
        "should": [],
        "must_not": []
      }
    },
    "size": 1000
  }
}
```
response: (cache is still pending to get results)
```
{
  "msg": "Creating cache",
  "data": {},
  "aggr": [],
  "cache_pending": true
}
```
payload 2: (If cache_pending, it retries)
```
{
  "index": "sp-raym-1",
  "discover": true,
  "query": {
    "sort": [
      {
        "i_dont": {
          "order": "desc",
          "unmapped_type": "boolean"
        }
      },
      {
        "i_dont": {
          "order": "desc",
          "unmapped_type": "boolean"
        }
      }
    ],
    "aggs": {
      "2": {
        "date_histogram": {
          "field": "i_dont",
          "interval": "1y",
          "time_zone": "Asia/Kolkata",
          "min_doc_count": 1
        }
      }
    },
    "query": {
      "bool": {
        "must": [
          {
            "match_phrase": {
              "access_detail_write_email": {
                "query": "renz.monterola@gmail.com"
              }
            }
          }
        ],
        "filter": [
          {
            "bool": {
              "filter": []
            }
          }
        ],
        "should": [],
        "must_not": []
      }
    },
    "size": 1000
  }
}
```
response:
```
{
  "status": 1,
  "data": {
    "data": {
      "total": 2,
      "max_score": null,
      "hits": [
        {
          "_index": "m_cm2kffsooung05mcjk6g_1703233471803",
          "_type": "_doc",
          "_id": "ON2gkIwB2EoPkFylibMx",
          "_score": null,
          "_source": {
            "schema": "sharepoint_document",
            "content_skipped": false,
            "access_given_through_fullcontrol": [
              ""
            ],
            "extension": "xls",
            "access_given_through_read": [
              ""
            ],
            "collect_content": false,
            "downloadUrl": "https://35thyb.sharepoint.com/_layouts/15/download.aspx?UniqueId=258ef2f8-9222-479c-8998-232be46bb851&Translate=false&tempauth=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvMzV0aHliLnNoYXJlcG9pbnQuY29tQDY1NzI2ZjFjLTIyMTYtNDMyMC1hNDc0LThjZmU1OTRlNzg4ZSIsImlzcyI6IjAwMDAwMDAzLTAwMDAtMGZmMS1jZTAwLTAwMDAwMDAwMDAwMCIsIm5iZiI6IjE3MDMyMzM0ODUiLCJleHAiOiIxNzAzMjM3MDg1IiwiZW5kcG9pbnR1cmwiOiIxcXdIVmZpTTIzeHp0WnlaaXBvQ25ka0pKbS96Um52S0hQUkN5SVM0MU9RPSIsImVuZHBvaW50dXJsTGVuZ3RoIjoiMTE3IiwiaXNsb29wYmFjayI6IlRydWUiLCJjaWQiOiI0c3ZJYlVud3FVS3ZTZ1JyQkxDemNRPT0iLCJ2ZXIiOiJoYXNoZWRwcm9vZnRva2VuIiwic2l0ZWlkIjoiT0dZeFlUUTJNRGd0Wm1Wa1lTMDBOalUxTFRrMk16QXRNVFppT1RjMk9UVXlNR0ppIiwiYXBwX2Rpc3BsYXluYW1lIjoidGVzdCBhcHAiLCJuYW1laWQiOiI1OGI1MGQ2MS0xZDBlLTRhYzMtOGY1Yi1iZDJmZjA2ZGFjNzhANjU3MjZmMWMtMjIxNi00MzIwLWE0NzQtOGNmZTU5NGU3ODhlIiwicm9sZXMiOiJncm91cC5yZWFkIGFsbHNpdGVzLnJlYWQiLCJ0dCI6IjEiLCJpcGFkZHIiOiIyMC4xOTAuMTYzLjI5In0.V3Wu5LqqCwvpDHTSlAsVZzTFC4x9FKlpFbR7Wj7wq6Q&ApiVersion=2.0",
            "date_partition_ingested": "2023-12-22T08:24:49.197971",
            "last_modified_date": "2023-12-19T23:36:03Z",
            "last_access_date": "1970-01-01T00:00:00",
            "change_type": "",
            "redundant": false,
            "repository_type": "sharepoint",
            "path": "/Communication site/Documents",
            "access_given_through_write": [
              "Communication site Members"
            ],
            "trivial": false,
            "outdated": false,
            "record_updated": "metadata",
            "access_given_through": [
              "explicit",
              "Communication site Members"
            ],
            "parent_path": "/drives/b!CEYaj9r-VUaWMBa5dpUgu3jsGm8DgS1Mqkenvwfv0vDf4cqRuRc4S7U3P_PVpplA/root:",
            "access_detail_fullcontrol_email": [
              ""
            ],
            "content_hash": "content_hash_NA",
            "analysis_error": false,
            "create_date": "2023-12-19T23:36:03Z",
            "abandoned": false,
            "repository_name": "sp-raym",
            "explicit_permission_exists": true,
            "similarity_hash": "similarity_hash_NA",
            "item_id": "01WNC537XY6KHCKIUSTRDYTGBDFPSGXOCR",
            "resource_type": "file",
            "outdated_by_create_date": false,
            "last_modified_by": "Ray M",
            "created_by": "Ray M",
            "sharedlink": [
              {
                "permission_type": "edit",
                "permission_scope": "anonymous",
                "permission_id": "e1dec9ac-7e37-401e-bedd-8737e5a77190",
                "permission_preventsDownload": false,
                "email": [
                  "raym@35thyb.onmicrosoft.com",
                  "renz.monterola@gmail.com"
/api/v1/sharepoint/update_user_permission                ]
              }
            ],
            "explicit": [
              {
                "permission_type": "write",
                "permission_id": "e1dec9ac-7e37-401e-bedd-8737e5a77190",
                "email": "raym@35thyb.onmicrosoft.com"
              },
              {
                "permission_type": "write",
                "permission_id": "e1dec9ac-7e37-401e-bedd-8737e5a77190",
                "email": "renz.monterola@gmail.com"
              }
            ],
            "similarity_metadata_hash": "12569272775613015",
            "shared_link_exists": true,
            "site": "Communication site",
            "date_ingestion_started": "2023-12-22T08:24:31.803000",
            "access_detail_read_email": [
              ""
            ],
            "filename": "1-mb-xls.xls",
            "web_url": "https://35thyb.sharepoint.com/_layouts/15/Doc.aspx?sourcedoc=%7B258EF2F8-9222-479C-8998-232BE46BB851%7D&file=1-mb-xls.xls&action=default&mobileredirect=true",
            "size": 1071104,
            "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
            "outdated_by_last_access_date": false,
            "access_detail_write_email": [
              "renz.monterola@gmail.com",
              "raym@35thyb.onmicrosoft.com"
            ]
          },
          "sort": [
            -9223372036854776000,
            -9223372036854776000
          ]
        },
        {
          "_index": "m_cm2kffsooung05mcjk6g_1703233471803",
          "_type": "_doc",
          "_id": "Od2gkIwB2EoPkFylibNN",
          "_score": null,
          "_source": {
            "schema": "sharepoint_document",
            "content_skipped": false,
            "access_given_through_fullcontrol": [
              ""
            ],
            "extension": "bin",
            "access_given_through_read": [
              ""
            ],
            "collect_content": false,
            "downloadUrl": "https://35thyb.sharepoint.com/_layouts/15/download.aspx?UniqueId=5bbadaa9-ee62-49bb-b200-b1d9ae3d61d5&Translate=false&tempauth=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvMzV0aHliLnNoYXJlcG9pbnQuY29tQDY1NzI2ZjFjLTIyMTYtNDMyMC1hNDc0LThjZmU1OTRlNzg4ZSIsImlzcyI6IjAwMDAwMDAzLTAwMDAtMGZmMS1jZTAwLTAwMDAwMDAwMDAwMCIsIm5iZiI6IjE3MDMyMzM0ODUiLCJleHAiOiIxNzAzMjM3MDg1IiwiZW5kcG9pbnR1cmwiOiJZYTNKUXVZYVIyS3VrektxaDAvazI5bEw5YVFQRGxBYmc1VFFnTHo2ZERnPSIsImVuZHBvaW50dXJsTGVuZ3RoIjoiMTE3IiwiaXNsb29wYmFjayI6IlRydWUiLCJjaWQiOiI0c3ZJYlVud3FVS3ZTZ1JyQkxDemNRPT0iLCJ2ZXIiOiJoYXNoZWRwcm9vZnRva2VuIiwic2l0ZWlkIjoiT0dZeFlUUTJNRGd0Wm1Wa1lTMDBOalUxTFRrMk16QXRNVFppT1RjMk9UVXlNR0ppIiwiYXBwX2Rpc3BsYXluYW1lIjoidGVzdCBhcHAiLCJuYW1laWQiOiI1OGI1MGQ2MS0xZDBlLTRhYzMtOGY1Yi1iZDJmZjA2ZGFjNzhANjU3MjZmMWMtMjIxNi00MzIwLWE0NzQtOGNmZTU5NGU3ODhlIiwicm9sZXMiOiJncm91cC5yZWFkIGFsbHNpdGVzLnJlYWQiLCJ0dCI6IjEiLCJpcGFkZHIiOiIyMC4xOTAuMTYzLjI5In0.kauRWsmXeeKIC-TN2Ijj7E5c9gb-GFFAC78cIf1ST40&ApiVersion=2.0",
            "date_partition_ingested": "2023-12-22T08:24:49.226141",
            "last_modified_date": "2023-12-19T23:28:07Z",
            "last_access_date": "1970-01-01T00:00:00",
            "change_type": "",
            "redundant": false,
            "repository_type": "sharepoint",
            "path": "/Communication site/Documents",
            "access_given_through_write": [
              "Communication site Members"
            ],
            "trivial": false,
            "outdated": false,
            "record_updated": "metadata",
            "access_given_through": [
              "explicit",
              "Communication site Members"
            ],
            "parent_path": "/drives/b!CEYaj9r-VUaWMBa5dpUgu3jsGm8DgS1Mqkenvwfv0vDf4cqRuRc4S7U3P_PVpplA/root:",
            "access_detail_fullcontrol_email": [
              ""
            ],
            "content_hash": "content_hash_NA",
            "analysis_error": false,
            "create_date": "2023-12-19T23:28:07Z",
            "abandoned": false,
            "repository_name": "sp-raym",
            "explicit_permission_exists": true,
            "similarity_hash": "similarity_hash_NA",
            "item_id": "01WNC537VJ3K5FWYXOXNE3EAFR3GXD2YOV",
            "resource_type": "file",
            "outdated_by_create_date": false,
            "last_modified_by": "Ray M",
            "created_by": "Ray M",
            "sharedlink": [
              {
                "permission_type": "edit",
                "permission_scope": "anonymous",
                "permission_id": "9799c8bf-1f5f-4c9c-90cc-2c27c715ea2c",
                "permission_preventsDownload": false,
                "email": [
                  "renz.monterola@gmail.com"
                ]
              }
            ],
            "explicit": [
              {
                "permission_type": "write",
                "permission_id": "9799c8bf-1f5f-4c9c-90cc-2c27c715ea2c",
                "email": "renz.monterola@gmail.com"
              }
            ],
            "similarity_metadata_hash": "4913116747267314805",
            "shared_link_exists": true,
            "site": "Communication site",
            "date_ingestion_started": "2023-12-22T08:24:31.803000",
            "access_detail_read_email": [
              ""
            ],
            "filename": "5MB.bin",
            "web_url": "https://35thyb.sharepoint.com/Shared%20Documents/5MB.bin",
            "size": 5242880,
            "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
            "outdated_by_last_access_date": false,
            "access_detail_write_email": [
              "renz.monterola@gmail.com"
            ]
          },
          "sort": [
            -9223372036854776000,
            -9223372036854776000
          ]
        }
      ]
    },
    "total_count": 3
  },
  "cache_pending": false
}
```

### /api/v1/sharepoint/update_user_permission
payload:
```
{
  "action": "",
  "user_email": "renz.monterola@gmail.com",
  "current_role": "write",
  "new_role": "read",
  "site_id_item_map": [
    {
      "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
      "site_name": "Communication site",
      "item_ids": [
        "01WNC537XY6KHCKIUSTRDYTGBDFPSGXOCR"
      ],
      "access_given_through": [
        "Communication site Members"
      ]
    },
    {
      "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
      "site_name": "Communication site",
      "item_ids": [
        "01WNC537VJ3K5FWYXOXNE3EAFR3GXD2YOV"
      ],
      "access_given_through": [
        "Communication site Members"
      ]
    }
  ],
  "permission_item_map": {
    "01WNC537XY6KHCKIUSTRDYTGBDFPSGXOCR": "e1dec9ac-7e37-401e-bedd-8737e5a77190",
    "01WNC537VJ3K5FWYXOXNE3EAFR3GXD2YOV": "9799c8bf-1f5f-4c9c-90cc-2c27c715ea2c"
  },
  "data_source_id": "cm2jv86g705g0450tdp0"
}
```
response:
```
{
  "code": 200,
  "success": true,
  "message": "{\"user_tobe_removed_from\": [], \"user_tobe_added_to\": [\"Communication site Visitors\"]}"
}
```
After confirming action (same endpoint):
payload:
```
{
  "action": "explicit",
  "user_email": "renz.monterola@gmail.com",
  "current_role": "write",
  "new_role": "read",
  "site_id_item_map": [
    {
      "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
      "site_name": "Communication site",
      "item_ids": [
        "01WNC537XY6KHCKIUSTRDYTGBDFPSGXOCR"
      ],
      "access_given_through": [
        "Communication site Members"
      ]
    },
    {
      "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
      "site_name": "Communication site",
      "item_ids": [
        "01WNC537VJ3K5FWYXOXNE3EAFR3GXD2YOV"
      ],
      "access_given_through": [
        "Communication site Members"
      ]
    }
  ],
  "permission_item_map": {
    "01WNC537XY6KHCKIUSTRDYTGBDFPSGXOCR": "e1dec9ac-7e37-401e-bedd-8737e5a77190",
    "01WNC537VJ3K5FWYXOXNE3EAFR3GXD2YOV": "9799c8bf-1f5f-4c9c-90cc-2c27c715ea2c"
  },
  "data_source_id": "cm2jv86g705g0450tdp0"
}
```
response:
```
{
  "code": 200,
  "success": true,
  "message": "{\"user_tobe_removed_from\": [], \"user_tobe_added_to\": [\"Communication site Visitors\"]}"
}
```
