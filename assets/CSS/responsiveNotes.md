These are good starters to a responsive and non-bloated CSS.
Found out about from these webpages:

https://alistapart.com/article/axiomatic-css-and-lobotomized-owls/
https://www.heydonworks.com/article/on-writing-less-damn-code
https://css-tricks.com/css-modules-part-1-need/
https://github.com/css-modules/css-modules#composition

https://github.com/css-modules/webpack-demo
^-------haven't used this, but I want to. look up just css modules on github

.grid {
	display: flex;
	flex-flow: row wrap;
}

.grid > * {
	flex-basis: 10em;
	flex-grow: 1;
}

The axiom is as follows: “All elements in the flow of the document that proceed other elements must receive a top margin of one line.”
This is the "lobotomized owl". It is in the form of an "adjacent sibling combinator", or "x + n"; a CSS selector (and expression) that says "if n-element follows x then do this".
*+*{
    margin-top: 1.5em;
}

p {
    font-size: 1em;
    line-height: 1.5em;
}

Assuming that your paragraphs’ font-size is 1 em and its line-height is 1.5, we just set a default margin of one line between all successive flow elements of all varieties occurring in any order.

To turn off in the flow :
.margins-off > * {
	margin-top: 0;
}

For compact half em margins between lines (you have to label w/e element with 'class="compact"'):
.compact * + * {
	margin-top: 0.75em;
}

For book-like, justified paragraphs:
p {
	text-align: justify;
}

p + p {
margin-top: 0;
text-indent: 2em;
}
