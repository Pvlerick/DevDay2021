http GET http://localhost:8080/

using var client = new HttpClient();
var quote = await client.GetStringAsync($"http://localhost:8080");
Console.WriteLine(quote);
quote = await client.GetStringAsync($"http://localhost:8080");
Console.WriteLine(quote);