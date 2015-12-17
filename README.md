# Onename Bootstrap

## Quick start

Several quick start options are available:

- [Download the latest release](https://github.com/twbs/bootstrap/archive/v4.0.0-alpha.2.zip).
- Clone the repo: `git clone https://github.com/twbs/bootstrap.git`.
- Install with [Bower](http://bower.io): `bower install bootstrap`.
- Install with [npm](https://www.npmjs.com): `npm install bootstrap`.
- Install with [Meteor](https://www.meteor.com): `meteor add twbs:bootstrap`.
- Install with [Composer](https://getcomposer.org): `composer require twbs/bootstrap`.
- Install with [NuGet](https://www.nuget.org): CSS: `Install-Package bootstrap -Pre` Sass: `Install-Package bootstrap.sass -Pre` (`-Pre` is only required until Bootstrap v4 has a stable release).

Read the [Getting started page](http://getbootstrap.com/getting-started/) for information on the framework contents, templates and examples, and more.

### What's included

Within the download you'll find the following directories and files, logically grouping common assets and providing both compiled and minified variations. You'll see something like this:

```
bootstrap/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   └── bootstrap.min.css.map
└── js/
    ├── bootstrap.js
    └── bootstrap.min.js
```

We provide compiled CSS and JS (`bootstrap.*`), as well as compiled and minified CSS and JS (`bootstrap.min.*`). CSS [source maps](https://developer.chrome.com/devtools/docs/css-preprocessors) (`bootstrap.*.map`) are available for use with certain browsers' developer tools.

## Documentation

Bootstrap's documentation, included in this repo in the root directory, is built with [Jekyll](http://jekyllrb.com) and publicly hosted on GitHub Pages at <http://getbootstrap.com>. The docs may also be run locally.

### Running documentation locally

1. If necessary, [install Jekyll](http://jekyllrb.com/docs/installation) (requires v3.0.x).
2. Install the Ruby-based syntax highlighter, [Rouge](https://github.com/jneen/rouge), with `gem install rouge`.
3. From the `/docs` directory, run `jekyll serve` in the command line.
4. Open `http://localhost:4000` in your browser, and voilà.

Learn more about using Jekyll by reading its [documentation](http://jekyllrb.com/docs/home/).

## Tooling setup

To use our Gruntfile and run our documentation locally, you'll need a copy of Bootstrap's source files, Node, and Grunt. Follow these steps and you should be ready to rock:

1. [Download and install Node](https://nodejs.org/download), which we use to manage our dependencies.
2. Install the Grunt command line tools, `grunt-cli`, with `npm install -g grunt-cli`.
3. Navigate to the root `/bootstrap` directory and run `npm install` to install our local dependencies listed in [package.json](https://github.com/twbs/bootstrap/blob/master/package.json).
4. [Install Ruby][install-ruby], install [Bundler][gembundler] with `gem install bundler`, and finally run `bundle install`. This will install all Ruby dependencies, such as Jekyll and plugins.
  - **Windows users:** Read [this unofficial guide](http://jekyll-windows.juthilo.com/) to get Jekyll up and running without problems.

When completed, you'll be able to run the various Grunt commands provided from the command line.

[install-ruby]: https://www.ruby-lang.org/en/documentation/installation/
[gembundler]: http://bundler.io/

## Using Grunt

Our Gruntfile includes the following commands and tasks:

| Task | Description |
| --- | --- |
| `grunt` | Run `grunt` to run tests locally and compile the CSS and JavaScript into `/dist`. **Uses [Sass](http://sass-lang.com/), [Autoprefixer][autoprefixer], and [UglifyJS](http://lisperator.net/uglifyjs/).** |
| `grunt dist` | `grunt dist` creates the `/dist` directory with compiled files. **Uses [Sass](http://sass-lang.com/), [Autoprefixer][autoprefixer], and [UglifyJS](http://lisperator.net/uglifyjs/).** |
| `grunt test` | Runs [scss-lint](https://github.com/brigade/scss-lint), [ESLint](http://eslint.org/) and [QUnit](http://qunitjs.com/) tests headlessly in [PhantomJS](http://phantomjs.org/) (used for CI). |
| `grunt docs` | Builds and tests CSS, JavaScript, and other assets which are used when running the documentation locally via `jekyll serve`. |
| `grunt watch` | This is a convenience method for watching just Sass files and automatically building them whenever you save. |

## Developing

1. Run `grunt` once to compile the CSS and JS into `/dist`.
1. In one tab, run `grunt watch` to continue syncing files as you edit them.
1. In another tab, `cd` into the `/docs` directory and run `jekyll serve` to serve up the documentation site with style guide.
1. Go to `localhost:4000` to view the documentation site.
1. As you update and save files, `grunt watch` will rebuild the assets. When it is done, you can refresh a page on the doc site and you will see the page has been updated with the new styles.