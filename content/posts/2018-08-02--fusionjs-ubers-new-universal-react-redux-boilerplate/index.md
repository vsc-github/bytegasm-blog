---
title: Fusion.js Universal Web Framework by UBER opensourced
subTitle: My thoughts and review on Uber's new isomprphic web boilerplate based on react & redux.
category: "deep dives"
cover: Header.png
---

If you are reading this, you already know that there is a new 'framework' in town. This may sound like everyday news in the Javascript world, but before you roll your eyes and go on a twitter rant, let's see what all the *FUSSion* is about.


##**React, Angular, Vue and now Fusion?**
**NO!** Fusion.js is not a replacement for React. To be precise Fusion.js is **feature-rich-boilerplate** built on top of react & redux which tries to ease major pain points of modern Single Page Web Appications.

It's been few hours since the [launch of fusion.js](https://eng.uber.com/fusionjs/) so this is not a deep dive but a brief summary & first impressions on Fusion.js.

###**Server Side Rendering out of the box**
SSR-ing your SPA has always been a bit tricky. There are various boilerplates that provide you setups to render your app on the server and hydrate it on the client. But these setups are quite opinionated and are deserted after some time, leaving you on your own. Fusion.js supports **server-side-rendering right out of the box**. Which means, *isomorphic universal webapps* which render on server and hydrate in the browser and SEO friendly pages which load faster.

###**Code Splitting & HMR right away**
Bundle splitting on an SSRed react-redux SPA has always been a front-end developer's *wet dream*. But configuring webpack for it and getting it to work as intended in all major browsers has been a *nightmare*. Also, Hot Module reloading is a blessing for devs, right? Both supported out of the box in Fusion.js.

###**Plugin Based Architecture**
A single entry point architecture enables Fusion.js to run it's code universally on the client as well as on the server. Thus also enabling plugins to be universal too. It allows plugin developers to co-locate snippets of code based on the library the code pertains to, as opposed to the environment the code runs in.

This can be better understood by this graphic:

![plugins in fusion.js](https://cdn-images-1.medium.com/max/800/1*Vst7vvHUUP-Fbzccb9PSxQ.png)
plugins logic based on their logical grouping rather than based on where the code needs to be added.

###**Typed dependency injection**
Plugins  can expose *well-defined APIs as services* to other plugins, and a plugin's dependencies can easily be mocked during tests. This is especially important when dependencies are responsible for communicating with data storage infrastructure or when they relate to observability (e.g., logging, analytics, and metrics).

![dependency injection in  Fusion.js](https://cdn-images-1.medium.com/max/800/1*4isGmV2nTYUvKdNN-WM2UQ.png)


###**No more Express, welcome Koa**
Most of the SSR, code-splitting solutions out there are based on Express. Express has an API that encourages side effects which made complex response transformations difficult to encapsulate and test. Fusion.js however is **based on Koa**, which provides a more **unit-test friendly context-based API**, and an elegant and lightweight abstraction for request lifetime management based on the concept of downstreams and upstreams. Fusion.js core segregates network side effects from application state and leverages Koa and DI to achieve loose coupling between subsystems.

###**Test by your Taste**
Fusion.js support modern test tooling such as **Jest, Enzyme & Puppeteer**. Apart from these, it also provides tools to test plugins. The fusion-test-utils package allows mocking the server itself, making it possible to quickly run integration tests between any permutation of plugins and mocks.

###**What about styling?**
It's possible to use any CSS framework or library with Fusion.js. By default Fusion comes with support of **[Styletron](https://github.com/rtsao/styletron)**, a high performance atomic CSS library that is maintained by the Fusion.js team.

###**Component based routing**
Fusion apps can use the **fusion-plugin-react-router** to integrate routing features into the component tree. The plugin uses react-router under the hood, and exposes a similar API which allows you to add routing behavior anywhere in your component tree.

###**Other Goodies**
* Security: automatically setup CSRF protection on endpoints.
* Data fetching: supports RPC-driven composable data fetching and GraphQL/Apollo
* Quality metrics: easily consume server performance and browser performance logging, error logging and generic event streams
* I18N: Automatically set up efficient bundle-splitting-aware translation loading

###**My 2 cents:**
Open source projects from big companies always warm my heart. Being a front-end developer setting up SSRed, code-splitting setup on react, redux & express was one of the hardest challenges I've faced. So, seeing such setup open sourced which is also used on a large scale by Uber is really nice. 

Talking about Open Source, [dev.to is going Open Source on 8/8/18](https://dev.to/ben/the-devto-codebase-will-go-open-source-on-august-8-2kia). Yay!

We already have amazing modern web setups like [Next.js](https://github.com/zeit/next.js/), [Gatsby](https://www.gatsbyjs.org/), [Electrode](http://www.electrode.io/) , the more the merrier. I can't wait to use Fusion's in my next project and find out how it plays out. What do you think about Fusion.js?
