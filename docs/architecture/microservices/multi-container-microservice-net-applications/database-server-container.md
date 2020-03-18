---
title: 컨테이너로 실행되는 데이터베이스 서버 사용
description: 컨테이너로 실행되는 데이터베이스 서버를 개발용으로만 사용하는 중요성을 이해합니다. 절대 프로덕션용이 아닙니다.
ms.date: 01/30/2020
ms.openlocfilehash: 0cbc933003aac10970814378c27e88b5cb0ddbe5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628529"
---
# <a name="use-a-database-server-running-as-a-container"></a>컨테이너로 실행되는 데이터베이스 서버 사용

온-프레미스 클러스터 또는 Azure SQL DB와 같은 클라우드의 PaaS 서비스에 있는 일반 독립 실행형 서버에 데이터베이스(SQL Server, PostgreSQL, MySQL 등)가 있을 수 있습니다. 그러나 개발 및 테스트 환경에서 데이터베이스를 컨테이너로 실행하는 것은 외부 종속성이 없고 간단히 `docker-compose up` 명령을 실행하면 전체 애플리케이션을 시작하기 때문에 편리합니다. 테스트가 예측 가능하도록 데이터베이스가 컨테이너에서 시작되고 항상 동일한 샘플 데이터로 채워지기 때문에 컨테이너로 해당 데이터베이스가 있다면 통합 테스트에 매우 유용합니다.

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>마이크로 서비스 관련 데이터베이스를 사용하여 컨테이너로 실행되는 SQL Server

eShopOnContainers에는 `sqldata`docker-compose.yml[ 파일에 정의된 것처럼 ](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml)라는 컨테이너가 있습니다. 이 컨테이너는 컨테이너가 필요한 모든 마이크로 서비스에 대해 SQL 데이터베이스를 포함하는 Linux용 SQL Server 인스턴스를 실행합니다.

마이크로 서비스의 핵심 요소는 각 마이크로 서비스가 관련된 데이터를 소유하고 있으므로 자체 데이터베이스를 포함해야 한다는 것입니다. 하지만 데이터베이스는 어디에나 있을 수 있습니다. 이 경우 Docker 메모리 요구 사항을 최대한 낮은 수준으로 유지하기 위해 모두 동일한 컨테이너에 있습니다. 이는 개발 및 테스트에는 적절한 솔루션이지만 프로덕션에는 적합하지 않습니다.

샘플 애플리케이션의 SQL Server 컨테이너는 `docker-compose up`을 실행할 때 실행되는 docker-compose.yml 파일에 다음 YAML 코드로 구성되어 있습니다. YAML 코드에는 제네릭 docker-compose.yml 파일 및 docker-compose.override.yml 파일의 통합된 구성 정보가 있습니다. (일반적으로 SQL Server 이미지에 관련된 기본 또는 고정 정보와 환경 설정을 분리합니다.)

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

비슷한 방식으로 `docker-compose`을 사용하는 대신 다음 `docker run` 명령은 해당 컨테이너를 실행할 수 있습니다.

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

그러나 eShopOnContainers와 같은 다중 컨테이너 애플리케이션을 배포하는 경우 애플리케이션에 필요한 모든 컨테이너를 배포할 수 있도록 `docker-compose up` 명령을 사용하는 것이 더 편리합니다.

처음으로 이 SQL Server 컨테이너를 시작할 때 컨테이너는 제공한 암호를 사용하여 SQL Server를 초기화합니다. 컨테이너로 SQL Server를 실행하면 SQL Server Management Studio, Visual Studio 또는 C\# 코드와 같은 일반 SQL 연결을 통해 연결하여 데이터베이스를 업데이트할 수 있습니다.

eShopOnContainers 애플리케이션은 다음 섹션에 설명한 대로 시작 시 데이터에서 시드하여 샘플 데이터와 함께 각 마이크로 서비스 데이터베이스를 초기화합니다.

SQL Server를 컨테이너로 실행하면 SQL Server의 인스턴스에 대한 액세스 권한이 없는 데모에 유용하지 않습니다. 앞서 언급한 대로 새 샘플 데이터를 시드하여 깔끔한 SQL Server 이미지 및 알려진 데이터에서 시작하는 통합 테스트를 실행할 수 있도록 개발 및 테스트 환경에 사용하는 것이 좋습니다.

