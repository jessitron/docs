---
id: dark-backend-components
title: Components
sidebar_label: Components
---

When building in Dark, you are able to create five major backend components, called handlers:

- API Endpoints (REST)
- Background workers (with built in event/queue system)
- Scheduled jobs/cron
- Persistent Datastores (key-value/hashmap)
- REPLs (internal tools)

These components live on your canvas. They are created from the sidebar, or by hitting cmd-k to bring up the omnibox.

![assests/backend/image2.png](assets/backend/image2.png)

Dark code is meant to be written in these handlers. We always recommend writing code within these components, and then extracting that code into a function, using alt-x, as needed. Code written in Dark is expression based, and as you add an expression it will automatically create blanks for the parameters it takes. If you delete an expression, the parameters will also be removed.

These components **do not** require you to set up any additional infrastructure or deployment processes. As soon as you create them, they’re available and update as you write code (deployless). Each handler is of one of these types, and has a name as well as additional information. You can see examples of each component [here](https://darklang.com/a/sample-helloworld).

All of these components support core Dark functionality:

- Trace data & live values (see: [Trace Driven Development](trace-driven-development.md)).
- Implicit returns & pipelines (see: [Functional Aspects of Dark](functional-aspects.md)).
- Autocomplete (i.e. typing **DB::**) will return all the datastore functions. This also works by type.

More on each type is below, but we recommend continuing to [Trace Driven Development](trace-driven-development.md) and coming back when you are creating an endpoint.

---

## Canvas

In Dark, your backend components appear in the browser, on a canvas. These are at: [https://darklang.com/a/username](https://darklang.com/a/username) or [https://darklang.com/a/username-canvasname](https://darklang.com/a/username-canvasname). We intend for you to only have one canvas per company or entirely separate project. You can create any canvas by navigating to it.

Your endpoints would appear at: [https://username-canvasname.builtwithdark.com/route](https://username-canvasname.builtwithdark.com/route) (we can help you set up DNS if you want another domain to point at your canvas).

You can navigate the canvas via the left-hand sidebar, or via the omnibox (accessible using cmd/ctrl-k).

---

## REST API Endpoints

- If you hit an endpoint that does not exist (see: [Trace Driven Development](trace-driven-development.md)), the endpoint will appear in the 404 section.
- Support the standard REST protocols (GET, POST, PATCH, DELETE, PUT).
- Accept url parameters (ex: /profile/:username) and appear as variables within the handler.
- Have implicit returns (see: [Functional Aspects of Dark](functional-aspects.md)), and return JSON by default.
- All traces are available as dots on the LHS. If you do not have a trace selected, you will see a spinner for all live values.

## Background Workers

- Workers receive events via the **emit** expression, and will appear in the 404 section if you emit to a non-existent worker.
- Run asynchronously and retry in case of failure.

## CRON

- Runs on a given schedule, selected by developer (every minute, hour, week, etc).

## REPL

- Is triggered only by the developer and frequently relies on play buttons (see [Trace Driven Development](trace-driven-development.md)).

## Persistent Datastores

In Dark, all datastores are a key-value store - a persistent hashmap/dictionary (not a relational database). When looking at a Datastore you’ll see the schema, all handlers that call the datastore, how many entries are in it, and a sample entry.

![assets/backend/image3.png](assets/backend/image3.png)

[Detailed datastore information](datastores.md).

## Deleted

If you delete a handler, we save that code for you in the Deleted section of your canvas. Everything you delete is sorted by type, and will remain in that section until you remove it.

![assets/backend/Screen_Shot_2020-01-07_at_4.00.20_PM.png](assets/backend/Screen_Shot_2020-01-07_at_4.00.20_PM.png)
