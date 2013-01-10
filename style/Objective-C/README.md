Style
=====

### A guide for programming in style.

High level guidelines:

- Be consistent.
- Don't rewrite existing code to follow this guide.
- Don't violate the conventions without a good reason.

### Objective-C

- #import linked frameworks in the prefix header (ProjectName-Prefix.pch).
- Keep .xib files grouped with their associated view class.
- Order #import statements alphabetically.
- Order @class directives alphabetically.
- Order @property modifiers: memory management, atomicity, writability.
- Organize classes into models, views, controllers, categories, and services directories.
- Prefer @class to #import when referring to external classes in a public @interface.
- Prefer @property to declaring instance variables.
- Prefix class names with a 2-letter project acronym.
- Prefix string constants being used as keys with 'k'.
- Remove #import statements for Foundation and UIKit in new project templates.
- Separate methods by function using #pragma mark - <Section Name>
- Separate sections into subsections using #pragma mark <Subsection Name>
- Use @[arrayObject], @{@"key" : value}, @(YES or NO), and @5.0 literals.
- Use @interface ClassName () to declare private properties.
- Use lowerCamelCase for method names.
- Use NSAssert in methods that require the presence of certain arguments.
- Write methods using the happy path. Indent the exceptional cases. Keep the optimal case in the left-most column.