# Intersection Observer API

The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport.

## Intersection information is needed for many reasons, such as:

* Lazy-loading of images or other content as a page is scrolled.
* Implementing "infinite scrolling" web sites, where more and more content is loaded and rendered as you scroll, so that the user doesn't have to flip through pages.
* Reporting of visibility of advertisements in order to calculate ad revenues.
* Deciding whether or not to perform tasks or animation processes based on whether or not the user will see the result.

## Intersection observer concepts

The Intersection Observer API allows you to configure a callback that is called when either of these circumstances occur:

* A target element intersects either the device's viewport or a specified element. That specified element is called the root element or root for the purposes of the Intersection Observer API.
* The first time the observer is initially asked to watch a target element.

Typically, you'll want to watch for intersection changes with regard to the target element's closest scrollable ancestor, or, if the target element isn't a descendant of a scrollable element, the device's viewport. To watch for intersection relative to the device's viewport, specify null for root option. Keep reading for a more detailed explanation about intersection observer options.

Whether you're using the viewport or some other element as the root, the API works the same way, executing a callback function you provide whenever the visibility of the target element changes so that it crosses desired amounts of intersection with the root.

The degree of intersection between the target element and its root is the intersection ratio. This is a representation of the percentage of the target element which is visible as a value between 0.0 and 1.0.install foobar

## Usage

```python
let options = {
  root: document.querySelector('#scrollArea'),
  rootMargin: '0px',
  threshold: 1.0
}

let observer = new IntersectionObserver(callback, options);
```

```python
let target = document.querySelector('#listItem');
observer.observe(target);

// the callback we setup for the observer will be executed now for the first time
// it waits until we assign a target to our observer (even if the target is currently not visible)
```

```python
let callback = (entries, observer) => {
  entries.forEach((entry) => {
    // Each entry describes an intersection change for one observed
    // target element:
    //   entry.boundingClientRect
    //   entry.intersectionRatio
    //   entry.intersectionRect
    //   entry.isIntersecting
    //   entry.rootBounds
    //   entry.target
    //   entry.time
  });
};

```

## See more here

https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API
