# engageSPARK changes

This branch, es-master, only records these changes to the README, so that the bugfix-changes are not mixed up.

To get a PhantomJS usable with our selenium tests, checkout branch es-2.0 and build it as normally.

In includes these changes:

* 5f663b8b39138c0510a7acac153a86492373988f [fixes](https://github.com/ariya/phantomjs/issues/12506#issuecomment-61698339) file-uploads by skipping gesture-processing. Whenever 2.0.1 gets released, this fix should be included already.

You might get a weird error about file-uploads:

    E               WebDriverException: Message: Error - incompatible type of argument(s) in call to _uploadFile(); candidates were
    E                   _uploadFile(QString,QStringList)

In this case you need to disable the "_is_remote" property of the RemoteDriver for the duration of calling `sendKeys`.
By this you skip sending the files to be uploaded to PhantomJS via the Webdriver protocol.
Instead, only the path is sent to the browser, which is the normal behavior.
Unfortuantely, this entails that PhantomJS and the Seleniumtests must run on the same server, and you likely must send an absolute path.

---

# [PhantomJS](http://phantomjs.org) - Scriptable Headless WebKit

PhantomJS ([www.phantomjs.org](http://phantomjs.org)) is a headless WebKit scriptable with JavaScript. It is used by hundreds of [developers](http://phantomjs.org/buzz.html) and dozens of [organizations](http://phantomjs.org/users.html) for web-related development workflow.

The latest [stable release](http://phantomjs.org/release-2.0.html) is version 2.0.

**Note**: Please **do not** create a GitHub pull request **without** reading the [Contribution Guide](https://github.com/ariya/phantomjs/blob/master/CONTRIBUTING.md) first. Failure to do so may result in the rejection of the pull request.

## Use Cases

- **Headless web testing**. Lightning-fast testing without the browser is now possible! Various [test frameworks](http://phantomjs.org/headless-testing.html) such as Jasmine, Capybara, QUnit, Mocha, WebDriver, YUI Test, BusterJS, FuncUnit, Robot Framework, and many others are supported.
- **Page automation**. [Access and manipulate](http://phantomjs.org/page-automation.html) web pages with the standard DOM API, or with usual libraries like jQuery.
- **Screen capture**. Programmatically [capture web contents](http://phantomjs.org/screen-capture.html), including CSS, SVG and Canvas. Build server-side web graphics apps, from a screenshot service to a vector chart rasterizer.
- **Network monitoring**. Automate performance analysis, track [page loading](http://phantomjs.org/network-monitoring.html) and export as standard HAR format.

## Features

- **Multiplatform**, available on major operating systems: Windows, Mac OS X, Linux, and other Unices.
- **Fast and native implementation** of web standards: DOM, CSS, JavaScript, Canvas, and SVG. No emulation!
- **Pure headless (no X11) on Linux**, ideal for continuous integration systems. Also runs on Amazon EC2, Heroku, and Iron.io.
- **Easy to install**: [Download](http://phantomjs.org/download.html), unpack, and start having fun in just 5 minutes.

## Ecosystem

PhantomJS needs not be used only as a stand-alone tool. Check also some excellent related projects:

- [CasperJS](http://casperjs.org) enables easy navigation scripting and common high-level testing.
- [Poltergeist](https://github.com/jonleighton/poltergeist) allows running Capybara tests headlessly.
- [Guard::Jasmine](https://github.com/netzpirat/guard-jasmine) automatically tests Jasmine specs on Rails when files are modified.
- [GhostDriver](http://github.com/detro/ghostdriver/) complements Selenium tests with a PhantomJS WebDriver implementation.
- [PhantomRobot](https://github.com/datakurre/phantomrobot) runs Robot Framework acceptance tests in the background via PhantomJS.
- [Mocha-PhantomJS](https://github.com/metaskills/mocha-phantomjs) run Mocha tests using PhantomJS.

and many others [related projects](http://phantomjs.org/related-projects.html).

## Questions?

- Explore the complete [documentation](http://phantomjs.org/documentation/).
- Read tons of [user articles](http://phantomjs.org/buzz.html) on using PhantomJS.
- Join the [mailing-list](http://groups.google.com/group/phantomjs) and discuss with other PhantomJS fans.

PhantomJS is free software/open source, and is distributed under the [BSD license](http://opensource.org/licenses/BSD-3-Clause). It contains third-party code, see the included `third-party.txt` file for the license information on third-party code.

PhantomJS is created and maintained by [Ariya Hidayat](http://ariya.ofilabs.com/about) (Twitter: [@ariyahidayat](http://twitter.com/ariyahidayat)), with the help of [many contributors](https://github.com/ariya/phantomjs/contributors). Follow the official Twitter stream [@PhantomJS](http://twitter.com/PhantomJS) to get the frequent development updates.


