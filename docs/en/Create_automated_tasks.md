**Create Account Management Task:** Directly call the [Add Task API](https://open.geelark.com/api/task-add).

**Create Video or Image Collection Posting Task:** First, upload the materials, then call the [Add Task API](https://open.geelark.com/api/task-add).

Creating Video or Image Collection Posting Task
-----------------------------------------------

1.  [File Upload](https://open.geelark.com/api/upload-getUrl)
    
2.  Use the `resource access URL` obtained in step 1 as the upload URL for the video or image, and then call the [Add Task API](https://open.geelark.com/api/task-add).