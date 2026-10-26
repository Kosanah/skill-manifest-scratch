
## REPO: angular-sample

### FILE: README.md
```
# Angular — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Angular** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `src/app/orders/orders.component.ts` — the sample itself, with comments on the pattern it shows

## Run / read

Open `src/app/orders/orders.component.ts` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: src/app/orders/orders.component.ts
```
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({ selector: 'app-orders', standalone: true, imports: [CommonModule], template: `<ul><li *ngFor="let o of orders">{{ o.name }} - {{ o.total }}</li></ul>` })
export class OrdersComponent {
  orders = [{ name: 'Order 1', total: 120 }, { name: 'Order 2', total: 45 }];
}

```


## REPO: aspnet-core-sample

### FILE: Program.cs
```
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddControllers();
var app = builder.Build();
app.MapGet("/health", () => Results.Ok(new { status = "ok" }));
app.MapControllers();
app.Run();

```

### FILE: README.md
```
# ASP.NET Core — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **ASP.NET Core** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Program.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Program.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: aws-sample

### FILE: OrderLambda.cs
```
using Amazon.Lambda.Core;
using Amazon.Lambda.APIGatewayEvents;

// AWS Lambda sample: API Gateway handler returning JSON.
public class OrderLambda
{
    public APIGatewayProxyResponse Get(APIGatewayProxyRequest req, ILambdaContext ctx)
    {
        var id = req.PathParameters?.GetValueOrDefault("id") ?? "1";
        return new APIGatewayProxyResponse { StatusCode = 200, Body = $"{{\"id\": \"{id}\", \"status\": \"Paid\"}}", Headers = new Dictionary<string, string> { ["Content-Type"] = "application/json" } };
    }
}

```

### FILE: README.md
```
# AWS — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **AWS** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `OrderLambda.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `OrderLambda.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: azure-devops-sample

### FILE: README.md
```
# Azure DevOps — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Azure DevOps** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `azure-pipelines.yml` — the sample itself, with comments on the pattern it shows

## Run / read

Open `azure-pipelines.yml` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: azure-pipelines.yml
```
trigger: [main]
pool: {vmImage: 'ubuntu-latest'}
steps:
  - task: DotNetCoreCLI@2
    inputs: {command: 'build', projects: '**/*.csproj'}
  - task: DotNetCoreCLI@2
    inputs: {command: 'test', projects: '**/*Tests.csproj'}

```


## REPO: azure-sample

### FILE: OrderFunction.cs
```
using Microsoft.Azure.Functions.Worker;
using Microsoft.Azure.Functions.Worker.Http;

// Azure Functions sample: HTTP-triggered function returning JSON.
public class OrderFunction
{
    [Function("GetOrder")]
    public HttpResponseData Get([HttpTrigger(AuthorizationLevel.Function, "get", Route = "orders/{id}")] HttpRequestData req, int id)
    {
        var res = req.CreateResponse(System.Net.HttpStatusCode.OK);
        res.WriteString(System.Text.Json.JsonSerializer.Serialize(new { id, status = "Paid" }));
        return res;
    }
}

```

### FILE: README.md
```
# Azure — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Azure** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `OrderFunction.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `OrderFunction.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: bootstrap-sample

### FILE: README.md
```
# Bootstrap — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Bootstrap** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `index.html` — the sample itself, with comments on the pattern it shows

## Run / read

Open `index.html` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: index.html
```
<!DOCTYPE html>
<html lang="en">
<head><meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1"><link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"><title>Orders</title></head>
<body><main class="container py-4"><h1>Orders</h1><div class="row g-3"><div class="col-md-4"><div class="card"><div class="card-body"><h2 class="card-title h5">Order 1</h2><p class="card-text">$120 — Paid</p><button class="btn btn-primary">View</button></div></div></div></div></main></body>
</html>

```


## REPO: cosmos-db-sample

