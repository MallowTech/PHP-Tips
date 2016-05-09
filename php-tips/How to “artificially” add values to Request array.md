---
title: How to “artificially” add values to Request array
tip-number: 7
tip-username: Vijayanand
tip-username-profile: https://github.com/vijayanandp
tip-description: How to “artificially” add values to Request array.

---

We often come in an situation that a store() or update() method with Request parameter need to add additional values to a request before calling Eloquent function.

Here is the normal code without additional values.

```php
function store(Request $request) 
{
  // some additional code goes here 
  User::create($request->all());
}
```
This is how we can change the code to get additional values.

```php
function store(Request $request) 
{
  // some additional code goes here 
  $mark = 100; // some logic that decies your mark
  $request->request->add(['mark' => $mark]);
  User::create($request->all());
}
```

