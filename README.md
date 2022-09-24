# Querying EF using DbSet

https://www.learnentityframeworkcore.com/dbset


//Order by lastname
var data = context.Authors.OrderBy(a => a.LastName);

// Return 1 fetching all columns from the table {First, FirstOrDefault}
// FirstOrDefault will return null
// First will not return null
var author = context.Authors.First();
Ex. SELECT TOP(1) [a].[AuthorId], [a].[FirstName], [a].[LastName] FROM [Authors] AS [a]

// Return single value with condition {Single, SingleOrDefault}
// SingleOrDefault will return null
// Single will not return null
var author = context.Authors.Single(a => a.AuthorId == 1);

// Method returning multiple results also return null {Find}
var author = context.Authors.Find(1);

// Select *
List<ProductHeader> headers = context.Products.Select(p => new ProductHeader{
    ProductId = p.ProductId,
    ProductName = p.ProductName
}).ToList();
  
// Adding single data to database
context.Authors.Add(author);

  
// Adding multiple data to database
context.Books.AddRange(books);
  
  
// Update data to database 
context.Authors.Update(author);
OR
var author = context.Authors.Find(1);
author.FirstName = "Bill";
  
// Delete data to database 
context.Authors.Remove(context.Authors.Find(1));
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

