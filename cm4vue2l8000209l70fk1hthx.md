---
title: "Day 5: Defining Collections for Our Appwrite Project"
seoTitle: "Appwrite Project: Day 5 - Define Collections"
seoDescription: "Create and manage Appwrite collections for note-taking. Step-by-step: define structure, perform operations"
datePublished: Thu Dec 19 2024 21:37:15 GMT+0000 (Coordinated Universal Time)
cuid: cm4vue2l8000209l70fk1hthx
slug: day-5-defining-collections-for-our-appwrite-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1734644168734/6408f0e9-f4d6-45d3-9e35-15e79c76fd92.png
tags: backend, databases, appwrite

---

Welcome to Day 5 of our Appwrite series. Today, we’ll explore creating collections in Appwrite for our note-taking app project.

### Introduction

On Day 4, we created a new Appwrite project and set up our note-taking app. Now, we’ll create a note collection and define its structure.

### Creating the Notes Collection

To create the notes collection, follow these steps:

1. Log in to your Appwrite account.
    
2. Select the project you created.
    
3. Navigate to the **Databases** section and create a new Database.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734631492443/441faef8-8c4b-447c-a949-b7b2e032d728.png align="center")
    
4. Click on the **Create Collection** button.
    
5. Fill in the required details, such as the collection name.
    
6. Click **Create** to create the collection.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734631517034/e7be2bd0-2763-44ef-9eff-6fa66928060d.png align="center")
    

### Defining the Notes Collection Structure

Let’s define the structure of our notes collection. We’ll need the following fields:

* `id` (string): A unique identifier for each note.
    
* `title` (string): The title of the note.
    
* `content` (string): The content of the note.
    
* `createdAt` (date): The date and time when the note was created.
    
* `updatedAt` (date): The date and time when the note was last updated.
    

We’ll use Appwrite’s built-in data types to define these fields.

### Creating a New Note

To create a new note, we’ll use the Appwrite CLI. Run the following command:

```bash
 appwrite databases create-document --database-id=<DATABASE_ID> --collection-id=<COLLECTION_ID> --document-id="unique()" --data '{"id": "1", "title": "My First Note", "content": "This is my First Note."}'
```

![Screenshot showing a terminal command to create a document in an Appwrite database with details like ID, title, and content. The note's title is "My First Note," and the content reads "time to post 5th day of appwrite series." Various permissions and timestamps are shown.](https://cdn.hashnode.com/res/hashnode/image/upload/v1734641909643/23afb3f1-17f8-4522-a166-8683e6ecd35b.png align="center")

Replace `[DATABASE_ID]` and `[COLLECTION_ID]` with the actual ID you created.

### Retrieving Notes

To retrieve all notes, run the following command:

```bash
 appwrite databases list-documents --database-id=<DATABASE_ID> --collection-id=<COLLECTION_ID>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734642319940/f791c4c6-b13f-417e-8b93-cd72cd0b723b.png align="center")

### Updating a Note

To update all notes, run the following command:

```bash
appwrite databases update-document --database-id=<DOCUMENT_ID> --collection-id=<COLLECTION_ID> --document-id=<DOCUMENT_ID> --data '{"id": "1001", "title": "My second note", "content": "This command used to update the document"}'
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734642742287/79a80fc0-0157-4bc3-96c0-508b6f71b125.png align="center")

Replace `[DATABASE_ID]` and `COLLECTION_ID` with the actual ID you created, and `[DOCUMENT_ID]` with the actual ID of the note, you want to update.

### Deleting a Note

To delete a note, run the following command:

```bash
$ appwrite databases delete-document --database-id=<DATABASE_ID> --collection-id=<COLLECTION_ID> --document-id=<DOCUMENT_ID>
```

Replace `[DATABASE_ID]` and `COLLECTION_ID` with the actual ID you created, and `[DOCUMENT_ID]` with the actual ID of the note, you want to delete.

### Conclusion

In this article, we created a note collection in Appwrite and defined its structure. We also explored creating, retrieving, updating, and deleting notes using the Appwrite CLI.

Stay tuned for Day 6, where we'll explore user authentication in Appwrite.

### Additional Resources

* [Appwrite Documentation](https://appwrite.io/docs)