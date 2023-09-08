---
layout: topic
title: Search in React
topic: JavaScript
category: phase3-fe
parent: Phase 3 Front End
nav_order: 11
published: true
---

## 🎯 Objectives

- Checking in on project progress 👀
- Adding search in your application 🔍

To implement search in your application, you will need to collect user input and then either make an API request or filter existing data on the page. You probably want to have a text input so that your user can type in a search term, although you could use other types of inputs as well.

## 🏗️ Project

Where do things stand with your project today? What tasks are highest priority today and tomorrow? Is there anything blocking you from making progress?

## Example Search Request with Query Params

Remember the [iTunes API](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html#//apple_ref/doc/uid/TP40017632-CH5-SW1)? You made a request to the API to get search results, and you needed to include query params that specified the search fields and terms you wanted to use for the search.

```txt
https://itunes.apple.com/search?term=jack+johnson
```

Here's how you might make a request that uses query params using [Axios](https://github.com/axios/axios#request-config). Note: this example depends on `searchTerm` and `token` being defined in your code. You'll need an input element in otder for your user to type in their search term, and you'll need to use that input in your React component.

```js
axios.get('https://drf-library-api.herokuapp.com/api/books',
  {
    params: {search: searchTerm},
    headers: {Authorization: `Token ${token}` }
  }
)
```

## Example Search with Filter

If you want to allow your user to search through data you already have in your component, you can filter the data based on a user's search term. Instead of making a request you can filter existing data using the `filter` array method and then display a filtered collection of data. `filter` returns an array, so you can chain `map` directly after it.

```js
collectionOfItems.filter((item) => {
  return item.title.toLowerCase().includes(searchTerm.toLowerCase())
  }).map(...)
```

## 🔖 References

- [Search & Filtering][react-search]
- [Forms][react-forms]
- [`useRef`][react-useref]
- [Custom Hooks][react-custom-hooks]

{% include reference_links.md %}
