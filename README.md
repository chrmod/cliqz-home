# cliqz-home

This project is used by CLIQZ Frontend Team to experiment with various
Javascript frameworks and identify which one is most suitable for CLIQZ browser
New Tab page.

We are evaluating:
* [pure javascript](./packages/cliqz-home-native)
* [glimmer](./packages/cliqz-home-glimmer)
* [react](./packages/cliqz-home-react)
* [vue](./packages/cliqz-home-vue)
* [svelte](./packages/raureif-svelte)

## Testing setup

Each individual framework has its own subproject in `packages` directory.

To build and start the test application run:

```
npm install
npm start
```

It will start development server at http://localhost:3000/


Tests can be performed only in CLIQZ browser. Please download one from:
[https://cliqz.com](https://cliqz.com)

On top of CLIQZ browser, a special version of CLIQZ extension has to be loaded.
Please download it from [here](http://cdn2.cliqz.com/update/browser_beta/Cliqz.1.18.0.1b145.xpi)

Important, CLIQZ addons automatically update and updated version will not allow the test.
If this happens, please reinstall the addon from above.
(you can check addon version in `about:support` - the only working version is 1.18.0.1b145)

## Testing

Start your project of choice and open [http://localhost:3000](http://localhost:3000)
in CLIQZ browser with development addon installed.

Refresh page couple times so benchmark data can be gathers or open
[http://localhost:3000/#30](http://localhost:3000/#30) - which will reload
the page automatically 30 times in the row.

When done, open browser Web Console (Tools > Web Developer > Web Console)

and type `benchmark.compare()` to see the test results.

Run same procedure for other test projects to evaluate which one works best.


**Important** tests must be run with Web Console turned off. Otherwise results
will be much slower than in real use case.

## Findings

So far, we've identified the given order of rendering speed:

native > svelte > vue / react > glimmer


