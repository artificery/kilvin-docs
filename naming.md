
# Naming

## PHP Classes, Methods, and Variables.

The Kilvin CMS standard is to name all methods and classes in CamelCase with classes having their first letter capitalized. Variables are typically camel_case. For example: 

`(new HighSchool)->findClassById($class_id)->class_name;`

## Template Folders, Template Names, and Entry URL Titles

Allowed characters in the name of a template folder, template name, or a weblog entry's URL Title are alphanumerical characters as well as hyphens and underscores.

For weblog entry URL titles, the javascript auto-create code in the Publish area will, by default, use hyphens. You can switch this to underscore in the Weblog Preferences for each weblog.

## Twig: Variables, Functions, Filters, etc

Kilvin CMS follows the same standard as its PHP code when building Twig functions, filters, and variables.  All functions and filters will be camelCase (ex: `wordLimit`) and all variables will be snake case (ex: `member_group_id`).

For the names of weblog fields, custom member fields, and template variables, Kilvin CMS requires that you name them using snake case as well. This is because the [Twig template language](https://twig.symfony.com/doc/2.x/templates.html#variables) treats hyphens as a minus operator and the variable would need to be treated a special way in order to work correctly in templates. 