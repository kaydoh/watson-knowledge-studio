---

copyright:
  years: 2015, 2018
lastupdated: "2018-03-20"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

This documentation is for {{site.data.keyword.knowledgestudiofull}} on {{site.data.keyword.cloud}}. To see the documentation for the previous version of {{site.data.keyword.knowledgestudioshort}} on {{site.data.keyword.IBM_notm}} Marketplace, [click this link ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/docs/services/knowledge-studio/rule-annotator.html){: new_window}.
{: tip}

# Rules
{: #rule-annotator}

Create a rule-based model that can recognize patterns in your documents. Use rules to capture patterns that occur in documents and convey information about underlying entity types.
{: shortdesc}

## Class overview

When you construct a rule, you use classes to represent types of information. These classes are similar to entity types. So, why don't we just use entity types when defining rules? Because as you build rules, you can define intermediate classes that are used only to build other more complex classes. These intermediate classes are solely utilitarian. They are not useful on their own. Intermediate classes work with other intermediate classes to define a more useful and complete class. An intermediate class is necessary, but not something you expose as part of a type system. To enable the rule-based model to do useful things like pre-annotate documents with entity mentions, you must map the complex classes that you use during rule creation to their equivalent entity types from the type system.

For example, you want a model that can recognize people's names. To train a machine learning model to recognize people's names, you would annotate many different names that are written in a variety of formats in documents in an annotation set with the `PERSON` entity type, and train a model to recognize people's names. To create a rule-based model to recognize people's names, you define a rule that describes the text patterns used to write people's names. So, you might create a `FirstName` class and a `LastName` class and use these intermediate classes to define a `FullName` class. You might define conditions that determine the placement of the `FullName` class in relation to common prefixes, such as `Dr.` and common suffixes, such as `Jr.`. When the rule-based model is used, the `FullName` class is mapped to the `PERSON` entity type.

Another reason to avoid mapping intermediate classes to entities in your type system is that if you pre-annotate documents with the rule-based model, and then add them to your ground truth for training a machine learning model, you do not want to define rules in such a way that they will produce overlapping entity mentions. For example, if you were to map both the intermediate class `FirstName` and the complex class `FullName` to the `PERSON` entity, then an occurrence of `John Doe, Jr.` would result in an overlapping mention.

## Rule editor tools

The rule editor provides some tools that help you to define rules.

- Dictionary

    Add a dictionary and assign it a class name. Any words that are found that match entries in the dictionary are automatically annotated with the assigned class.

- Regular expression

    A regular expression (regex) is a sequence of characters that define a search pattern. The regex tool that is included in the rule editor recognizes expressions that follow the `java.util.regex.Pattern` syntax. Here's a basic example:
    `[A-Z][a-z]*`: Finds capitalized words.

    `[A-Z]` matches any capital alphabetical letter (A through Z) and `[a-z]*` matches any lower-case alphabetical letter (a through z) zero or more times. The asterisk (*) is the character that defines the repeating setting (zero or more times).

    Consider using a free web-based regex utility to help you determine the right expression to use to capture the pattern you want to find.

    For example, your documents might have several references that are similar to the following phrases:

    ```
    35-year-old driver
    16-year-old learner
    ```
    {: screen}

    The syntax `n-year-old x` is a pattern that typically represents a person. You can define a regular expression rule to find phrases that match the `n-year-old x` pattern, and annotate them as `PERSON` entity mentions.
