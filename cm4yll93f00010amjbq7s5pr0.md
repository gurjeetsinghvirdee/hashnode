---
title: "Implementing Authorization in Notes App"
seoTitle: "Secure Authorization for Notes App"
seoDescription: "Learn how to implement authorization in a Notes app using attribute-based access control to ensure secure access to user-specific notes"
datePublished: Sat Dec 21 2024 19:54:12 GMT+0000 (Coordinated Universal Time)
cuid: cm4yll93f00010amjbq7s5pr0
slug: implementing-authorization-in-notes-app
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1734809247678/dee09ccc-bcaf-4eb7-bd25-e70c14e58b9b.png
tags: backend, databases, appwrite

---

Welcome to Day 7 of our Appwrite series. Today, we’ll explore implementing authorization and access control in our note-taking app.

### Introduction

In our Notes app, we want to ensure that users can only access and modify their notes. We’ll implement authorization using attribute-based access control.

### Implementing Permissions

To implement attribute-based access control, we’ll store the note ownership as an attribute on the document. We’ll then check this attribute when retrieving the note to ensure only the owner can access or modify it.

Here’s an example of how to implement attributes-based access control:

```typescript
// notes.service.ts
import { Appwrite } from 'appwrite';

const appwrite = new Appwrite();
appwrite
    .setEndpoint('https://localhost.appwrite.io/v1') // Your Appwrite Endpoint
    .setProject('YOUR_PROJECT_ID')

const createNote = async (note: any, userId: string) => {
    const document = await appwrite.databases.createDocument('notes', note, ['owner:' + userId]);
    return document; 
}

const getNote = async (noteId: string, userId: string) => {
    const document = await appwrite.databases.getDocument('notes', noteId);
    if (document.attributes['owner'] !== userId) {
        throw new Error('Unauthorized');
    }
    return document;
};
```

Navigate to the **Settings** tab, there you get your API endpoint and your project ID.  

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734810764208/84b718c0-163d-4e26-8fad-fb1a905cf5d5.png align="center")

### Conclusion

In this article, we implemented authorization in our Notes app using attribute-based access control. We stored the note ownership as an attribute on the document and checked it when retrieving it to ensure that only the owner can access or modify it.

Stay tuned for Day 8, where we'll explore implementing real-time updates in Appwrite.