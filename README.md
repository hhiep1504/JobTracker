# JobTracker sync laptop + iPhone

Du an nay dong bo du lieu giua nhieu thiet bi bang Firebase Firestore.

## 1) Cau hinh Firebase

Mo file uk_job_tracker.html va thay cac gia tri trong FIREBASE_CONFIG:
- apiKey
- authDomain
- projectId
- storageBucket
- messagingSenderId
- appId

Trong Firebase Console:
- Tao project
- Bat Firestore Database (Production hoac Test mode)

Rule Firestore toi thieu de dung ca nhan:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /job_tracker_rooms/{roomId} {
      allow read, write: if true;
    }
  }
}
```

Luu y: Rule tren don gian cho nhu cau ca nhan. Neu can bao mat cao hon, nen them Firebase Auth.

## 2) Deploy len GitHub Pages

1. Tao repository GitHub va push folder nay len.
2. Dung nhanh mac dinh la main.
3. Vao Settings > Pages, chon Source la GitHub Actions.
4. Moi lan push len main, workflow deploy-pages.yml se tu deploy.
5. Mo URL Pages tren laptop va iPhone.

## 3) Ket noi sync tren 2 thiet bi

1. Mo website.
2. Nhap cung mot Sync ID tren laptop va iPhone.
3. Bam Connect sync.
4. Doi trang thai hien Synced: ten-id.

Luc nay ca hai thiet bi se dung chung du lieu job application.
