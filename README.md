# N E G A  T I C K E T
A typical setup in most ticketing system is to model the <strong>ticket request</strong> as a mutable object, with properties, fields, timestamps, and a <strong>status</strong> field that is manually moved from one state to another: when certain status transitions occur, you have certain business logic activate.  This approach has several problems:
* What if the request is in several states at once?
* What if several people are working on the same request at once?
* What if the workflow needs to dynamically change, halway through, based on new findings when working the request?
* What if certain requests require a large amount of workflow, and other requests require a small amount of workflow?
* What if you need fast reporting of all the timestamps of every workflow action performed on each request?

NegaTicket solves these problems, by keeping the mutable object representation for the request, and modeling each workflow item as a separate <strong>task</strong> that is immutable after being completed.

Your ticket's status is now mathematically defined: it is the <strong>sum</strong> of all active tasks, which means that it can also be considered in two states at once, if your workflow works that way.
