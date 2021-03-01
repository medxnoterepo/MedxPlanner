# MedxPlanner Getting Started

### Prerequisite Software

- Microsoft Teams 
- Postman

## App Installation Process

1. **Consent process**: 

   1. Create a user called: [medxplanner1@_____.com](mailto:medxplanner1@_____.com) and make sure `medxplanner1` is all small.
   2. Now hit this endpoint [https://medxprod-api-consent-service.medx.im](https://medxprod-api-consent-service.medx.im) and sign-in with the above credentials.
   3. For admin approval click `Have an admin account? Sign in with that account`.
   4. Sign in with your Admin credentials and accept all the permission.
   5. Sign in again using your medxplanner1 email created earlier.
   
    For more assistance refer to `ConsentProcess.mov` from our `medxplanner-videos` folder.

2. **Tab upload and configuration in your team/channel**:
  
   1. log in to Microsoft Teams with `admin credentials` and go to the apps section.
   2. Click on `Upload a coustomised app` and select the zip folder attached with in the same folder.
   3. Click `Add to a team` and select the team in which you want to add, then click `Setup tab`.
   4. Please, follow the instructions and click `Authenticate`
   5. Create a bucket, if already created then skip.
   6. In the form shown, go to **Dropdown of an existing plan or new plan** and select **New Plan**.
   7. Enable shift, if you use Microsoft Shifts.
   8. **Important:** Click the button before saving.
   
    For more assistance refer to `RouteCreation.mov` from our `medxplanner-videos` folder.
######  Bravo!! tab uploaded successfully in your team. Get ready to add tasks.

## Add Task using Postman

   API Endpoint: [https://medxprod-api-task-service.medx.im/medxtask](https://medxprod-api-task-service.medx.im/medxtask)
   ```
   $ Authorization : Get this from MedxPlanner tab as "API Key",  Example: a55c65d0-d466-480d-9ea9-72b621e0a307
   $ userId: Get this from MedxPlanner tab as "User ID", Example: b8c43f7a-7bc3-4e6f-978b-050e7448a522
   $ routeId: Get this from the MedxPlanner tab as "ID" under route list, for the route which you want to send the task too, Example: 2ebd0508-ef81-4d5f-9f32-07d11a31ee20
   $ tenantId: Click on the ellipsis on the right of Team and click on "Get a link to team", Just Copy your "tenantId". Example: tenantId=5df91xxx-xxxx-xxxx-xxxx-bdc0cba3xxxx
   $ startDateTimestamp example: 2021-01-04 15:12:12Z
   $ hospitalReference: medxtask_a06a7b53-e384-4433-b274-2e4b2712b726
   ```
   
   ### Implement Manually

   1. Select the request as `POST` and paste the above endpoint.
   2. Under Authorization, select type as `Bearer Token` and paste the above Authorization (`API Key`).
   3. Go to `Body` and select `raw` with text as `JSON`.
   4. Update the content of the below sample bodies with `routeId`, `userId`, `tenantId`.
   
**Minimal Body content**

```
{
  "routeId": "7fcxxxxx-xxxx-xxxx-xxxx-5d35838xxxxx",
  "userId": "77cxxxxx-xxxx-xxxx-xxxx-5f09858xxxxx",
  "tenantId": "dcdxxxxx-xxxx-xxxx-xxxx-31002a1xxxxx",
  "title": "Task: Add you task title",
  "percentComplete": 0,
  "createdTimestamp": "2021-01-29T21:51:49Z",
  "startDateTimestamp": "2021-01-29T15:10:15Z",
  "dueDate": "2021-11-20T11:47:33.000Z",
  "Notes": "Add some useful notes here"
}

```

**Full Body content**

```
{
  "routeId": "7fcxxxxx-xxxx-xxxx-xxxx-5d35838xxxxx",
  "userId": "77cxxxxx-xxxx-xxxx-xxxx-5f09858xxxxx",
  "tenantId": "dcdxxxxx-xxxx-xxxx-xxxx-31002a1xxxxx",
  "title": "Task: Add you task title",
  "hospitalAssignment": null,
  "percentComplete": 0,
  "createdTimestamp": "2021-01-29T21:51:49Z",
  "startDateTimestamp": "2021-01-29T15:10:15Z",
  "dueDate": "2021-11-20T11:47:33.000Z",
  "Notes": "Add some useful notes here",
  "checklistItems": [
    {
      "title": "itema"
    },
    {
      "title": "itemb"
    }
  ],
  "attachments": [
    {
      "url": "https://www.google.co.in",
      "alias": "name of the file"
    }
  ],
  "comments": "null,",
  "priority": null
}
```

For more assistance refer to `TaskViaPostman.mov` from our `medxplanner-videos` folder.

   ### Implement via Postman Collection
   
   **Collection URL**: `https://www.getpostman.com/collections/4bad5287ba6d5b7c4465`
   
   1. Go to Postman, select `Import` under the `Link` section paste in the above URL and import.
   2. Under `Authorization`, select type as `Bearer Token` and paste the above Authorization (`API Key`).
   3. Go to `Body` update `routeId`, `userId` and `tenantId` as per the data in you MedxPlanner.
   
