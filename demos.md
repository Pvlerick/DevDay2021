http GET http://localhost:8080/

using var client = new HttpClient();
var quote = await client.GetStringAsync($"http://localhost:8080");
Console.WriteLine(quote);
quote = await client.GetStringAsync($"http://localhost:8080");
Console.WriteLine(quote);

# Demo 1

dotnet new console --framework net5.0

# Demo 2

# Demo 3
awaitable snippet
await and run => block because IsCompleted is false
change it to true and run again, it works (and is synchronous now)
make it return a string

# Demo 4

add CW everywhere and show call to OnCompletion
continuation is what's after await in the caller!
Breakpoint after the await in Main and show the call stack

# Demo 5

Show ILSpy decompiled code
machine.builder.Start(ref machine) -> follow links in ILSpy -> stateMachine.MoveNext();
IAsyncStateMachine interface & fields to keep state (variables values) between steps
Add more calls to see that it moves from an if to a switch/case