# v3.0.0, 2018-??-??

v3.0.0 brings better and more consistent error handling!

All errors from workers include the `stack` property, and any others (Firefox has some extra non-standard properties). Since [normally stack traces are not sent from the worker to the main thread](https://github.com/mknichel/javascript-errors/blob/master/README.md#dedicated-workers), instead we capture the stack trace in the worker and manually send it to the main thread.

Additionally, the callback passed to `PromiseWorker.registerError` will now recieve Error objects directly, rather than ErrorEvent objects or weird non-standard things that are kind of like ErrorEvent objects. This is a breaking change to the API, necessitating the new major version.

# v2.2.1, 2017-12-02

Fix race condition where hostID was previously sometimes undefined.

# v2.2.0, 2017-03-28

Cross-browser consistency in error reporting from Shared Workers through PromiseWorker.registerError.

# v2.1.1, 2017-03-25

When using a Shared Worker, if the user closes a tab, we don't need to keep track of that hostID and MessagePort anymore.

# v2.1.0, 2017-03-24

Added support for Shared Workers.

# v2.0.2, 2017-03-14

Fix error reporting in Safari.

# v2.0.1, 2017-03-04

Fix error reporting.

# v2.0.0, 2017-03-02

First release of promise-worker-bi, forked from [promise-worker](https://github.com/nolanlawson/promise-worker) but adding support for sending messages from the worker to the host, rather than just from the host to the worker.