# Basic Selectors

###### Type Selectors

selecting an element by tag name. for example:

- p { ... }
- text { ... }
- a { ... }
- div { ... }

###### Class Selectors

selecting an element by class value assigned through class attribute of the element.

to do so, we should type a dot and write the name of class after it.

say we have the following element which its class name is (( test-css-class-name )):

```html
<p class="test-css-class-name" >Test Text</p>
```

to style it in CSS we can select it as following:

- .test-css-class-name { ... }

###### Id Selector

to select an element by id value assigned through id attribute of the element.

to do so, we should type a sharp and write the value of id after it.

say we have the following element which its class name is (( test-css-class-name )):

```html
<p id="test-id" >Test Text</p>
```

to style it in CSS we can select it as following:

- #test-id { ... }



***

# Combinators

###### Descendant Combinator

to use more than 2 selectors we can combine the with space, like bellow examples:

- .class-name p { ... }
  - this combination selects all ((p)) tags that their main parent is an element with class name ((class-name)).
- #id1 .class-name { ... }
  - this combination selects all elements with class name ((class-name)) that their main parent is an element with id value ((id1)).

###### Child Combinator

to use more than 2 selectors we can combine the with ((>)), like bellow examples:

- .class-name > p { ... }
  - this combination selects all immediate child elements of type ((p)), that their first parent is an element with class name ((class-name)).
- #id1 > .class-name { ... }
  - this combination selects all immediate child elements with class name ((class-name)), that their first parent is an element with id value ((id1)).

###### Sibling Combinator

to use more than 2 selectors we can combine the with ((+)), like bellow examples:

- .class-name + p { ... }
  - this combination selects element of type ((p)) adjacent to an element with class name ((class-name)).
  - in HTML that ((p)) tag is selected which is the next sibling of an element with class name ((class-name)).
- #id1 + .class-name { ... }
  - this combination selects element with class name ((class-name))  adjacent to an element with id value ((id1)).
  - in HTML that element with class name ((class-name)) is selected which is the next sibling of an element with id value ((id1)).

###### General Sibling Combinator

to use more than 2 selectors we can combine the with ((~)), like bellow examples:

- .class-name ~ p { ... }
  - this combination selects all sibling elements of type ((p)) in same level of an element with class name ((class-name)).
  - in HTML those ((p)) tags are selected which are the next sibling of an element with class name ((class-name)).
- #id1 ~ .class-name { ... }
  - this combination selects all sibling elements with class name ((class-name)) in same level of an element with id value ((id1)).
  - in HTML those elements with class name ((class-name)) are selected which are the next sibling of an element with id value ((id1)).



***

