
# Java Style Guide for Smarp mobile projects.

## Introduction

Code that looks familiar is easier to understand and therefore also easier to review, debug and maintain. To ensure that code looks familiar to all developers on the project it’s important to agree on a common set of style guidelines.

This document provides guidelines for low level coding practices such as how to indent code and how to name types and variables. Many of the stylistic choices are subjective and different developers may have different opinions about them. Keep in mind however, that having a consistent style is more important than to satisfy each individual developers preference.

## Guiding Principles

Strive to make your code compile without warnings. This rule informs many style decisions.

Use the Java naming conventions described in the [Java Style Guide Naming](http://cr.openjdk.java.net/~alundblad/styleguide/index-v6.html#toc-naming).

## Where to put code

#### Packages and file names

```code

|-- data
|   |-- repositories
|   |   |-- LikeRepository.java
|   |   |-- LikeRepositoryInterface.java
|   |   `-- LikeSendCallback.java
|   |-- local
|   |   |-- PermanentStorage.java
|   |   `-- MemoryStorage.java
|   |-- remote
|   |    `-- Server.java
|   `-- DataProviderInterface.java
|-- domain
|   |-- entities
|   |   |-- Bookmark.java
|   |   `-- Like.java
|    `-- usecases
|       |-- LikeUseCases.java
|       `-- LikeUseCasesInterface.java
`-- presentation
    |-- navigation
    |   `-- Navigator.java
     `-- channelSubscription
        |-- ChannelSubscriptionActivity.java
        |-- ChannelSubscriptionActivityInterface.java
        |-- ChannelSubscriptionActivityPresenter.java
        |-- ChannelSubscriptionActivityPresenterInterface.java
        `-- SelectedItemChangedCallback.java

```

## How to name

#### Presenter methods called by the view
onInit()   
onButtonClicked()   
onTextChanged()   
onSearchTriggered()   
onDataChanged()   
onQueryChanged()   

#### View methods called by the presenter
init/setUp()   
findViews()   
setUIElementColor()   
setUIElementText()   
setUIElementClickListener()   
navigateToNextScreen()   
showUIElement()   
hideUIElement()   
enableUIElement()   
disableUIElement()   


#### Package

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
<details>
<summary>checkstyle</summary>
 
 - PackageName
 
</details>


#### Class, Interface and Enum

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
<details>
<summary>checkstyle</summary>
 
  - ClassTypeParameterName
  - InterfaceTypeParameterName
  
</details>

#### Methods

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

<details>
<summary>checkstyle</summary>
 
 - MethodName
 
</details>

#### Constants

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

<details>
<summary>checkstyle</summary>
 
 - ConstantName
 
</details>

#### Parameters and local variables

Variable names should be in mixed case with the first letter in lower case.

```diff
+ Preferred: Short, concise and descriptive, lower camel case
```
```java
int currentIndex;
boolean dataAvailable;
String newCustomerId
```

```diff
- Not Preferred
```
```java
int current_index;
boolean DataAvailable;
String newCustomerID;

```

<details>
<summary>checkstyle</summary>
 
 - LocalVariableName
 - ParameterName
 - MemberName
 - TypeName
 
</details>

#### UI elements

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

<details>
<summary>checkstyle</summary>
 
 - AbbreviationAsWordInName
 
</details>

#### Data dictionary objects

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

<details>
<summary>checkstyle</summary>
 
 - MemberName
 - AbbreviationAsWordInName
 
</details>

#### Test methods

Example template of test method signatures is 
*test*`WhatYouAreTesting`*Should*`WhatIsExpected`

```diff
+ Preferred: "test"+WhatYouAreTesting+OptionalCondition+"Should"+WhatIsExpected
```
```Java
testClickApproveButtonShouldChangeUIToApprove();
testClickApproveButtonWithNoInternetShouldChangeUIToApprove();

```

```diff
- Not Preferred
```
```Java
testFirstLeaderBoardMustBeCalled();
```

<details>
<summary>checkstyle</summary>
 
 - MethodName
 
</details>

#### Redundant Parentheses

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



