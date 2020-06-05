---
title: 데이터 액세스 및 관리
description: ASP.NET Web Forms 및 Blazor에서 데이터에 액세스 하 고 처리 하는 방법에 대해 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 04/26/2020
ms.openlocfilehash: b9805da60722de1b5d4f91107e856f647f7564a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446480"
---
# <a name="work-with-data"></a><span data-ttu-id="67217-103">데이터 작업</span><span class="sxs-lookup"><span data-stu-id="67217-103">Work with data</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="67217-104">데이터 액세스는 ASP.NET Web Forms 앱의 백본입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-104">Data access is the backbone of an ASP.NET Web Forms app.</span></span> <span data-ttu-id="67217-105">웹에 대 한 양식을 작성 하는 경우 해당 데이터는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="67217-105">If you're building forms for the web, what happens to that data?</span></span> <span data-ttu-id="67217-106">Web Forms에서 데이터베이스와 상호 작용 하는 데 사용할 수 있는 여러 데이터 액세스 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-106">With Web Forms, there were multiple data access techniques you could use to interact with a database:</span></span>

- <span data-ttu-id="67217-107">Data Sources</span><span class="sxs-lookup"><span data-stu-id="67217-107">Data Sources</span></span>
- <span data-ttu-id="67217-108">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="67217-108">ADO.NET</span></span>
- <span data-ttu-id="67217-109">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="67217-109">Entity Framework</span></span>

<span data-ttu-id="67217-110">데이터 원본은 Web Forms 페이지에 놓고 다른 컨트롤과 같이 구성할 수 있는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-110">Data Sources were controls that you could place on a Web Forms page and configure like other controls.</span></span> <span data-ttu-id="67217-111">Visual Studio는 컨트롤을 구성 하 고 Web Forms 페이지에 바인딩하는 데 사용할 수 있는 친숙 한 대화 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-111">Visual Studio provided a friendly set of dialogs to configure and bind the controls to your Web Forms pages.</span></span> <span data-ttu-id="67217-112">"코드 부족" 또는 "코드 없음" 방식을 활용 하는 개발자는 Web Forms 처음 출시 될 때이 기술을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-112">Developers who enjoy a "low code" or "no code" approach preferred this technique when Web Forms was first released.</span></span>

![Data Sources](media/data/datasources.png)

<span data-ttu-id="67217-114">ADO.NET는 데이터베이스와 상호 작용 하는 하위 수준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-114">ADO.NET is the low-level approach to interacting with a database.</span></span> <span data-ttu-id="67217-115">앱에서 상호 작용 하기 위해 명령, 레코드 집합 및 데이터 집합을 사용 하 여 데이터베이스에 대 한 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-115">Your apps could create a connection to the database with Commands, Recordsets, and Datasets for interacting.</span></span> <span data-ttu-id="67217-116">그런 다음 결과를 많은 코드 없이 화면에 있는 필드에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-116">The results could then be bound to fields on screen without much code.</span></span> <span data-ttu-id="67217-117">이 방법의 단점은 각 ADO.NET 개체 집합 ( `Connection` , `Command` 및 `Recordset` )이 데이터베이스 공급 업체에서 제공 하는 라이브러리에 바인딩 되었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-117">The drawback of this approach was that each set of ADO.NET objects (`Connection`, `Command`, and `Recordset`) was bound to libraries provided by a database vendor.</span></span> <span data-ttu-id="67217-118">이러한 구성 요소를 사용 하면 코드가 고정 되어 다른 데이터베이스로 마이그레이션하기 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="67217-118">Use of these components made the code rigid and difficult to migrate to a different database.</span></span>

## <a name="entity-framework"></a><span data-ttu-id="67217-119">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="67217-119">Entity Framework</span></span>

