DELETE /api/v1/sharepoint/delete_user_permission
payload:
```
{
  "user_email": "renz.monterola@gmail.com",
  "current_role": "read",
  "site_id_item_map": [
    {
      "site_id": "35thyb.sharepoint.com,8f1a4608-feda-4655-9630-16b9769520bb,6f1aec78-8103-4c2d-aa47-a7bf07efd2f0",
      "site_name": "Communication site",
      "item_ids": [
        "01WNC537QFY3OZAHHSA5CZYOQFKDOAS4BJ"
      ],
      "access_given_through": [
        ""
      ]
    }
  ],
  "permission_item_map": {
    "01WNC537QFY3OZAHHSA5CZYOQFKDOAS4BJ": "aTowIy5mfG1lbWJlcnNoaXB8cmVuei5tb250ZXJvbGFfZ21haWwuY29tI2V4dCNAMzV0aHliLm9ubWljcm9zb2Z0LmNvbQ"
  },
  "data_source_id": "cm4s2ukub7bg04a5pcrg"
}
```
response:
```
{
  "code": 200,
  "success": true,
  "message": "{\"user_tobe_removed_from\": [], \"user_tobe_added_to\": []}"
}
```