### FILE: OrdersRepository.cs
```
using Microsoft.Azure.Cosmos;

// Cosmos DB sample: container query with a partition key, parameterized.
public class OrdersRepository
{
    private readonly Container _container;
    public OrdersRepository(CosmosClient client) => _container = client.GetContainer("app", "orders");
    public async Task<List<OrderDoc>> PaidAsync(string customerId)
    {
        var q = _container.GetItemQueryIterator<OrderDoc>(new QueryDefinition("SELECT * FROM c WHERE c.paid = true"), requestOptions: new QueryRequestOptions { PartitionKey = new PartitionKey(customerId) });
        var out_ = new List<OrderDoc>();
        while (q.HasMoreResults) out_.AddRange(await q.ReadNextAsync());
        return out_;
    }
}
public class OrderDoc { public string id { get; set; } = ""; public bool paid { get; set; } }

```

### FILE: README.md
```
# Cosmos DB — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Cosmos DB** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `OrdersRepository.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `OrdersRepository.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: csharp-sample

### FILE: Program.cs
```
using System;
using System.Linq;
using System.Threading.Tasks;

// Small C# sample: LINQ, async/await, records, pattern matching.
var orders = new[] { new Order(1, 120m, true), new Order(2, 45m, false) };
var total = orders.Where(o => o.Paid).Sum(o => o.Amount);
Console.WriteLine($"Paid total: {total:C}");
await Task.Delay(1);
record Order(int Id, decimal Amount, bool Paid);

```

### FILE: README.md
```
# C# — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **C#** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Program.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Program.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: css3-sample

### FILE: README.md
```
# CSS3 — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **CSS3** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `styles.css` — the sample itself, with comments on the pattern it shows

## Run / read

Open `styles.css` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: styles.css
```
:root { --gap: 1rem; --brand: #0b4f6c; }
.card { display: grid; gap: var(--gap); padding: 1rem; border: 1px solid #ccc; border-radius: 8px; }
@media (max-width: 600px) { .card { grid-template-columns: 1fr; } }
button:focus-visible { outline: 3px solid var(--brand); outline-offset: 2px; }

```


## REPO: docker-sample

### FILE: Dockerfile
```
# Docker sample: multi-stage build for a .NET app.
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "Sample.dll"]

```

### FILE: README.md
```
# Docker — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Docker** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Dockerfile` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Dockerfile` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: dotnet-sample

### FILE: README.md
```
# .NET — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **.NET** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Sample.csproj` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Sample.csproj` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: Sample.csproj
```
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net8.0</TargetFramework>
    <Nullable>enable</Nullable>
  </PropertyGroup>
</Project>

```


## REPO: entity-framework-core-sample

### FILE: Data/AppDbContext.cs
```
using Microsoft.EntityFrameworkCore;

public class AppDbContext : DbContext
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) {}
    public DbSet<Customer> Customers => Set<Customer>();
    protected override void OnModelCreating(ModelBuilder b)
    {
        b.Entity<Customer>().HasIndex(c => c.Email).IsUnique();
        b.Entity<Customer>().Property(c => c.Name).HasMaxLength(100).IsRequired();
    }
}
public class Customer { public int Id { get; set; } public string Name { get; set; } = ""; public string Email { get; set; } = ""; }

```

### FILE: README.md
```
# Entity Framework Core — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Entity Framework Core** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Data/AppDbContext.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Data/AppDbContext.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: fullstack-dotnet-developer-sample

### FILE: Dockerfile
```
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY . .
ENTRYPOINT ["dotnet", "Api.dll"]

```

### FILE: README-fullstack-note.md
```
Full-stack structure in this repo:
- api/ — ASP.NET Core Web API (see the portal sample for a larger version)
- web/ — React + TypeScript front end calling the API
- db/ — SQL Server schema + seed data
- Dockerfile + CI pipeline

This repo is the overview + front-end/API samples; the larger accessible portal repo shows the same stack end-to-end.

```