<span data-ttu-id="67217-120">EF (Entity Framework)는 .NET Foundation에서 유지 관리 되는 오픈 소스 개체-관계형 매핑 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-120">Entity Framework (EF) is the open source object-relational mapping framework maintained by the .NET Foundation.</span></span> <span data-ttu-id="67217-121">처음에 .NET Framework와 함께 출시 된 EF를 사용 하면 데이터베이스 연결, 저장소 스키마 및 상호 작용에 대 한 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-121">Initially released with .NET Framework, EF allows for generating code for the database connections, storage schemas, and interactions.</span></span> <span data-ttu-id="67217-122">이 추상화를 사용 하면 앱의 비즈니스 규칙에 집중 하 고 데이터베이스를 신뢰할 수 있는 데이터베이스 관리자가 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-122">With this abstraction, you can focus on your app's business rules and allow the database to be managed by a trusted database administrator.</span></span> <span data-ttu-id="67217-123">.NET Core에서는 EF Core 이라는 업데이트 된 버전의 EF를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-123">In .NET Core, you can use an updated version of EF called EF Core.</span></span> <span data-ttu-id="67217-124">EF Core 명령줄 도구를 사용 하 여 사용할 수 있는 일련의 명령을 사용 하 여 코드와 데이터베이스 간의 상호 작용을 생성 하 고 유지 관리 하는 데 도움이 됩니다 `dotnet ef` .</span><span class="sxs-lookup"><span data-stu-id="67217-124">EF Core helps generate and maintain the interactions between your code and the database with a series of commands that are available for you using the `dotnet ef` command-line tool.</span></span> <span data-ttu-id="67217-125">데이터베이스 작업을 수행 하는 몇 가지 샘플을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-125">Let's take a look at a few samples to get you working with a database.</span></span>

### <a name="ef-code-first"></a><span data-ttu-id="67217-126">EF Code First</span><span class="sxs-lookup"><span data-stu-id="67217-126">EF Code First</span></span>

<span data-ttu-id="67217-127">데이터베이스 상호 작용 빌드를 신속 하 게 시작 하는 방법은 사용할 클래스 개체부터 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-127">A quick way to get started building your database interactions is to start with the class objects you want to work with.</span></span> <span data-ttu-id="67217-128">EF는 클래스에 적합 한 데이터베이스 코드를 생성 하는 데 도움이 되는 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-128">EF provides a tool to help generate the appropriate database code for your classes.</span></span> <span data-ttu-id="67217-129">이 방법을 "Code First" 개발 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-129">This approach is called "Code First" development.</span></span> <span data-ttu-id="67217-130">`Product`Microsoft SQL Server와 같은 관계형 데이터베이스에 저장 하려는 샘플 storefront 앱에 대 한 다음 클래스를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="67217-130">Consider the following `Product` class for a sample storefront app that we want to store in a relational database like Microsoft SQL Server.</span></span>

```csharp
public class Product
{
    public int Id { get; set; }

    [Required]
    public string Name { get; set; }

    [MaxLength(4000)]
    public string Description { get; set; }

    [Range(0, 99999,99)]
    [DataType(DataType.Currency)]
    public decimal Price { get; set; }
}
```

<span data-ttu-id="67217-131">제품에는 기본 키와 데이터베이스에 생성 되는 세 가지 추가 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-131">Product has a primary key and three additional fields that would be created in our database:</span></span>  

