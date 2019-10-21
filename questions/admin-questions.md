## Salesforce Admin Questions

Pull requests for suggestions and corrections are welcome!

## Salesforce Fundamentals
* [How can we find out what licenses the org has? And how many licenses are available?](#How-can-we-find-out-what-licenses-the-org-has)
* [What is a sandbox org? What are the different types of sandboxes in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What useful information can you find on the company information page?](#describe-z-index-and-how-stacking-context-is-formed)
* [What useful information can you find on the company information page?](#describe-z-index-and-how-stacking-context-is-formed)

## Security & Access
* [What is a profile](#describe-z-index-and-how-stacking-context-is-formed)
* [What is the difference between a profile & permission set?](#describe-block-formatting-context-bfc-and-how-it-works)
* [What is the difference between role & profile?](#what-are-the-various-clearing-techniques-and-which-is-appropriate-for-what-context)
* [What are sharing settings?](#describe-z-index-and-how-stacking-context-is-formed)
* [What’s the difference between Record Types & Page Layouts? What is the use of each?](#what-is-css-selector-specificity-and-how-does-it-work)
* [Can you delete a user? Why not?](#what-is-css-selector-specificity-and-how-does-it-work)
* [What are Audit Fields?](#whats-the-difference-between-resetting-and-normalizing-css-which-would-you-choose-and-why)

## Data Modelling
* [What is the difference between a lookup relationship & master:detail relationship?](#how-would-you-approach-fixing-browser-specific-styling-issues)
* [What is an External lookup?](#what-are-the-different-ways-to-visually-hide-content-and-make-it-available-only-for-screen-readers)
* [Why do we create relationships between objects?](#explain-css-sprites-and-how-you-would-implement-them-on-a-page-or-site)
* [What is a self-relationship?](#how-do-you-serve-your-pages-for-feature-constrained-browsers-what-techniquesprocesses-do-you-use)
* [What is a junction object? What do we use them for?](#are-you-familiar-with-styling-svg)
* [What happens if you delete a field?](#have-you-used-or-implemented-media-queries-or-mobile-specific-layoutscss)
* [What can you do with a schema builder?](#have-you-used-or-implemented-media-queries-or-mobile-specific-layoutscss)
* [What is a junction object? What do we use them for?](#are-you-familiar-with-styling-svg)

## Sales, Service, Analytics, Data Management
* [What is a price book?](#are-you-familiar-with-styling-svg)
* [When you convert a Lead what does it become?](#are-you-familiar-with-styling-svg)
* [What is a case?](#are-you-familiar-with-styling-svg)
* [What are the key 3 report types available in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the 3 key differences between Data Loader & Data Import Wizard?](#are-you-familiar-with-styling-svg)

## Automation
* [What are the key automation tools in Salesforce? How do you know when to use which?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is a validation rule?](#what-are-some-of-the-gotchas-for-writing-efficient-css)


## Scenario Based Questions
* [How do you restrict access to a certain object?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [How do you give access to a certain object?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [I am looking at an Opportunity record. The record does not have a 'Share' button. Why?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the key automation tools in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the key automation tools in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the key automation tools in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the key automation tools in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)


### How can we find out what licenses the org has
The browser determines what styles to show on an element depending on the specificity of CSS rules. We assume that the browser has already determined the rules that match a particular element. Among the matching rules, the specificity, four comma-separate values, `a, b, c, d` are calculated for each rule based on the following:

1. `a` is whether inline styles are being used. If the property declaration is an inline style on the element, `a` is 1, else 0.
2. `b` is the number of ID selectors.
3. `c` is the number of classes, attributes and pseudo-classes selectors.
4. `d` is the number of tags and pseudo-elements selectors.

The resulting specificity is not a score, but a matrix of values that can be compared column by column. When comparing selectors to determine which has the highest specificity, look from left to right, and compare the highest value in each column. So a value in column `b` will override values in columns `c` and `d`, no matter what they might be. As such, specificity of `0,1,0,0` would be greater than one of `0,0,10,10`.

In the cases of equal specificity: the latest rule is the one that counts. If you have written the same rule into your stylesheet (regardless of internal or external) twice, then the lower rule in your style sheet is closer to the element to be styled, it is deemed to be more specific and therefore will be applied.

I would write CSS rules with low specificity so that they can be easily overridden if necessary. When writing CSS UI component library code, it is important that they have low specificities so that users of the library can override them without using too complicated CSS rules just for the sake of increasing specificity or resorting to `!important`.

###### References

* https://www.smashingmagazine.com/2007/07/css-specificity-things-you-should-know/
* https://www.sitepoint.com/web-foundations/specificity/

[[↑] Back to top](#css-questions)