### FILE: README.md
```
# Full Stack .NET Developer — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Full Stack .NET Developer** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `README-fullstack-note.md` — the sample itself, with comments on the pattern it shows

## Run / read

Open `README-fullstack-note.md` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: api/Program.cs
```
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddControllers();
var app = builder.Build();
app.MapGet("/api/orders", () => new[] { new { id = 1, total = 120 } });
app.MapControllers();
app.Run();

```

### FILE: db/schema.sql
```
CREATE TABLE Orders (Id INT IDENTITY(1,1) PRIMARY KEY, Total DECIMAL(10,2) NOT NULL, Paid BIT NOT NULL DEFAULT 0);

```

### FILE: web/src/Orders.tsx
```
import { useEffect, useState } from 'react';
export function Orders() { const [orders, setOrders] = useState<any[]>([]); useEffect(() => { fetch('/api/orders').then(r => r.json()).then(setOrders).catch(() => setOrders([{id:1,total:120}])); }, []); return <ul>{orders.map(o => <li key={o.id}>Order {o.id} — ${o.total}</li>)}</ul>; }

```


## REPO: github-sample

### FILE: .github/workflows/ci.yml
```
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-dotnet@v4
        with: {dotnet-version: '8.0.x'}
      - run: dotnet build

```

### FILE: README.md
```
# GitHub — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **GitHub** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `.github/workflows/ci.yml` — the sample itself, with comments on the pattern it shows

## Run / read

Open `.github/workflows/ci.yml` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: gitlab-ci-sample

### FILE: .gitlab-ci.yml
```
stages: [build, test]
build:
  stage: build
  image: mcr.microsoft.com/dotnet/sdk:8.0
  script: [dotnet build]
test:
  stage: test
  image: mcr.microsoft.com/dotnet/sdk:8.0
  script: [dotnet test]

```

### FILE: README.md
```
# GitLab CI/CD — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **GitLab CI/CD** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `.gitlab-ci.yml` — the sample itself, with comments on the pattern it shows

## Run / read

Open `.gitlab-ci.yml` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: html5-sample

### FILE: README.md
```
# HTML5 — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **HTML5** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `index.html` — the sample itself, with comments on the pattern it shows

## Run / read

Open `index.html` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: index.html
```
<!DOCTYPE html>
<html lang="en">
<head><meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1"><title>Orders</title></head>
<body>
<header><h1>Orders</h1></header>
<main><section aria-labelledby="list-heading"><h2 id="list-heading">Recent orders</h2><table><caption>Recent orders</caption><thead><tr><th scope="col">ID</th><th scope="col">Total</th></tr></thead><tbody><tr><td>1</td><td>$120</td></tr></tbody></table></section></main>
</body>
</html>

```


## REPO: javascript-sample

### FILE: README.md
```
# JavaScript — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **JavaScript** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `src/orders.js` — the sample itself, with comments on the pattern it shows

## Run / read

Open `src/orders.js` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: src/orders.js
```
export async function fetchOrders(baseUrl) {
  const res = await fetch(`${baseUrl}/api/orders`);
  if (!res.ok) throw new Error(`Request failed: ${res.status}`);
  return res.json();
}

export function paidTotal(orders) {
  return orders.filter(o => o.paid).reduce((sum, o) => sum + o.total, 0);
}

```


## REPO: kafka-sample

### FILE: Producer.cs
```
using Confluent.Kafka;

// Kafka sample: producer publishing an order event to a topic.
public class OrderEventProducer
{
    private readonly IProducer<string, string> _producer;
    public OrderEventProducer(string bootstrap) => _producer = new ProducerBuilder<string, string>(new ProducerConfig { BootstrapServers = bootstrap }).Build();
    public Task ProduceAsync(string orderId, string json) => _producer.ProduceAsync("orders", new Message<string, string> { Key = orderId, Value = json });
}

```

### FILE: README.md
```
# Kafka — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Kafka** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Producer.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Producer.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: kubernetes-sample