### <a name="additional-resources"></a>추가 자료

- **Linux, Mac 또는 Windows에서 SQL Server Docker 이미지 실행** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- **sqlcmd를 사용하여 Linux에서 SQL Server 연결 및 쿼리** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a>웹 애플리케이션 시작 시 테스트 데이터로 시드

애플리케이션이 시작될 때 데이터베이스에 데이터를 추가하려면 Web API 프로젝트의 `Main` 클래스에서 `Program` 메서드에 다음과 같은 코드를 추가할 수 있습니다.

```csharp
public static int Main(string[] args)
{
    var configuration = GetConfiguration();

    Log.Logger = CreateSerilogLogger(configuration);

    try
    {
        Log.Information("Configuring web host ({ApplicationContext})...", AppName);
        var host = CreateHostBuilder(configuration, args);

        Log.Information("Applying migrations ({ApplicationContext})...", AppName);
        host.MigrateDbContext<CatalogContext>((context, services) =>
        {
            var env = services.GetService<IWebHostEnvironment>();
            var settings = services.GetService<IOptions<CatalogSettings>>();
            var logger = services.GetService<ILogger<CatalogContextSeed>>();

            new CatalogContextSeed()
                .SeedAsync(context, env, settings, logger)
                .Wait();
        })
        .MigrateDbContext<IntegrationEventLogContext>((_, __) => { });

        Log.Information("Starting web host ({ApplicationContext})...", AppName);
        host.Run();

        return 0;
    }
    catch (Exception ex)
    {
        Log.Fatal(ex, "Program terminated unexpectedly ({ApplicationContext})!", AppName);
        return 1;
    }
    finally
    {
        Log.CloseAndFlush();
    }
}
```

컨테이너를 시작하는 동안 마이그레이션을 적용하고 데이터베이스를 시드할 때 중요한 주의 사항이 있습니다. 어떤 이유로든 데이터베이스 서버를 사용하지 못할 수도 있으므로 서버를 사용할 수 있을 때까지 대기하는 동안 다시 시도를 처리해야 합니다. 이 재시도 논리는 다음 코드와 같이 `MigrateDbContext()` 확장 메서드에 의해 처리됩니다.

```cs
public static IWebHost MigrateDbContext<TContext>(
    this IWebHost host,
    Action<TContext,
    IServiceProvider> seeder)
      where TContext : DbContext
{
    var underK8s = host.IsInKubernetes();

    using (var scope = host.Services.CreateScope())
    {
        var services = scope.ServiceProvider;

        var logger = services.GetRequiredService<ILogger<TContext>>();

        var context = services.GetService<TContext>();

        try
        {
            logger.LogInformation("Migrating database associated with context {DbContextName}", typeof(TContext).Name);

            if (underK8s)
            {
                InvokeSeeder(seeder, context, services);
            }
            else
            {
                var retry = Policy.Handle<SqlException>()
                    .WaitAndRetry(new TimeSpan[]
                    {
                    TimeSpan.FromSeconds(3),
                    TimeSpan.FromSeconds(5),
                    TimeSpan.FromSeconds(8),
                    });

                //if the sql server container is not created on run docker compose this
                //migration can't fail for network related exception. The retry options for DbContext only
                //apply to transient exceptions
                // Note that this is NOT applied when running some orchestrators (let the orchestrator to recreate the failing service)
                retry.Execute(() => InvokeSeeder(seeder, context, services));
            }

            logger.LogInformation("Migrated database associated with context {DbContextName}", typeof(TContext).Name);
        }
        catch (Exception ex)
        {
            logger.LogError(ex, "An error occurred while migrating the database used on context {DbContextName}", typeof(TContext).Name);
            if (underK8s)
            {
                throw;          // Rethrow under k8s because we rely on k8s to re-run the pod
            }
        }
    }

    return host;
}
```

사용자 지정 CatalogContextSeed 클래스의 다음 코드는 데이터를 채웁니다.

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

통합 테스트를 실행할 때 통합 테스트와 일치하는 데이터를 생성하는 방법이 있어야 합니다. 컨테이너에서 실행되는 SQL Server의 인스턴스를 포함하여 처음부터 모두 만들 수 있다면 테스트 환경에 유용합니다.

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>컨테이너로 실행되는 EF Core InMemory 데이터베이스 및 SQL Server