- <span data-ttu-id="67217-132">EF는 규칙에 `Id` 따라 속성을 기본 키로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-132">EF will identify the `Id` property as a primary key by convention.</span></span>
- <span data-ttu-id="67217-133">`Name`텍스트 저장소로 구성 된 열에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67217-133">`Name` will be stored in a column configured for text storage.</span></span> <span data-ttu-id="67217-134">`[Required]`이 속성을 데코레이팅하는 특성은 `not null` 이 선언 된 속성 동작을 강제 적용 하는 데 도움이 되는 제약 조건을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-134">The `[Required]` attribute decorating this property will add a `not null` constraint to help enforce this declared behavior of the property.</span></span>
- <span data-ttu-id="67217-135">`Description`는 텍스트 저장소로 구성 된 열에 저장 되며, 특성에 의해 결정 된 대로 최대 길이가 4000 자로 구성 됩니다 `[MaxLength]` .</span><span class="sxs-lookup"><span data-stu-id="67217-135">`Description` will be stored in a column configured for text storage, and have a maximum length configured of 4000 characters as dictated by the `[MaxLength]` attribute.</span></span> <span data-ttu-id="67217-136">데이터베이스 스키마는 `MaxLength` 데이터 형식을 사용 하 여 라는 열로 구성 됩니다 `varchar(4000)` .</span><span class="sxs-lookup"><span data-stu-id="67217-136">The database schema will be configured with a column named `MaxLength` using data type `varchar(4000)`.</span></span>
- <span data-ttu-id="67217-137">`Price`속성이 통화로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67217-137">The `Price` property will be stored as currency.</span></span> <span data-ttu-id="67217-138">`[Range]`특성은 선언 된 최소값과 최대값 이외의 데이터 저장을 방지 하기 위해 적절 한 제약 조건을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-138">The `[Range]` attribute will generate appropriate constraints to prevent data storage outside of the minimum and maximum values declared.</span></span>

<span data-ttu-id="67217-139">데이터베이스에 대 `Product` 한 연결 및 변환 작업을 정의 하는 데이터베이스 컨텍스트 클래스에이 클래스를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-139">We need to add this `Product` class to a database context class that defines the connection and translation operations with our database.</span></span>

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

