Create simple classifier
![[Screenshot from 2023-11-14 21-25-32.png]]
```
POST /api/v1/queries
Payload 
{
  "rank": 0,
  "classification_json": {
    "mode": "contextual",
    "indexList": [
      0,
      1,
      0
    ]
  },
  "classification_query_json": {
    "condition": "and",
    "rules": [
      {
        "field": "classification_label",
        "operator": "is null",
        "value": null
      },
      {
        "condition": "or",
        "rules": []
      }
    ]
  },
  "classification_query": "SPE - Restricted - Financials - Executive Compensation",
  "field": "classification_label",
  "value": "SPE - Restricted - Financials - Executive Compensation",
  "index_aliases": [
    "gdrive1-access1"
  ],
  "owner_id": 2,
  "overwrite_existing": false
}

Response
{
  "id": "cl9ncb597qpg04uqgghg",
  "rank": 0,
  "classification_json": {
    "mode": "contextual",
    "indexList": [
      0,
      1,
      0
    ]
  },
  "classification_query_json": {
    "condition": "and",
    "rules": [
      {
        "field": "classification_label",
        "operator": "is null",
        "value": null
      },
      {
        "condition": "or",
        "rules": []
      }
    ]
  },
  "classification_query": "SPE - Restricted - Financials - Executive Compensation",
  "field": "classification_label",
  "value": "SPE - Restricted - Financials - Executive Compensation",
  "overwrite_existing": false,
  "dashboard_filter": null,
  "from_dashboard": false,
  "status": "pending",
  "index_aliases": [
    "gdrive1-access1"
  ],
  "owner_id": 2,
  "created_at": "2023-11-14T13:29:16Z",
  "updated_at": "2023-11-14T13:29:16Z",
  "last_executed_at": null,
  "failure_reason": null,
  "auto_classification": true
}
```

