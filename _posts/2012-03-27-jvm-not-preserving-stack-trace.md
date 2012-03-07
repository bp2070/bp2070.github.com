#JVM not preserving stack traces

I encountered an issue recently where the JVM was discarding the stack trace for a null pointer exception, so the only information being logged was that the exception had occured, but not where. After some investigation I found the cause to be the JVM performing some optimization which retains only the type of exception, not the stack trace. I found a helpful post on StackOverflow which pointed to the following flag that can be passed to prevent the JVM from performing this optimization:

-XX:-OmitStackTraceInFastThrow

It would be nice if the exception message would say that the stack trace was discarded due to an optimization and that this flag could be used to preserve it, as without knowing the cause it is confusing.