<span data-ttu-id="67217-140">`MyDbContext`클래스는 클래스에 대 한 액세스 및 변환을 정의 하는 속성 하나를 제공 합니다 `Product` .</span><span class="sxs-lookup"><span data-stu-id="67217-140">The `MyDbContext` class provides the one property that defines the access and translation for the `Product` class.</span></span>  <span data-ttu-id="67217-141">응용 프로그램은 클래스의 메서드에서 다음 항목을 사용 하 여 데이터베이스와의 상호 작용을 위해이 클래스를 구성 합니다 `Startup` `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="67217-141">Your application configures this class for interaction with the database using the following entries in the `Startup` class's `ConfigureServices` method:</span></span>

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

<span data-ttu-id="67217-142">위의 코드는 지정 된 연결 문자열을 사용 하 여 SQL Server 데이터베이스에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67217-142">The preceding code will connect to a SQL Server database with the specified connection string.</span></span> <span data-ttu-id="67217-143">*Appsettings* 파일, 환경 변수 또는 기타 구성 저장 위치에 연결 문자열을 저장 하 고 포함 된 문자열을 적절 하 게 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-143">You can place the connection string in your *appsettings.json* file, environment variables, or other configuration storage locations and replace this embedded string appropriately.</span></span>

<span data-ttu-id="67217-144">그런 다음, 다음 명령을 사용 하 여이 클래스에 적절 한 데이터베이스 테이블을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-144">You can then generate the database table appropriate for this class using the following commands:</span></span>

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

<span data-ttu-id="67217-145">첫 번째 명령은 라는 새 EF Migration로 데이터베이스 스키마에 대 한 변경 내용을 정의 합니다 `Create Product table` .</span><span class="sxs-lookup"><span data-stu-id="67217-145">The first command defines the changes you're making to the database schema as a new EF Migration called `Create Product table`.</span></span>  <span data-ttu-id="67217-146">마이그레이션은 새 데이터베이스 변경 내용을 적용 하 고 제거 하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-146">A Migration defines how to apply and remove your new database changes.</span></span>

<span data-ttu-id="67217-147">일단 적용 되 면 `Product` 데이터베이스에 간단한 테이블이 있고 데이터베이스 스키마를 관리 하는 데 도움이 되는 몇 가지 새로운 클래스가 프로젝트에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-147">Once applied, you have a simple `Product` table in your database and some new classes added to the project that help manage the database schema.</span></span>  <span data-ttu-id="67217-148">이러한 생성 된 클래스는 기본적으로 *마이그레이션*이라는 새 폴더에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-148">You can find these generated classes, by default, in a new folder called *Migrations*.</span></span>  <span data-ttu-id="67217-149">클래스를 변경 `Product` 하거나 데이터베이스와 상호 작용 하는 데 더 많은 관련 클래스를 추가 하는 경우 새 마이그레이션 이름으로 명령줄 명령을 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-149">When you make changes to the `Product` class or add more related classes you would like interacting with your database, you need to run the command-line commands again with a new name of the migration.</span></span>  <span data-ttu-id="67217-150">이 명령은 다른 마이그레이션 클래스 집합을 생성 하 여 데이터베이스 스키마를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-150">This command will generate another set of migration classes to update your database schema.</span></span>

### <a name="ef-database-first"></a><span data-ttu-id="67217-151">EF Database First</span><span class="sxs-lookup"><span data-stu-id="67217-151">EF Database First</span></span>

<span data-ttu-id="67217-152">기존 데이터베이스의 경우 .NET 명령줄 도구를 사용 하 여 EF Core에 대 한 클래스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-152">For existing databases, you can generate the classes for EF Core by using the .NET command-line tools.</span></span> <span data-ttu-id="67217-153">클래스를 스 캐 폴드 다음 명령의 변형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-153">To scaffold the classes, use a variation of the following command:</span></span>

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

<span data-ttu-id="67217-154">이전 명령은 지정 된 연결 문자열 및 공급자를 사용 하 여 데이터베이스에 연결 합니다 `Microsoft.EntityFrameworkCore.SqlServer` .</span><span class="sxs-lookup"><span data-stu-id="67217-154">The preceding command connects to the database using the specified connection string and the `Microsoft.EntityFrameworkCore.SqlServer` provider.</span></span> <span data-ttu-id="67217-155">연결 되 면 라는 데이터베이스 컨텍스트 클래스가 `MyDbContext` 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="67217-155">Once connected, a database context class named `MyDbContext` is created.</span></span> <span data-ttu-id="67217-156">또한 옵션을 사용 하 여 지정 된 및 테이블에 대 한 지원 클래스가 생성 됩니다 `Product` `Customer` `-t` .</span><span class="sxs-lookup"><span data-stu-id="67217-156">Additionally, supporting classes are created for the `Product` and `Customer` tables that were specified with the `-t` options.</span></span> <span data-ttu-id="67217-157">이 명령에는 데이터베이스에 적합 한 클래스 계층 구조를 생성 하는 다양 한 구성 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-157">There are many configuration options for this command to generate the class hierarchy appropriate for your database.</span></span> <span data-ttu-id="67217-158">전체 참조는 [명령의 설명서](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67217-158">For a complete reference, see [the command's documentation](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span></span>

<span data-ttu-id="67217-159">[EF Core](/ef/core/) 에 대 한 자세한 내용은 Microsoft Docs 사이트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-159">More information about [EF Core](/ef/core/) can be found on the Microsoft Docs site.</span></span>

## <a name="interact-with-web-services"></a><span data-ttu-id="67217-160">웹 서비스와 상호 작용</span><span class="sxs-lookup"><span data-stu-id="67217-160">Interact with web services</span></span>

<span data-ttu-id="67217-161">ASP.NET가 처음 출시 될 때 웹 서버와 클라이언트가 데이터를 교환 하는 데는 SOAP 서비스가 선호 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67217-161">When ASP.NET was first released, SOAP services were the preferred way for web servers and clients to exchange data.</span></span> <span data-ttu-id="67217-162">그 이후에는 대부분 변경 되었으며 서비스와의 기본 작용은 HTTP 클라이언트 상호 작용을 직접 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-162">Much has changed since that time, and the preferred interactions with services have shifted to direct HTTP client interactions.</span></span> <span data-ttu-id="67217-163">ASP.NET Core 및 Blazor를 사용 하 여 클래스의 메서드에의 구성을 등록할 수 있습니다 `HttpClient` `Startup` `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="67217-163">With ASP.NET Core and Blazor, you can register the configuration of your `HttpClient` in the `Startup` class's `ConfigureServices` method.</span></span> <span data-ttu-id="67217-164">HTTP 끝점과 상호 작용 해야 하는 경우이 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-164">Use that configuration when you need to interact with the HTTP endpoint.</span></span> <span data-ttu-id="67217-165">다음 구성 코드를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-165">Consider the following configuration code:</span></span>

