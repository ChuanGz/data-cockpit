# Data Cockpit

Data Cockpit is a small .NET library for building CRUD-oriented services on top of a domain model and an Entity Framework Core data layer. The repository separates the core CRUD abstractions from the EF Core implementation so applications can reuse a consistent repository shape across multiple entities.

## Highlights

- Generic CRUD contracts for application-facing models
- Reusable EF Core repository base implementation
- Soft-delete support through a shared entity base
- AutoMapper-based mapping between data entities and domain models
- Split packages for core abstractions and EF Core integration

## Repository Layout

- `DataCockpit`: core abstractions such as `ICrud`, `IRepository`, model base types, and shared helpers
- `DataCockpit.EfCore`: EF Core-specific repository infrastructure and query support
- `DataCockpit.sln`: solution file for the library projects

## Tech Stack

- .NET 7
- Entity Framework Core 7
- AutoMapper

## Build

```bash
dotnet build DataCockpit.sln
```

## Design Overview

- The core project defines generic model and repository contracts that stay independent from database concerns.
- The EF Core project provides a reusable `DbRepositoryBase` that handles querying, mutation, mapping, and soft-delete behavior.
- The repository design is useful when you want a thin internal CRUD library instead of repeating the same repository plumbing in multiple services.

## Notes

- This repository is best suited for internal application use rather than as a full-featured public package.
- The current implementation targets .NET 7 and can be modernized further if the library becomes an actively maintained shared dependency.