```
PUT /api/v1/classifications
payload:
{
  "data": [
    {
      "id": "cflq1rg6ijj004mjqqc0",
      "name": "Restricted",
      "description": null,
      "classifier_info": null,
      "status": "active",
      "priority": null,
      "children": [
        {
          "id": "cflq2bg6ijj004mjqqd0",
          "name": "BoD",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 1,
          "classifier_info": "{\"title\":\"Restricted - BoD\",\"description\":\"Description: Classification of BoD\",\"selectedAliases\":[{\"id\":\"bb-users-access1\",\"alias\":\"bb-users-access1\"},{\"id\":\"gdrive1-access1\",\"alias\":\"gdrive1-access1\"}],\"fields\":[{\"name\":\"extension\",\"terms\":[]}],\"overWriteClassifier\":false,\"autoClassify\":true,\"indexList\":[0,0],\"status\":{\"executedPending\":false,\"executedSuccess\":false,\"executedError\":false,\"saved\":true},\"classifierId\":\"cl94q9i7ul0g04iej5i0\"}"
        },
        {
          "id": "cflq2g86ijj004mjqqe0",
          "name": "Financials",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrm0",
              "name": "Executive Compensation",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 3,
              "classifier_info": "{\"title\":\"Restricted - Financials - Executive Compensation\",\"description\":\"Description: Classification of Executive Compensation\",\"selectedAliases\":[{\"id\":\"gdrive1-access1\",\"alias\":\"gdrive1-access1\"}],\"fields\":[{\"name\":\"extension\",\"terms\":[]}],\"overWriteClassifier\":false,\"autoClassify\":true,\"indexList\":[0,1,0],\"status\":{\"executedPending\":false,\"executedSuccess\":false,\"executedError\":false,\"saved\":true},\"classifierId\":\"cl9ncb597qpg04uqgghg\"}"
            }
          ],
          "owner_id": null,
          "priority": 2,
          "classifier_info": null
        },
        {
          "id": "cflq2k86ijj004mjqqf0",
          "name": "IP (Critical)",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrmg",
              "name": "R&D",
              "description": null,
              "status": "active",
              "children": [
                {
                  "id": "cflq9586ijj00aqkhrn0",
                  "name": "Firmware",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 6,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhrng",
                  "name": "Formula",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 7,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhro0",
                  "name": "Hardware",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 8,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhrog",
                  "name": "Software",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 9,
                  "classifier_info": null
                }
              ],
              "owner_id": 2,
              "priority": 5,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 4,
          "classifier_info": null
        },
        {
          "id": "cflq2mo6ijj0044fdb0g",
          "name": "Legal",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 10,
          "classifier_info": null
        },
        {
          "id": "cflq2p06ijj0044fdb1g",
          "name": "M&A",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 11,
          "classifier_info": null
        }
      ]
    },
    {
      "id": "cflq1vg6ijj004eesar0",
      "name": "Confidential",
      "description": null,
      "classifier_info": null,
      "status": "active",
      "priority": null,
      "children": [
        {
          "id": "cflq3206ijj004mjqqg0",
          "name": "Agreements & Contracts",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrp0",
              "name": "Employment",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 13,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 12,
          "classifier_info": null
        },
        {
          "id": "cflq3406ijj004mjqqh0",
          "name": "BoD",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 14,
          "classifier_info": null
        },
        {
          "id": "cflq3ag6ijj004eesas0",
          "name": "Business Plan & Strategy",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 15,
          "classifier_info": null
        },
        {
          "id": "cflq3co6ijj0044fdb2g",
          "name": "Financials",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrpg",
              "name": "Payroll (Retain 10Yrs After Create)",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 17,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrq0",
              "name": "Sales",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 18,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrqg",
              "name": "Tax",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 19,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 16,
          "classifier_info": null
        },
        {
          "id": "cflq3fg6ijj003q3rg10",
          "name": "HR",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrr0",
              "name": "Complaints & Incidents",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 21,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrrg",
              "name": "Employment Agreement",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 22,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrs0",
              "name": "Offer Letter",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 23,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrsg",
              "name": "Performance Reviews",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 24,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrt0",
              "name": "Separation Agreement",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 25,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 20,
          "classifier_info": null
        },
        {
          "id": "cflq6cg6ijj004eesat0",
          "name": "Insurance & Claims",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrtg",
              "name": "Cyber",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 27,
              "classifier_info": null
            },
            {
              "id": "cfn2mblp4brg04k9pfog",
              "name": "E&O",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 31,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhru0",
              "name": "Property",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 28,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrug",
              "name": "Umbrella",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 29,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhrv0",
              "name": "Workers Comp",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 30,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 26,
          "classifier_info": null
        },
        {
          "id": "cflq6i06ijj004mjqqi0",
          "name": "IP (Non Critical)",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhrvg",
              "name": "Patent Application",
              "description": null,
              "status": "active",
              "children": [
                {
                  "id": "cflq9586ijj00aqkhs00",
                  "name": "Firmware",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 34,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhs0g",
                  "name": "Formula",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 35,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhs10",
                  "name": "Hardware",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 36,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhs1g",
                  "name": "Software",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 37,
                  "classifier_info": null
                }
              ],
              "owner_id": 2,
              "priority": 33,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs20",
              "name": "R&D",
              "description": null,
              "status": "active",
              "children": [
                {
                  "id": "cflq9586ijj00aqkhs2g",
                  "name": "Firmware",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 39,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhs30",
                  "name": "Formula",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 40,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhs3g",
                  "name": "Hardware",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 41,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhs40",
                  "name": "Software",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 42,
                  "classifier_info": null
                }
              ],
              "owner_id": 2,
              "priority": 38,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 32,
          "classifier_info": null
        },
        {
          "id": "cflq6l06ijj0044fdb3g",
          "name": "Legal",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhs4g",
              "name": "Immigration",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 44,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs50",
              "name": "Litigation",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 45,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 43,
          "classifier_info": null
        },
        {
          "id": "cflq6s86ijj004mjqqj0",
          "name": "Privacy (PII)",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhs5g",
              "name": "Customer",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 47,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs60",
              "name": "Vendor",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 48,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs6g",
              "name": "Workforce",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 49,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 46,
          "classifier_info": null
        },
        {
          "id": "cflq7186ijj004mjqqk0",
          "name": "Reports",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhs70",
              "name": "Audits & Assessments",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 51,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs7g",
              "name": "Cybersecurity",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 52,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs80",
              "name": "Incident",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 53,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs8g",
              "name": "Market Research",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 54,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs90",
              "name": "Personnel Security",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 55,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhs9g",
              "name": "Physical Security",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 56,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsa0",
              "name": "Strategy",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 57,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 50,
          "classifier_info": null
        },
        {
          "id": "cflq73g6ijj004mjqql0",
          "name": "Tax",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 58,
          "classifier_info": null
        }
      ]
    },
    {
      "id": "cflq2386ijj0044fdavg",
      "name": "Internal",
      "description": null,
      "classifier_info": null,
      "status": "active",
      "priority": null,
      "children": [
        {
          "id": "cflq7do6ijj004eesau0",
          "name": "Agreements & Contracts",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhsag",
              "name": "Lease & Rentals",
              "description": null,
              "status": "active",
              "children": [
                {
                  "id": "cflq9586ijj00aqkhsb0",
                  "name": "Building",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 61,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhsbg",
                  "name": "Car",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 62,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhsc0",
                  "name": "Equipment",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 63,
                  "classifier_info": null
                },
                {
                  "id": "cflq9586ijj00aqkhscg",
                  "name": "Office",
                  "description": null,
                  "status": "active",
                  "children": [],
                  "owner_id": 2,
                  "priority": 64,
                  "classifier_info": null
                }
              ],
              "owner_id": 2,
              "priority": 60,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsd0",
              "name": "Licensing",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 65,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsdg",
              "name": "Non Disclosure",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 66,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhse0",
              "name": "RFP & SoW",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 67,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 59,
          "classifier_info": null
        },
        {
          "id": "cl69tpqdn26g032f4p7g",
          "name": "Financials",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 82,
          "classifier_info": null
        },
        {
          "id": "cflq7kg6ijj003q3rg20",
          "name": "General Business",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 68,
          "classifier_info": null
        },
        {
          "id": "cflq7og6ijj004eesb00",
          "name": "Marketing",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 69,
          "classifier_info": null
        },
        {
          "id": "cflq7s06ijj004mjqqm0",
          "name": "Media & Systems",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 70,
          "classifier_info": null
        },
        {
          "name": "Personal (PI)",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "id": "cl6fpfn9tpa0044tdqcg",
          "priority": 90,
          "classifier_info": null
        },
        {
          "id": "cl69tpqdn26g032f4p80",
          "name": "Policies & Procedures",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhsfg",
              "name": "Code of Conduct",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 84,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsg0",
              "name": "HR",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 85,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsgg",
              "name": "Privacy",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 86,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsh0",
              "name": "Sales & Marketing",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 87,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 83,
          "classifier_info": null
        },
        {
          "id": "cflq87g6ijj0044fdb4g",
          "name": "Privacy (PI)",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhshg",
              "name": "Contact List",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 72,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsi0",
              "name": "Customer",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 73,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsig",
              "name": "Resume",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 74,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsj0",
              "name": "Workforce",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 75,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 71,
          "classifier_info": null
        },
        {
          "id": "cflq89g6ijj003q3rg30",
          "name": "Reporting",
          "description": null,
          "status": "active",
          "children": [
            {
              "id": "cflq9586ijj00aqkhsjg",
              "name": "HR",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 77,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhsk0",
              "name": "Market Research",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 78,
              "classifier_info": null
            },
            {
              "id": "cflq9586ijj00aqkhskg",
              "name": "Royalty",
              "description": null,
              "status": "active",
              "children": [],
              "owner_id": 2,
              "priority": 79,
              "classifier_info": null
            }
          ],
          "owner_id": null,
          "priority": 76,
          "classifier_info": null
        },
        {
          "id": "cflq8b86ijj004eesb10",
          "name": "Tax",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 80,
          "classifier_info": null
        },
        {
          "id": "cflq8e06ijj004eesb20",
          "name": "Training",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 81,
          "classifier_info": null
        }
      ]
    },
    {
      "id": "cflq2706ijj003q3rg00",
      "name": "Public",
      "description": null,
      "classifier_info": null,
      "status": "active",
      "priority": null,
      "children": [
        {
          "id": "cflq8o06ijj0044fdb5g",
          "name": "Open Source SW",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 88,
          "classifier_info": null
        },
        {
          "id": "cl69tpqdn26g032f4p8g",
          "name": "Safety Noticies",
          "description": null,
          "status": "active",
          "children": [],
          "owner_id": null,
          "priority": 89,
          "classifier_info": null
        }
      ]
    }
  ],
  "owner_id": 2
}

Response:
[
  {
    "id": "cflq1rg6ijj004mjqqc0",
    "name": "Restricted",
    "description": null,
    "classifier_info": null,
    "status": "active",
    "priority": null,
    "children": [
      {
        "id": "cflq2bg6ijj004mjqqd0",
        "name": "BoD",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 1,
        "classifier_info": "{\"title\":\"Restricted - BoD\",\"description\":\"Description: Classification of BoD\",\"selectedAliases\":[{\"id\":\"bb-users-access1\",\"alias\":\"bb-users-access1\"},{\"id\":\"gdrive1-access1\",\"alias\":\"gdrive1-access1\"}],\"fields\":[{\"name\":\"extension\",\"terms\":[]}],\"overWriteClassifier\":false,\"autoClassify\":true,\"indexList\":[0,0],\"status\":{\"executedPending\":false,\"executedSuccess\":false,\"executedError\":false,\"saved\":true},\"classifierId\":\"cl94q9i7ul0g04iej5i0\"}"
      },
      {
        "id": "cflq2g86ijj004mjqqe0",
        "name": "Financials",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrm0",
            "name": "Executive Compensation",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 3,
            "classifier_info": "{\"title\":\"Restricted - Financials - Executive Compensation\",\"description\":\"Description: Classification of Executive Compensation\",\"selectedAliases\":[{\"id\":\"gdrive1-access1\",\"alias\":\"gdrive1-access1\"}],\"fields\":[{\"name\":\"extension\",\"terms\":[]}],\"overWriteClassifier\":false,\"autoClassify\":true,\"indexList\":[0,1,0],\"status\":{\"executedPending\":false,\"executedSuccess\":false,\"executedError\":false,\"saved\":true},\"classifierId\":\"cl9ncb597qpg04uqgghg\"}"
          }
        ],
        "owner_id": null,
        "priority": 2,
        "classifier_info": null
      },
      {
        "id": "cflq2k86ijj004mjqqf0",
        "name": "IP (Critical)",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrmg",
            "name": "R&D",
            "description": null,
            "status": "active",
            "children": [
              {
                "id": "cflq9586ijj00aqkhrn0",
                "name": "Firmware",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 6,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhrng",
                "name": "Formula",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 7,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhro0",
                "name": "Hardware",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 8,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhrog",
                "name": "Software",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 9,
                "classifier_info": null
              }
            ],
            "owner_id": 2,
            "priority": 5,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 4,
        "classifier_info": null
      },
      {
        "id": "cflq2mo6ijj0044fdb0g",
        "name": "Legal",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 10,
        "classifier_info": null
      },
      {
        "id": "cflq2p06ijj0044fdb1g",
        "name": "M&A",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 11,
        "classifier_info": null
      }
    ]
  },
  {
    "id": "cflq1vg6ijj004eesar0",
    "name": "Confidential",
    "description": null,
    "classifier_info": null,
    "status": "active",
    "priority": null,
    "children": [
      {
        "id": "cflq3206ijj004mjqqg0",
        "name": "Agreements & Contracts",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrp0",
            "name": "Employment",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 13,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 12,
        "classifier_info": null
      },
      {
        "id": "cflq3406ijj004mjqqh0",
        "name": "BoD",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 14,
        "classifier_info": null
      },
      {
        "id": "cflq3ag6ijj004eesas0",
        "name": "Business Plan & Strategy",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 15,
        "classifier_info": null
      },
      {
        "id": "cflq3co6ijj0044fdb2g",
        "name": "Financials",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrpg",
            "name": "Payroll (Retain 10Yrs After Create)",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 17,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrq0",
            "name": "Sales",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 18,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrqg",
            "name": "Tax",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 19,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 16,
        "classifier_info": null
      },
      {
        "id": "cflq3fg6ijj003q3rg10",
        "name": "HR",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrr0",
            "name": "Complaints & Incidents",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 21,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrrg",
            "name": "Employment Agreement",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 22,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrs0",
            "name": "Offer Letter",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 23,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrsg",
            "name": "Performance Reviews",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 24,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrt0",
            "name": "Separation Agreement",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 25,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 20,
        "classifier_info": null
      },
      {
        "id": "cflq6cg6ijj004eesat0",
        "name": "Insurance & Claims",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrtg",
            "name": "Cyber",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 27,
            "classifier_info": null
          },
          {
            "id": "cfn2mblp4brg04k9pfog",
            "name": "E&O",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 31,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhru0",
            "name": "Property",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 28,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrug",
            "name": "Umbrella",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 29,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhrv0",
            "name": "Workers Comp",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 30,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 26,
        "classifier_info": null
      },
      {
        "id": "cflq6i06ijj004mjqqi0",
        "name": "IP (Non Critical)",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhrvg",
            "name": "Patent Application",
            "description": null,
            "status": "active",
            "children": [
              {
                "id": "cflq9586ijj00aqkhs00",
                "name": "Firmware",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 34,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhs0g",
                "name": "Formula",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 35,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhs10",
                "name": "Hardware",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 36,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhs1g",
                "name": "Software",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 37,
                "classifier_info": null
              }
            ],
            "owner_id": 2,
            "priority": 33,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs20",
            "name": "R&D",
            "description": null,
            "status": "active",
            "children": [
              {
                "id": "cflq9586ijj00aqkhs2g",
                "name": "Firmware",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 39,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhs30",
                "name": "Formula",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 40,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhs3g",
                "name": "Hardware",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 41,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhs40",
                "name": "Software",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 42,
                "classifier_info": null
              }
            ],
            "owner_id": 2,
            "priority": 38,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 32,
        "classifier_info": null
      },
      {
        "id": "cflq6l06ijj0044fdb3g",
        "name": "Legal",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhs4g",
            "name": "Immigration",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 44,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs50",
            "name": "Litigation",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 45,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 43,
        "classifier_info": null
      },
      {
        "id": "cflq6s86ijj004mjqqj0",
        "name": "Privacy (PII)",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhs5g",
            "name": "Customer",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 47,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs60",
            "name": "Vendor",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 48,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs6g",
            "name": "Workforce",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 49,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 46,
        "classifier_info": null
      },
      {
        "id": "cflq7186ijj004mjqqk0",
        "name": "Reports",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhs70",
            "name": "Audits & Assessments",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 51,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs7g",
            "name": "Cybersecurity",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 52,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs80",
            "name": "Incident",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 53,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs8g",
            "name": "Market Research",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 54,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs90",
            "name": "Personnel Security",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 55,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhs9g",
            "name": "Physical Security",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 56,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsa0",
            "name": "Strategy",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 57,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 50,
        "classifier_info": null
      },
      {
        "id": "cflq73g6ijj004mjqql0",
        "name": "Tax",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 58,
        "classifier_info": null
      }
    ]
  },
  {
    "id": "cflq2386ijj0044fdavg",
    "name": "Internal",
    "description": null,
    "classifier_info": null,
    "status": "active",
    "priority": null,
    "children": [
      {
        "id": "cflq7do6ijj004eesau0",
        "name": "Agreements & Contracts",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhsag",
            "name": "Lease & Rentals",
            "description": null,
            "status": "active",
            "children": [
              {
                "id": "cflq9586ijj00aqkhsb0",
                "name": "Building",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 61,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhsbg",
                "name": "Car",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 62,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhsc0",
                "name": "Equipment",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 63,
                "classifier_info": null
              },
              {
                "id": "cflq9586ijj00aqkhscg",
                "name": "Office",
                "description": null,
                "status": "active",
                "children": [],
                "owner_id": 2,
                "priority": 64,
                "classifier_info": null
              }
            ],
            "owner_id": 2,
            "priority": 60,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsd0",
            "name": "Licensing",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 65,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsdg",
            "name": "Non Disclosure",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 66,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhse0",
            "name": "RFP & SoW",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 67,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 59,
        "classifier_info": null
      },
      {
        "id": "cl69tpqdn26g032f4p7g",
        "name": "Financials",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 82,
        "classifier_info": null
      },
      {
        "id": "cflq7kg6ijj003q3rg20",
        "name": "General Business",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 68,
        "classifier_info": null
      },
      {
        "id": "cflq7og6ijj004eesb00",
        "name": "Marketing",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 69,
        "classifier_info": null
      },
      {
        "id": "cflq7s06ijj004mjqqm0",
        "name": "Media & Systems",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 70,
        "classifier_info": null
      },
      {
        "name": "Personal (PI)",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "id": "cl6fpfn9tpa0044tdqcg",
        "priority": 90,
        "classifier_info": null
      },
      {
        "id": "cl69tpqdn26g032f4p80",
        "name": "Policies & Procedures",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhsfg",
            "name": "Code of Conduct",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 84,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsg0",
            "name": "HR",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 85,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsgg",
            "name": "Privacy",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 86,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsh0",
            "name": "Sales & Marketing",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 87,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 83,
        "classifier_info": null
      },
      {
        "id": "cflq87g6ijj0044fdb4g",
        "name": "Privacy (PI)",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhshg",
            "name": "Contact List",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 72,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsi0",
            "name": "Customer",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 73,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsig",
            "name": "Resume",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 74,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsj0",
            "name": "Workforce",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 75,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 71,
        "classifier_info": null
      },
      {
        "id": "cflq89g6ijj003q3rg30",
        "name": "Reporting",
        "description": null,
        "status": "active",
        "children": [
          {
            "id": "cflq9586ijj00aqkhsjg",
            "name": "HR",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 77,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhsk0",
            "name": "Market Research",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 78,
            "classifier_info": null
          },
          {
            "id": "cflq9586ijj00aqkhskg",
            "name": "Royalty",
            "description": null,
            "status": "active",
            "children": [],
            "owner_id": 2,
            "priority": 79,
            "classifier_info": null
          }
        ],
        "owner_id": null,
        "priority": 76,
        "classifier_info": null
      },
      {
        "id": "cflq8b86ijj004eesb10",
        "name": "Tax",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 80,
        "classifier_info": null
      },
      {
        "id": "cflq8e06ijj004eesb20",
        "name": "Training",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 81,
        "classifier_info": null
      }
    ]
  },
  {
    "id": "cflq2706ijj003q3rg00",
    "name": "Public",
    "description": null,
    "classifier_info": null,
    "status": "active",
    "priority": null,
    "children": [
      {
        "id": "cflq8o06ijj0044fdb5g",
        "name": "Open Source SW",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 88,
        "classifier_info": null
      },
      {
        "id": "cl69tpqdn26g032f4p8g",
        "name": "Safety Noticies",
        "description": null,
        "status": "active",
        "children": [],
        "owner_id": null,
        "priority": 89,
        "classifier_info": null
      }
    ]
  }
]
```