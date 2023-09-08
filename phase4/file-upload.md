---
layout: topic
title: Uploading Files
topic: JavaScript
category: phase3-fe
parent: Phase 3 Front End
nav_order: 12
published: true
---

## 🎯 Objectives

- Project progress check-in
- Get past any blockers you have
- File inputs and implementing file upload

## 🏗️ Wrapping Up This Project

What remains to be done on your project? Some things to consider:

- Is it working in production?
- Is it styled?
- Have you considered [how to handle states like errors (e.g., a 400 or 403 response), loading, or empty](https://blog.logrocket.com/ui-design-best-practices-loading-error-empty-state-react/)?

## 📂 Handling Uploaded Files

The back-end is learning how to accept requests that included attached files (including image files). They will need to provide you with an endpoint that can accept attached files so that you can make a request to upload the file. But even before that endpoint is working, you can implement the form to allow users to upload a file.

You'll need a way to [access the file that is being uploaded by the user](https://developer.mozilla.org/en-US/docs/Web/API/File_API/Using_files_from_web_applications#accessing_selected_files). That file is what is stored in the `file` variable in the examples below.

The HTTP method for the request could be a POST, PUT, or PATCH, depending on how the backend implements the endpoint.

### Send the file by itself and no JSON

Attach a file as an update to an existing record, sending just the file and no additional data.

👉 Notice:
    - we are using the PATCH method
    - the file is in the second position as an argument to `axios.patch()` as the body of the request.

We must set the `Content-Disposition` header, which is required by the server to handle the binary file attachment, in addition to the `Authorization` and `Content-Type` headers.

```js
axios.patch(url, file, {
  headers: {
    Authorization: 'Token ' + token,
    'Content-Type': file.type,
    'Content-Disposition': `attachment; filename=${file.name}`
  }
}).then(res => {
    // do whatever you need to do, like set state or console.log to see what you've got
    })
```

### Sending JSON + a file using FormData

If you Google how to include a file attachment in an HTTP request, you'll see a lot of references to [using the FormData object](https://developer.mozilla.org/en-US/docs/Web/API/FormData/Using_FormData_Objects). This can be useful if you want to send JSON and a file attachment at the same time. 

```js
const handleSubmit = (event) => {
    event.preventDefault()
    const formData = new FormData()
    if (titlePageImage) {
      formData.append('title_page', titlePageImage, titlePageImage.name)
    }
    formData.append('title', title)
    formData.append('author', author)
    formData.append('publication_year', pubDate)
    createBook(token, formData)
      .then((res) => {
        setSubmitted(true)
        setTitle('')
        setAuthor('')
        setPubDate('')
      })
      .catch((err) => setError(err.response.data.error))
  }
```


See the references below for more information about using a file input element and accessing a selected file. [The `useRef()` hook](https://reactjs.org/docs/hooks-reference.html#useref) will be helpful to get the files from the input element after a user has selected a file using the form.

## 🔖 Resources

- [UI Best Practices][ui-best-practices]
- [HTTP headers][http-headers]
- [The useRef hook][react-useref]
- [Uploading Files][file-upload]

{% include reference_links.md %}
