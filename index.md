
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

## Naming packages


<details>
<summary>JavaLint</summary>
 - PackageName
</details>

Package names should be all lower case without underscores or other special characters.
Don’t use plural form. Follow the convention of the standard API which uses for instance `java.lang.annotation` and not `java.lang.annotations`.

```diff
+ Preferred: follow the convention of standard java API
```
```java
java.lang.annotation
```

```diff
- Not Preferred
```
```java
java.lang.annotations
com.example.deepSpace
com.example.deep_space
```

## Class, Interface and Enum Names

<details>
<summary>JavaLint</summary>
  * ClassTypeParameterName
  * InterfaceTypeParameterName
</details>

Class and enum names should typically be nouns.
Interface names should typically be nouns or adjectives ending with …able.
Use mixed case with the first letter in each word in upper case.
Use whole words and avoid using abbreviations. Format an abbreviation as a word if the it is part of a longer class name.

```diff
+ Preferred: follow the convention of standard java API
```
```java
class EmptyCell
class RunningMode
interface Expandable
class XmlParser
enum ServerResponse
```

```diff
- Not Preferred
```
```java
class Empty  // Too generic
class Running // Not a noum
class XMLParser // Abbreviation should be formatted as 'Xml'
class BtnAwesome // Abreviation of button
```

## Instance variables

<details>
<summary>JavaLint</summary>
 - LocalVariableName
 - MemberName
 - TypeName
</details>

Lower camel case

```diff
+ Preferred: Short, concise and descriptive, lower camel case
```
```java
newCustomerId
```

```diff
- Not Preferred
```
```java
newCustomerID
```

## Method Names

<details>
<summary>JavaLint</summary>
 - MethodName
</details>

Method names should typically be verbs or other descriptions of actions.
Use mixed case with the first letter in lower case.(Camel Case)

```diff
+ Preferred: Short, concise and descriptive
```
```java
public void expand()
public boolean isExpanding()
public State getState()
```

```diff
- Not Preferred
```
```java
public boolean expanding()
public State GetState()
public int get_index()
```
## Constant names

<details>
<summary>JavaLint</summary>
 - ConstantName
</details>

All in uppercase

```diff
+ Preferred: All in upper case, using underline is not prohobited
```
```Java
String SERVER_NAME
String SOCNET_TYPE
```

```diff
- Not Preferred
```
```Java
String Server_Name
String SOCNETTYPE
String SERVERName
```

## Parameters and local variables

<details>
<summary>JavaLint</summary>
 - LocalVariableName
 - ParameterName
</details>

Variable names should be in mixed case with the first letter in lower case.

```diff
+ Preferred: Short, concise and descriptive
```
```java
int currentIndex;
boolean dataAvailable;
```

```diff
- Not Preferred
```
```java
int current_index;
boolean DataAvailable;
```

## Naming UI elements

<details>
<summary>JavaLint</summary>
 - AbbreviationAsWordInName
</details>

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

## Naming several time used data dictionary objects inside business layers

<details>
<summary>JavaLint</summary>
 - MemberName
 - AbbreviationAsWordInName
</details>

Use the whole name of the object and append it with usage purpose.

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

<details>
<summary>JavaLint</summary>
 - MethodName
</details>

Example template of test method signatures is 
*test*`WhatYouAreTesting`*Should*`WhatIsExpected`

```diff
+ Preferred: "test"+WhatYouAreTesting+"Should"+WhatIsExpected
```
```Java
testClickApproveButtonShouldChangeUIToApprove();

```

```diff
- Not Preferred
```
```Java
testFirstLeaderBoardMustBeCalled();
```

## Redundant Parentheses

Variable names shoRedundant grouping parentheses (i.e. parentheses that does not affect evaluation) may be used if they improve readability.
Redundant grouping parentheses should typically be left out in shorter expressions involving common operators but included in longer expressions or expressions involving operators whose precedence and associativity is unclear without parentheses. Ternary expressions with non-trivial conditions belong to the latter.
The entire expression following a return keyword must not be surrounded by parentheses.

```diff
+ Preferred: Short, concise and descriptive
```
```java
return flag ? "yes" : "no";
String cmp = (flag1 != flag2) ? "not equal" : "equal";
```

```diff
- Not Preferred
```
```java
return (flag ? "yes" : "no");
```


## References

* [Java Style Guidelines (Draft, v6)](https://google.github.io/styleguide/javaguide.html)
* [Twitter Java Style Guide](https://github.com/twitter/commons/blob/master/src/java/com/twitter/common/styleguide.md)
* [Code Conventions for the Java TM Programming Language](https://www.oracle.com/technetwork/java/codeconvtoc-136057.html)
* [Sourcefourge checkstyle](http://checkstyle.sourceforge.net/config_naming.html)