### FILE: README.md
```
# Kubernetes — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Kubernetes** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `deployment.yaml` — the sample itself, with comments on the pattern it shows

## Run / read

Open `deployment.yaml` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: deployment.yaml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: sample-api
spec:
  replicas: 2
  selector:
    matchLabels: {app: sample-api}
  template:
    metadata:
      labels: {app: sample-api}
    spec:
      containers:
        - name: api
          image: sample-api:latest
          ports: [{containerPort: 8080}]
          resources:
            requests: {cpu: "100m", memory: "128Mi"}

```


## REPO: microservices-sample

### FILE: README.md
```
# Microservices — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Microservices** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Services/OrderService.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Services/OrderService.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: Services/OrderService.cs
```
// Microservice boundary sample: one service, one responsibility, own data model.
public interface IOrderService { Task<OrderDto> GetAsync(int id); }
public class OrderService : IOrderService
{
    public Task<OrderDto> GetAsync(int id) => Task.FromResult(new OrderDto(id, "Paid"));
}
public record OrderDto(int Id, string Status);

```


## REPO: mongodb-sample

### FILE: OrdersRepository.cs
```
using MongoDB.Driver;

// MongoDB sample: typed collection, filtered query, no SQL strings.
public class OrdersRepository
{
    private readonly IMongoCollection<OrderDoc> _col;
    public OrdersRepository(IMongoDatabase db) => _col = db.GetCollection<OrderDoc>("orders");
    public Task<List<OrderDoc>> PaidAsync() => _col.Find(o => o.Paid).ToListAsync();
}
public class OrderDoc { public string Id { get; set; } = ""; public decimal Total { get; set; } public bool Paid { get; set; } }

```

### FILE: README.md
```
# MongoDB — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **MongoDB** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `OrdersRepository.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `OrdersRepository.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: mvc-sample

### FILE: Controllers/HomeController.cs
```
using Microsoft.AspNetCore.Mvc;

public class HomeController : Controller
{
    public IActionResult Index() => View(new HomeViewModel("Hello from MVC", DateTime.UtcNow));
}
public record HomeViewModel(string Title, DateTime GeneratedAt);

```

### FILE: README.md
```
# MVC — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **MVC** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Controllers/HomeController.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Controllers/HomeController.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: postgresql-sample

### FILE: README.md
```
# PostgreSQL — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **PostgreSQL** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `schema.sql` — the sample itself, with comments on the pattern it shows

## Run / read

Open `schema.sql` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: schema.sql
```
-- PostgreSQL sample: table, index, and a parameterized query pattern.
CREATE TABLE orders (id SERIAL PRIMARY KEY, customer TEXT NOT NULL, total NUMERIC(10,2) NOT NULL, paid BOOLEAN NOT NULL DEFAULT FALSE);
CREATE INDEX ix_orders_customer ON orders (customer);
-- SELECT id, customer, total FROM orders WHERE paid = $1;

```


## REPO: react-sample

### FILE: README.md
```
# React — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **React** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `src/Orders.tsx` — the sample itself, with comments on the pattern it shows

## Run / read

Open `src/Orders.tsx` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: src/Orders.tsx
```
import { useState } from 'react';

export function Orders() {
  const [orders] = useState([{ id: 1, name: 'Order 1', total: 120 }]);
  return (<ul>{orders.map(o => <li key={o.id}>{o.name} — ${o.total}</li>)}</ul>);
}

```


## REPO: redis-sample

### FILE: CacheService.cs
```
using StackExchange.Redis;

// Redis sample: cache-aside pattern with a TTL, JSON payload.
public class CacheService
{
    private readonly IDatabase _db;
    public CacheService(IConnectionMultiplexer mux) => _db = mux.GetDatabase();
    public async Task<string?> GetAsync(string key) => await _db.StringGetAsync(key);
    public Task SetAsync(string key, string value) => _db.StringSetAsync(key, value, TimeSpan.FromMinutes(5));
}

