<!-- Please do not edit this file. Edit the `blah` field in the `package.json` instead. If in doubt, open an issue. -->


# github-calendar-parser

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Ask me anything](https://img.shields.io/badge/ask%20me-anything-1abc9c.svg)](https://github.com/IonicaBizau/ama) [![Version](https://img.shields.io/npm/v/github-calendar-parser.svg)](https://www.npmjs.com/package/github-calendar-parser) [![Downloads](https://img.shields.io/npm/dt/github-calendar-parser.svg)](https://www.npmjs.com/package/github-calendar-parser)

> Parses the GitHub contributions calendar SVG code into JSON.

## :cloud: Installation

```sh
$ npm i --save github-calendar-parser
```


## :clipboard: Example



```js
const parse = require("github-calendar-parser");

var svg = `<svg width="721" height="110" class="js-calendar-graph-svg">
  <g transform="translate(20, 20)">
      <g transform="translate(0, 0)">
          <rect class="day" width="11" height="11" y="39" fill="#1e6823" data-count="78" data-date="2014-12-31"/>
          <rect class="day" width="11" height="11" y="52" fill="#d6e685" data-count="6" data-date="2015-01-01"/>
          <rect class="day" width="11" height="11" y="65" fill="#d6e685" data-count="1" data-date="2015-01-02"/>
          <rect class="day" width="11" height="11" y="78" fill="#d6e685" data-count="21" data-date="2015-01-03"/>
      </g>
      <g transform="translate(13, 0)">
          <rect class="day" width="11" height="11" y="0" fill="#8cc665" data-count="40" data-date="2015-01-04"/>
          <rect class="day" width="11" height="11" y="13" fill="#8cc665" data-count="27" data-date="2015-01-05"/>
          <rect class="day" width="11" height="11" y="26" fill="#8cc665" data-count="27" data-date="2015-01-06"/>
          <rect class="day" width="11" height="11" y="39" fill="#44a340" data-count="57" data-date="2015-01-07"/>
          <rect class="day" width="11" height="11" y="52" fill="#8cc665" data-count="0" data-date="2015-01-08"/>
          <rect class="day" width="11" height="11" y="65" fill="#8cc665" data-count="3" data-date="2015-01-09"/>
          <rect class="day" width="11" height="11" y="78" fill="#d6e685" data-count="2" data-date="2015-01-10"/>
      </g>
  </g>
</svg>`;

console.log(parse(svg));
// =>
// { last_year: 262,
//   longest_streak: 9,
//   longest_streak_range: [ 2014-12-31T00:00:00.000Z, 2015-01-07T00:00:00.000Z ],
//   current_streak: 2,
//   current_streak_range: [ 2015-01-09T00:00:00.000Z, 2015-01-10T00:00:00.000Z ],
//   weeks: [ [ [Object], [Object], [Object], [Object] ] ],
//   days:
//    [ { fill: '#1e6823',
//        date: 2014-12-31T00:00:00.000Z,
//        count: 78,
//        level: 4 },
//      ...
//      { fill: '#d6e685',
//        date: 2015-01-10T00:00:00.000Z,
//        count: 2,
//        level: 1 } ],
//   last_contributed: 2015-01-10T00:00:00.000Z }
```



## :question: Get Help

There are few ways to get help:

 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:


## :memo: Documentation


### `parseGitHubCalendarSvg(input)`
Parses the SVG input (as string).

#### Params

- **String** `input`: The SVG code of the contributions calendar.

#### Return
- **Object** An object containing:
 - `last_year` (Number): The total contributions in the last year.
 - `longest_streak` (Number): The longest streak.
 - `longest_streak_range` (Array): An array of two date objects representing the date range.
 - `current_streak` (Number): The current streak.
 - `current_streak_range` (Array): An array of two date objects representing the date range.
 - `days` (Array): An array of day objects:
      - `fill` (String): The hex color.
      - `date` (Date): The day date.
      - `count` (Number): The number of commits.
      - `level` (Number): A number between 0 and 4 (inclusive) representing the contribution level (more commits, higher value).
 - `weeks` (Array): The day objects grouped by weeks (arrays).
 - `last_contributed` (Date): The last contribution date.



## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

 - Starring and sharing the projects you like :rocket:
 - [![Buy me a book][badge_amazon]][amazon]—I love books! I will remember you after years if you buy me one. :grin: :book:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)

Thanks! :heart:


## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:


 - [`github-calendar`](https://github.com/IonicaBizau/github-calendar#readme)—Embed your GitHub contributions calendar anywhere.

## :scroll: License

[MIT][license] © [Ionică Bizău][website]

[badge_patreon]: http://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: http://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: http://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: http://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2016#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
