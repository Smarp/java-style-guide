
# Java Style Guide for Smarp mobile projects.


## Correctness

Strive to make your code compile without warnings. This rule informs many style decisions.


## Introduction

This is a set of style guidelines for JDK Release Projects in the OpenJDK Community.

## Motivation

Code that looks familiar is easier to understand and therefore also easier to review, debug and maintain. To ensure that code looks familiar to all developers on the project it’s important to agree on a common set of style guidelines.

This document provides guidelines for low level coding practices such as how to indent code and how to name types and variables. Many of the stylistic choices are subjective and different developers may have different opinions about them. Keep in mind however, that having a consistent style is more important than to satisfy each individual developers preference.

## Guiding Principles

The guidelines in this document strive to maximize,

1. Correctness
2. Readability
3. Maintainability
4. Debuggability
5. Consistency
6. Aesthetics

While this document covers a lot of ground, it should be noted that no style guide can answer all questions for us, and developers will always need to use good judgment towards the end of producing code that is correct, readable, maintainable, debuggable, consistently formatted, and aesthetically pleasing.

Tool support is nice, but ultimately each IDE and style checking tool can handle different sets of rules, and support for rules that can’t be handled today might be added in future versions. So, whether a rule plays well with tools or not can be a factor, but it’s secondary to the above principles.

Use the Java naming conventions described in the [Java Style Guide Naming](http://cr.openjdk.java.net/~alundblad/styleguide/index-v6.html#toc-naming).

## Naming UI elements

Use the whole name of the element without the UI prefix. After that it can be followed by a description

```diff
+ Preferred: Short, concise and descriptive
```
```java
TextView textViewFirstName
TextView textViewLastName
Button buttonShareToFacebook
Button buttonShareToTwitter
ImageView imageViewProfileAvatar
ImageView imageViewLogo
URL urlProfileAvatar
RecyclerView recyclerViewShareHistory
...
```

```diff
- Not Preferred
```
```java
LinearLayout googleButton;
LinearLayout linkedInButton;
ButtonMuseo loginButtonPassword;
TextMuseo invalidPasswordHint;
InputMethodManager imm;
LinearLayout passwordBlocked;
TextMuseo errorText;
ImageButton xButton;
IconButton mBtnCheckBox;
```

## Naming one time used data dictionary objects inside business layers

Use the whole name of the object

```diff
+ Preferred: Short, concise and descriptive
```
```Java
HashMap<Class|Primitive, Class|Primitive> hashMap;
Map<Class|Primitive, Class|Primitive> map;
Set<Class|Primitive> set;
LinkedList<Class|Primitive> linkedList;
ArrayList<Class|Primitive> arrayList;
List<CommentItem> listCommentItem; // Custom class example
List<Class|Primitive> list;
SQLiteHelper sqliteHelper;
Cursor cursor;
...
```

```diff
- Not Preferred
```
```Java
HashMap<String, Integer> socnetShared;
List<String> twitterCommentSet;
HashMap<Integer, Fragment> mPageReferenceMap;
ArrayList<Object> channelList;
List<CommentItem> comments;
List<String> CommentSet;
```

## Naming several time used data dictionary objects inside business layers

Use the whole name of the object

```diff
+ Preferred: Short, concise and descriptive
```
```Java
HashMap<Object, Object> hashMap;
HashMap<Object, Object> hashMapPageReference;
Map<Object, Object> map;
Set<Object> set;
LinkedList<Object> linkedList;
ArrayList<Object> arrayListChannel;
List<CommentItem> listComment;
List<String> listComment;
SQLiteHelper sqliteHelper;
Cursor cursor;

```

```diff
- Not Preferred
```
```Java
HashMap<String, Integer> socnetShared;
HashMap<Integer, Fragment> mPageReferenceMap;
List<String> twitterCommentSet;
List<CommentItem> comments;
List<String> CommentSet;
ArrayList<Object> channelList;
```
## Naming test methods

Example template of test method signatures is 
*test*`WhatYouAreTesting`*Should*`WhatIsExpected`

```diff
+ Preferred: test+WhatYouAreTesting+Should+WhatIsExpected
```
```Java
testClickApproveButtonShouldChangeUIToApprove();
testClickApproveButtonShouldChangeUIToApprove();

```

```diff
- Not Preferred
```
```Java
HashMap<String, Integer> socnetShared;
HashMap<Integer, Fragment> mPageReferenceMap;
List<String> twitterCommentSet;
List<CommentItem> comments;
List<String> CommentSet;
ArrayList<Object> channelList;
```


## References

* [Java Style Guidelines (Draft, v6)](https://google.github.io/styleguide/javaguide.html)
* [Twitter Java Style Guide](https://github.com/twitter/commons/blob/master/src/java/com/twitter/common/styleguide.md)
* [Code Conventions for the Java TM Programming Language](https://www.oracle.com/technetwork/java/codeconvtoc-136057.html)
