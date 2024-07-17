# Repro for issue

## Versions

firebase-tools: v13.13.3<br>
node: v20.12.2<br>

## Steps to reproduce

1. Create a named db. example "named-db-4". Default production rules:
![image](https://github.com/user-attachments/assets/164a21d2-d9c6-41e0-a5c6-d63ebe27bfbf)
2. Run `firebase deploy --only firestore:named-db-4 --project PROJECT_ID`
```
i  deploying firestore
i  firestore: reading indexes from firestore.named-db.indexes.json...
i  cloud.firestore: checking firestore.named-db.rules for compilation errors...
✔  cloud.firestore: rules file firestore.named-db.rules compiled successfully
i  firestore: deploying indexes...
✔  firestore: deployed indexes in firestore.named-db.indexes.json successfully for named-db-4 database
i  firestore: uploading rules firestore.named-db.rules...
✔  firestore: released rules firestore.named-db.rules to cloud.firestore

✔  Deploy complete!
```
3. Refresh the page, rules are updated, but historical rules are not shown
![image](https://github.com/user-attachments/assets/c1fdff12-be01-4d09-8cc3-74527cca6af4)

## Notes

Updating via the Firebase Console updates both rules and historical rules tab

1. Current rules
![image](https://github.com/user-attachments/assets/f37206a2-ae6e-4740-9951-2900d050c1ad)
2. Make some changes, then publish
![image](https://github.com/user-attachments/assets/3db45dd0-86a8-4db3-a6f9-292ac06c9c01)
3. Historical rules are shown
![image](https://github.com/user-attachments/assets/0cff67d8-2300-45a3-88fa-5587efd32ff7)
