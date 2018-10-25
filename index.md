
# Java Style Guide for Smarp mobile projects.


## Correctness

Strive to make your code compile without warnings. This rule informs many style decisions.


## How to name

Descriptive and consistent naming makes software easier to read and understand. 

**Clarity at the point of use** is your most important goal. Entities such as methods and properties are declared only once but used repeatedly. Design APIs to make those uses clear and concise and consistent.

**Clarity is more important than brevity.** Although Java code can be compact, it is a non-goal to enable the smallest possible code with the fewest characters. Brevity in Java code, where it occurs, is a side-effect of the strong type system and features that naturally reduce boilerplate.

Use the Java naming conventions described in the [Java Style Guide](http://cr.openjdk.java.net/~alundblad/styleguide/index-v6.html).

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

## Naming one time used storing structure objects inside business layers

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
List<String> twitterCommentSet;
HashMap<Integer, Fragment> mPageReferenceMap;
ArrayList<Object> channelList;
List<CommentItem> comments;
List<String> CommentSet;
```

## References

* [Java Style Guidelines (Draft, v6)](https://google.github.io/styleguide/javaguide.html)
* [Twitter Java Style Guide](https://github.com/twitter/commons/blob/master/src/java/com/twitter/common/styleguide.md)
* [Code Conventions for the Java TM Programming Language](https://www.oracle.com/technetwork/java/codeconvtoc-136057.html)
