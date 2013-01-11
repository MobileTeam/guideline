Guideline and Style for Create iOS App
=====

A Guide to starting new iOS project and programming well

* [Guide](https://github.com/MobileTeam/guideline/edit/master/style/Objective-C/README.md#guide)
* [Style](https://github.com/MobileTeam/guideline/edit/master/style/Objective-C/README.md#style)
* [Best Practice](https://github.com/MobileTeam/guideline/edit/master/style/Objective-C/README.md#best-practice)

Guide
-----
### Create Xcode projects

Create a new project in Xcode with these settings:

* Check 'Create local git repository for this project'.
* Check 'Use Automatic Reference Counting'.
* Set an appropriate 2 or 3 letter class prefix.
* Set the Base SDK to 'Latest iOS'.
* Set the iOS Deployment Target to 6.0.
* Use the Apple LLVM compiler.

Add a `.gitignore` file with contents:
    
    .DS_Store
    *~
    *~.nib/
    *.dat
    *.dep
    *.swp
    *.hmap
    *.LinkFileList
    *.mode1
    *.mode1v3
    *.mode2v3
    *.o
    *.pbxuser
    *.perspective
    *.perspectivev3
    *.xcworkspace
    build/
    xcuserdata

Add a `.gitattributes` file with contents:

    *.pbxproj binary merge=union


Style
----
### A guide for programming in style.

High level guidelines:

- Be consistent.
- Don't rewrite existing code to follow this guide.
- Don't violate the conventions without a good reason.

### Objective-C

- #import linked frameworks in the prefix header (ProjectName-Prefix.pch).
- Keep `.xib` files grouped with their associated view class.
- Order `#import` statements alphabetically.
- Order `@class` directives alphabetically.
- Order `@property` modifiers: memory management, atomicity, writability.
- Organize classes into `models`, `views`, `controllers`, `categories`, and `services` directories.
- Prefer `@class` to `#import` when referring to external classes in a public `@interface`.
- Prefer `@property` to declaring instance variables.
- Prefix class names with a 2-letter project acronym.
- Prefix string constants being used as keys with 'k'.
- Remove `#import` statements for Foundation and UIKit in new project templates.
- Separate methods by function using `#pragma mark - <Section Name>`
- Separate sections into subsections using `#pragma mark <Subsection Name>`
- Use `@[arrayObject]`, `@{@"key" : value}`, `@(YES or NO)`, and `@5.0` literals.
- Use `@interface ClassName ()` to declare private properties.
- Use `lowerCamelCase` for method names.
- Use `NSAssert` in methods that require the presence of certain arguments.
- Write methods using the happy path. Indent the exceptional cases. Keep the optimal case in the left-most column.
- Don't create multiple class in same file.
- Don't call view-lifecycle method in your code.

### Extra Point

- Use `YES` and `NO` instead `true` and `false`
- Try to using dot syntax consistently
- Try fixes every analyzer issue.
- Treat `warings` as `errors`.
- Avoid using short variable name like `img` and `btn`.
- Avoid make giant `.xib` file. (split into small .nib or create in code)
- Don't use `UIGestureReconizer` to make button.
- Don't pass model or object to `UITableViewCell` subclass.

Best Practice
---

### General

* Don't duplicate the functionality of a built-in library.
* Don't swallow exceptions or "fail silently."
* Don't write code that guesses at future functionality.
* [Exceptions should be exceptional](http://rdd.me/yichhgvu).
* [Keep the code simple](http://rdd.me/ko2aqda2).


### Object-Oriented Design

* Avoid global variables.
* Avoid long parameter lists.
* Limit collaborators of an object (entities an object depends on).
* Limit an object's dependencies (entities that depend on an object).
* Prefer composition over inheritance.
* Prefer small methods. One line is best.
* Prefer small objects with a single, well-defined responsibility.
* [Tell, don't ask](http://goo.gl/Ztawt).


### Objective-C

* Prefer categories on `Foundation` classes to helper methods.
* Prefer string constants to literals when providing keys or key paths to methods.


Credit
------

* Thoughtbot guides - https://github.com/thoughtbot/guides
* inessential's Brent Simmons - http://inessential.com/2012/12/31/coders_in_the_hands_of_an_angry_god