```csharp
services.AddHttpClient("github", client =>
{
    client.BaseAddress = new Uri("http://api.github.com/");
    // Github API versioning
    client.DefaultRequestHeaders.Add("Accept", "application/vnd.github.v3+json");
    // Github requires a user-agent
    client.DefaultRequestHeaders.Add("User-Agent", "BlazorWebForms-Sample");
});
```

<span data-ttu-id="67217-166">GitHub에서 데이터에 액세스 해야 할 때마다 이름이 인 클라이언트를 만듭니다 `github` .</span><span class="sxs-lookup"><span data-stu-id="67217-166">Whenever you need to access data from GitHub, create a client with a name of `github`.</span></span> <span data-ttu-id="67217-167">클라이언트는 기본 주소를 사용 하 여 구성 되 고 요청 헤더는 적절 하 게 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67217-167">The client is configured with the base address, and the request headers are set appropriately.</span></span> <span data-ttu-id="67217-168">`IHttpClientFactory` `@inject` 속성의 지시문 또는 특성을 사용 하 여 Blazor 구성 요소에를 삽입 `[Inject]` 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-168">Inject the `IHttpClientFactory` into your Blazor components with the `@inject` directive or an `[Inject]` attribute on a property.</span></span> <span data-ttu-id="67217-169">명명 된 클라이언트를 만들고 다음 구문을 사용 하 여 서비스와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-169">Create your named client and interact with services using the following syntax:</span></span>

```razor
@inject IHttpClientFactory factory

...

@code {
    protected override async Task OnInitializedAsync()
    {
        var client = factory.CreateClient("github");
        var response = await client.GetAsync("repos/dotnet/docs/issues");
        response.EnsureStatusCode();
        var content = async response.Content.ReadAsStringAsync();
    }
}
```

<span data-ttu-id="67217-170">이 메서드는 *dotnet/docs* GitHub 리포지토리의 문제 컬렉션을 설명 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="67217-170">This method returns the string describing the collection of issues in the *dotnet/docs* GitHub repository.</span></span> <span data-ttu-id="67217-171">JSON 형식으로 콘텐츠를 반환 하 고 적절 한 GitHub 문제 개체로 deserialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67217-171">It returns content in JSON format and is deserialized into appropriate GitHub issue objects.</span></span> <span data-ttu-id="67217-172">미리 구성 된 `HttpClientFactory` 개체를 제공 하도록를 구성할 수 있는 여러 가지 방법이 있습니다 `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="67217-172">There are many ways that you can configure the `HttpClientFactory` to deliver preconfigured `HttpClient` objects.</span></span> <span data-ttu-id="67217-173">`HttpClient`작업 하는 다양 한 웹 서비스에 대해 다른 이름 및 끝점을 사용 하 여 여러 인스턴스를 구성 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67217-173">Try configuring multiple `HttpClient` instances with different names and endpoints for the various web services you work with.</span></span> <span data-ttu-id="67217-174">이 방법을 사용 하면 각 페이지에서 해당 서비스와의 상호 작용을 보다 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67217-174">This approach will make your interactions with those services easier to work with on each page.</span></span> <span data-ttu-id="67217-175">자세한 내용은 [IHttpClientFactory 설명서](/aspnet/core/fundamentals/http-requests)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67217-175">For more details, read [the documentation for the IHttpClientFactory](/aspnet/core/fundamentals/http-requests).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="67217-176">[이전](forms-validation.md)
>[다음](middleware.md)</span><span class="sxs-lookup"><span data-stu-id="67217-176">[Previous](forms-validation.md)
[Next](middleware.md)</span></span>