```

### FILE: README.md
```
# Redis — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Redis** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `CacheService.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `CacheService.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```


## REPO: rest-apis-sample

### FILE: README.md
```
# REST APIs — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **REST APIs** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `openapi.yaml` — the sample itself, with comments on the pattern it shows

## Run / read

Open `openapi.yaml` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: openapi.yaml
```
openapi: 3.0.3
info:
  title: Orders API sample
  version: 1.0.0
paths:
  /api/orders/{id}:
    get:
      summary: Get an order
      parameters:
        - {name: id, in: path, required: true, schema: {type: integer}}
      responses:
        '200': {description: OK}
        '404': {description: Not found}

```


## REPO: sass-sample

### FILE: README.md
```
# Sass — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Sass** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `styles/_tokens.scss` — the sample itself, with comments on the pattern it shows

## Run / read

Open `styles/_tokens.scss` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: styles/_tokens.scss
```
$brand: #0b4f6c;
$gap: 1rem;
$radius: 8px;

@mixin card {
  padding: $gap;
  border: 1px solid #ccc;
  border-radius: $radius;
}

.card { @include card; color: $brand; }

```


## REPO: sql-server-sample

### FILE: README.md
```
# SQL Server — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **SQL Server** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `schema.sql` — the sample itself, with comments on the pattern it shows

## Run / read

Open `schema.sql` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: schema.sql
```
-- SQL Server sample: table, index, and a parameterized stored procedure.
CREATE TABLE dbo.Orders (Id INT IDENTITY(1,1) PRIMARY KEY, Customer NVARCHAR(100) NOT NULL, Total DECIMAL(10,2) NOT NULL, Paid BIT NOT NULL DEFAULT 0);
CREATE INDEX IX_Orders_Customer ON dbo.Orders (Customer);
GO
CREATE PROCEDURE dbo.GetPaidOrders AS SELECT Id, Customer, Total FROM dbo.Orders WHERE Paid = 1;
GO

```


## REPO: typescript-sample

### FILE: README.md
```
# TypeScript — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **TypeScript** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `src/orders.ts` — the sample itself, with comments on the pattern it shows

## Run / read

Open `src/orders.ts` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```

### FILE: src/orders.ts
```
export interface Order { id: number; customer: string; total: number; paid: boolean; }

export function paidTotal(orders: Order[]): number {
  return orders.filter(o => o.paid).reduce((sum, o) => sum + o.total, 0);
}

export type OrderStatus = 'Paid' | 'Pending' | 'Cancelled';

```


## REPO: web-api-sample

### FILE: Controllers/OrdersController.cs
```
using Microsoft.AspNetCore.Mvc;

[ApiController, Route("api/[controller]")]
public class OrdersController : ControllerBase
{
    [HttpGet("{id:int}")]
    public IActionResult Get(int id) => id <= 0 ? BadRequest("id must be positive") : Ok(new { id, status = "Paid" });
    [HttpPost]
    public IActionResult Create([FromBody] CreateOrderRequest req) => Created($"/api/orders/1", new { id = 1, req.Amount });
}
public record CreateOrderRequest(decimal Amount);

```

### FILE: README.md
```
# Web API — Portfolio Sample

**By Hari Krishna Kosana — Senior Full Stack .NET Developer**

Small, focused portfolio sample demonstrating **Web API** in isolation.
Fictional demo data only — not client work, not a production system.

## What to look at

- `Controllers/OrdersController.cs` — the sample itself, with comments on the pattern it shows

## Run / read

Open `Controllers/OrdersController.cs` and read it top to bottom; it is intentionally short so a reviewer can verify the skill in under two minutes.

Related: the full-stack sample is in `fullstack-dotnet-developer-sample`, and the larger end-to-end portal is at https://github.com/Kosanah/-accessible-dotnet-portal-sample

```