테스트를 실행할 때 또 다른 방법은 Entity Framework InMemory 데이터베이스 공급자를 사용하는 것입니다. Web API 프로젝트에 있는 시작 클래스의 ConfigureServices 메서드에서 해당 구성을 지정할 수 있습니다.

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }

    // Other Startup code ...
}
```

하지만 중요한 점이 있습니다. 메모리 내 데이터베이스는 특정 데이터베이스에만 적용되는 여러 제약 조건을 지원하지 않습니다. 예를 들어 EF 핵심 모델의 열에 고유 인덱스를 추가하고 메모리 내 데이터베이스에 대해 테스트를 작성하여 중복 값을 추가할 수 있는지 확인할 수 있습니다. 하지만 메모리 내 데이터베이스를 사용하는 경우 열에서 고유 인덱스를 처리할 수 없습니다. 따라서 메모리 내 데이터베이스가 실제 SQL Server 데이터베이스와 동일하게 정확하게 작동하지 않습니다. 데이터베이스 관련 제약 조건을 에뮬레이트하지 않습니다.

그럼에도 메모리 내 데이터베이스는 테스트 및 프로토타입에 유용합니다. 하지만 특정 데이터베이스 구현의 동작을 고려하는 정확한 통합 테스트를 만들려는 경우 SQL Server와 같은 실제 데이터베이스를 사용해야 합니다. 이를 위해 컨테이너에서 SQL Server를 실행하는 것이 EF 코어 InMemory 데이터베이스 공급자보다 좋고 정확한 방법입니다.

## <a name="using-a-redis-cache-service-running-in-a-container"></a>컨테이너에서 실행되는 Redis 캐시 서비스 사용

개발 및 테스트 및 개념 증명 시나리오의 경우 컨테이너에서 Redis를 실행할 수 있습니다. 로컬 개발 컴퓨터뿐만 아니라 CI/CD 파이프라인의 테스트 환경의 경우 모든 종속성을 컨테이너에서 실행할 수 있기 때문에 이 시나리오는 편리합니다.

그러나 프로덕션에서 Redis를 실행할 때 PaaS(Platform as a Service)으로 실행되는 Redis Microsoft Azure와 같은 고가용성 솔루션을 검색하는 것이 좋습니다. 코드에서 연결 문자열을 변경하기만 하면 됩니다.

Redis는 Redis에서 Docker 이미지를 제공합니다. 해당 이미지는 다음 URL의 Docker 허브에서 제공됩니다.

<https://hub.docker.com/_/redis/>

명령 프롬프트에서 다음 Docker CLI 명령을 실행하여 Docker Redis 컨테이너를 직접 실행할 수 있습니다.

```console
docker run --name some-redis -d redis
```

연결된 표준 컨테이너가 연결된 컨테이너에 자동으로 제공되도록 Redis 이미지에는 expose:6379(Redis에서 사용하는 포트)가 포함됩니다.

eShopOnContainers에서 `basket-api` 마이크로 서비스는 컨테이너로 실행되는 Redis 캐시를 사용합니다. 다음 예제와 같이 해당 `basketdata` 컨테이너는 다중 컨테이너 *docker-compose.yml* 파일의 일부로 정의됩니다.

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

docker-compose.yml의 이 코드는 Redis 이미지를 기반으로 `basketdata`라는 컨테이너를 정의하고 포트 6379를 내부적으로 게시합니다. 즉, Docker 호스트 내에서 실행 중인 다른 컨테이너에서만 이 컨테이너에 액세스할 수 있습니다.

마지막으로 *docker-compose.override.yml* 파일에서 eShopOnContainers 샘플의 `basket-api` 마이크로 서비스는 해당 Redis 컨테이너에 사용할 연결 문자열을 정의합니다.

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

앞서 언급한 바와 같이 마이크로 서비스의 이름 `basketdata`는 Docker의 내부 네트워크 DNS에 의해 확인됩니다.

>[!div class="step-by-step"]
>[이전](multi-container-applications-docker-compose.md)
>[다음](integration-event-based-microservice-communications.md)
