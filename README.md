# Key Code Code [<img src="https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg" alt="Key Code Code" width="90" height="90" align="right">][Key Code Code]

[![NPM Version][npm-img]][npm-url]
[![Build Status][cli-img]][cli-url]
[![Licensing][lic-img]][lic-url]
[![Changelog][log-img]][log-url]

[Key Code Code] lets you map [key codes] to [codes] in JavaScript.

```sh
npm install kcc
```

```js
// simulate clicks on non-button button-like elements
import keyCode from 'kcc';

document.addEventListener(
	'keypress',
	(event) => {
		if (event.keyCode === keyCode.Space || event.keyCode === keyCode.Enter) {
			const target = event.target.closest('[role=button]:not(button)');

			if (target) {
				event.preventDefault();

				event.target.dispatchEvent(
					new MouseEvent(
						'click',
						{
							bubbles: true,
							cancelable: true,
							view: target.ownerDocument.defaultView
						}
					)
				);
			}
		}
	}
);
```

---

When compiled as a JavaScript module using something like [rollup], [Key Code Code] realistically contributes about 1 byte for each character you use from the library.

[Key Code Code]: https://github.com/jonathantneal/kcc

[npm-url]: https://www.npmjs.com/package/kcc
[npm-img]: https://img.shields.io/npm/v/kcc.svg
[cli-url]: https://travis-ci.org/jonathantneal/kcc
[cli-img]: https://img.shields.io/travis/jonathantneal/kcc.svg
[lic-url]: LICENSE.md
[lic-img]: https://img.shields.io/badge/license-CC0--1.0-blue.svg
[log-url]: CHANGELOG.md
[log-img]: https://img.shields.io/badge/changelog-md-blue.svg

[codes]: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code
[key codes]: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode
[rollup]: http://rollupjs.org/
