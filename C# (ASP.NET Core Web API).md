# Install Packages:
## 1. dotnet tool install --global dotnet-ef
Purpose: Installs the EF Core Command Line Interface (CLI) globally on your machine.
### Why you need it:
- Lets you run dotnet ef commands in the terminal (outside Visual Studio):
  - dotnet ef migrations add InitialCreate
  - dotnet ef database update
- Works together with the EF Core Design and Tools packages.
Note: You only need to install this once globally.
```console
dotnet tool install --global dotnet-ef
```

<br>

## 2. Microsoft.EntityFrameworkCore.Design
Purpose:
This package contains design‑time tools for Entity Framework Core (EF Core).
It is mainly used when you run commands like migrations (`dotnet ef migrations add ...`, `dotnet ef database update`).
### Why you need it:
- Enables scaffolding and reverse engineering of databases.
- Provides code generation for migrations.
- Required to work with the EF Core CLI commands.
```console
dotnet add package Microsoft.EntityFrameworkCore.Design
```

<br>

## 3. Microsoft.EntityFrameworkCore.Tools
Purpose:
Contains additional tools and utilities for Entity Framework Core at design‑time.
### Why you need it:
- Allows you to use EF Core commands inside the Package Manager Console or with dotnet ef.
- Commands like Add-Migration, Update-Database, Remove-Migration are available because of this package.
```console
dotnet add package Microsoft.EntityFrameworkCore.Tools
```

<br>

## 4. Npgsql.EntityFrameworkCore.PostgreSQL
Purpose: This is the PostgreSQL database provider for EF Core.
### Why you need it:
- It allows your EF Core models to connect and interact with a PostgreSQL database.
- Adds PostgreSQL-specific functionality (types, LINQ support, etc.).
### Example:
When you configure your `DbContext`, you’ll use something like:
```console
options.UseNpgsql(Configuration.GetConnectionString("DefaultConnection"));
```
### To Install:
```console
dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL
```

<br>

## 5. BCrypt.Net-Next
Purpose: Provides hashing utilities (BCrypt algorithm) to securely hash and verify passwords.
### Why you need it:
- Instead of saving plain-text passwords, you hash them before saving:
```console
string hashed = BCrypt.Net.BCrypt.HashPassword("myPassword");
bool verified = BCrypt.Net.BCrypt.Verify("myPassword", hashed);
```
### To Install:
```console
dotnet add package BCrypt.Net-Next
```

<br>

## 6. Microsoft.AspNetCore.Authentication.JwtBearer
Purpose: Adds support for JWT (JSON Web Token) authentication in ASP.NET Core.
### Why you need it:
- Enables your API to validate and accept JWT tokens in requests.
- Essential for building secure APIs with login/authentication.
- Works with `services.AddAuthentication().AddJwtBearer(...)` in `Program.cs` or `Startup.cs`.
### Example:
```console
services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options => {
        options.TokenValidationParameters = new TokenValidationParameters {
            // validation settings
        };
    });
```
### To Install:
```console
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
```

OR

```console
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer --version 8.0.7
```

<br>

## 7. System.IdentityModel.Tokens.Jwt
Purpose: Contains APIs for creating, reading, and validating JWT tokens.
### Why you need it:
- Used when you want to issue a JWT from your API (like after a successful login):
```console
var token = new JwtSecurityToken(...);
string jwt = new JwtSecurityTokenHandler().WriteToken(token);
```
### To Install:
```console
dotnet add package System.IdentityModel.Tokens.Jwt
```
