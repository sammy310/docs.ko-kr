---
title: 앱 구성
description: ConfigurationManager를 사용하지 않고 Blazor 앱을 구성하는 방법에 대해 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588241"
---
# <a name="app-configuration"></a><span data-ttu-id="31540-103">앱 구성</span><span class="sxs-lookup"><span data-stu-id="31540-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="31540-104">Web Forms에서 앱 구성을 로드하는 기본 방법은 web.config 파일의&mdash;항목을 서버또는 *web.config에서* 참조하는 관련 구성 파일입니다. *web.config* 정적 `ConfigurationManager` 개체를 사용하여 앱 설정, 데이터 리포지토리 연결 문자열 및 앱에 추가된 기타 확장 된 구성 공급자와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="31540-105">다음 코드에서 볼 수 있듯이 앱 구성과의 상호 작용을 확인하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="31540-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="31540-106">ASP.NET 코어 및 서버 측 Blazor를 사용하면 앱이 Windows IIS 서버에서 호스팅되는 경우 *web.config* 파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="31540-107">그러나 이 구성과의 `ConfigurationManager` 상호 작용은 없으며 다른 소스에서 보다 구조화된 앱 구성을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="31540-108">구성을 수집하는 방법과 *web.config* 파일에서 구성 정보에 계속 액세스하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="31540-109">구성 원본</span><span class="sxs-lookup"><span data-stu-id="31540-109">Configuration sources</span></span>

<span data-ttu-id="31540-110">ASP.NET Core는 앱에 사용할 수 있는 구성 소스가 많다는 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="31540-111">프레임워크는 기본적으로 이러한 기능 중 최고를 제공하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="31540-112">구성은 ASP.NET Core에 의해 이러한 다양한 소스에서 읽고 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="31540-113">동일한 구성 키에 대해 나중에 로드된 값이 이전 값보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="31540-114">ASP.NET Core는 클라우드를 인식하고 운영자와 개발자 모두 앱을 더 쉽게 구성할 수 있도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="31540-115">ASP.NET Core는 환경을 인식하고 사용자 또는 `Production` `Development` 환경에서 실행되고 있는지 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="31540-116">환경 표시기는 시스템 `ASPNETCORE_ENVIRONMENT` 환경 변수에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="31540-117">값이 구성되지 않은 경우 앱은 기본적으로 `Production` 환경에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="31540-118">앱은 환경 이름에 따라 여러 소스에서 구성을 트리거하고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="31540-119">기본적으로 구성은 나열된 순서대로 다음 리소스에서 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="31540-120">*appsettings.json* 파일(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="31540-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="31540-121">*앱 설정. {ENVIRONMENT_NAME}.json* 파일(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="31540-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="31540-122">디스크에 있는 사용자 비밀 파일(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="31540-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="31540-123">환경 변수</span><span class="sxs-lookup"><span data-stu-id="31540-123">Environment variables</span></span>
1. <span data-ttu-id="31540-124">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="31540-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="31540-125">appsettings.json 형식 및 액세스</span><span class="sxs-lookup"><span data-stu-id="31540-125">appsettings.json format and access</span></span>

<span data-ttu-id="31540-126">*appsettings.json* 파일은 다음과 같은 구조의 값으로 계층적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

<span data-ttu-id="31540-127">앞의 JSON과 함께 제공될 때 구성 시스템은 자식 값을 평평하게 하고 정규화된 계층 적 경로를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="31540-128">콜론`:`() 문자는 계층 구조의 각 속성을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="31540-129">예를 들어 구성 `section1:key0` 키는 개체 `section1` 리터럴값에 `key0` 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="31540-130">사용자 비밀</span><span class="sxs-lookup"><span data-stu-id="31540-130">User secrets</span></span>

<span data-ttu-id="31540-131">사용자 암호는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-131">User secrets are:</span></span>

* <span data-ttu-id="31540-132">앱 개발 폴더 외부의 개발자 워크스테이션의 JSON 파일에 저장된 구성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31540-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="31540-133">환경에서 실행할 때만 `Development` 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="31540-134">특정 앱과 연결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-134">Associated with a specific app.</span></span>
* <span data-ttu-id="31540-135">.NET 코어 CLI의 `user-secrets` 명령으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="31540-136">명령을 실행하여 비밀 저장소에 `user-secrets` 대한 앱을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="31540-137">앞의 명령은 프로젝트 `UserSecretsId` 파일에 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="31540-138">요소에는 비밀을 앱과 연결하는 데 사용되는 GUID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="31540-139">그런 다음 명령을 통해 `set` 암호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="31540-140">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="31540-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="31540-141">위의 명령은 개발자의 `Parent:ApiKey` 워크스테이션에서 구성 키를 값으로 `12345`사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="31540-142">사용자 기밀을 생성, 저장 및 관리하는 데 대한 자세한 내용은 ASP.NET Core 문서에서 [개발 중 앱 비밀의 안전한 저장소를](/aspnet/core/security/app-secrets) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="31540-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="31540-143">환경 변수</span><span class="sxs-lookup"><span data-stu-id="31540-143">Environment variables</span></span>

<span data-ttu-id="31540-144">앱 구성에 로드된 다음 값 집합은 시스템의 환경 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="31540-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="31540-145">이제 구성 API를 통해 시스템의 모든 환경 변수 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="31540-146">계층 적 값은 앱 내에서 읽을 때 병합 문자로 병합되고 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="31540-147">그러나 일부 운영 체제에서는 콜론 문자 환경 변수 이름을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="31540-148">ASP.NET Core는 이중 밑줄()`__`값이 있는 값을 액세스할 때 콜론으로 변환하여 이러한 제한을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="31540-149">위의 `Parent:ApiKey` 사용자 암호 섹션의 값을 환경 변수로 `Parent__ApiKey`재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="31540-150">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="31540-150">Command-line arguments</span></span>

<span data-ttu-id="31540-151">구성은 앱을 시작할 때 명령줄 인수로 제공될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="31540-152">이중 대시 ()`--`또는 정방향`/`슬래시 () 표기법() 표기법으로 설정할 구성 값의 이름과 구성할 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31540-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="31540-153">구문은 다음 명령과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="31540-154">web.config의 반환</span><span class="sxs-lookup"><span data-stu-id="31540-154">The return of web.config</span></span>

<span data-ttu-id="31540-155">IIS에서 Windows에 앱을 배포한 경우에도 *web.config* 파일은 여전히 IIS를 관리하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="31540-156">기본적으로 IIS는 ASP.NET 코어 모듈(ANCM)에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="31540-157">ANCM은 Kestrel 웹 서버 대신 앱을 호스팅하는 기본 IIS 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="31540-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="31540-158">이 *web.config* 섹션은 다음과 같은 XML 태그와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-158">This *web.config* section resembles the following XML markup:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

<span data-ttu-id="31540-159">앱별 구성은 `environmentVariables` `aspNetCore` 요소에 요소를 중첩하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="31540-160">이 섹션에 정의된 값은 ASP.NET Core 앱에 환경 변수로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="31540-161">환경 변수는 앱 시작 세그먼트 동안 적절하게 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="31540-161">The environment variables load appropriately during that segment of app startup.</span></span>

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="31540-162">앱에서 구성 읽기</span><span class="sxs-lookup"><span data-stu-id="31540-162">Read configuration in the app</span></span>

<span data-ttu-id="31540-163">ASP.NET 코어는 인터페이스를 <xref:Microsoft.Extensions.Configuration.IConfiguration> 통해 앱 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="31540-164">이 구성 인터페이스는 Blazor 구성 요소, Blazor 페이지 및 구성에 액세스해야 하는 기타 ASP.NET Core 관리 클래스에서 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="31540-165">ASP.NET Core 프레임워크는 이 인터페이스를 이전에 구성된 해결된 구성으로 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="31540-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="31540-166">Blazor 페이지 또는 구성 요소의 Razor 태그에서 다음과 `IConfiguration` 같은 `@inject` *.razor* 파일 의 맨 위에 지시문과 함께 개체를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="31540-167">이 앞의 문은 `IConfiguration` 개체를 `Configuration` Razor 템플릿의 나머지 부분에서 변수로 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="31540-168">개별 구성 설정은 인덱서 매개 변수로 검색되는 구성 설정 계층 구조를 지정하여 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="31540-169">이전 예제에서 section1에 <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> 대한 구성을 검색하는 것과 `GetSection("section1")` 유사한 구문을 사용하여 특정 위치에서 키 컬렉션을 검색하는 메서드를 사용하여 전체 구성 섹션을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="31540-170">강력한 형식의 구성</span><span class="sxs-lookup"><span data-stu-id="31540-170">Strongly typed configuration</span></span>

<span data-ttu-id="31540-171">Web Forms를 사용하면 <xref:System.Configuration.ConfigurationSection> 형식 및 관련 형식에서 상속된 강력한 형식의 구성 형식을 만들 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="31540-172">A를 `ConfigurationSection` 사용하면 이러한 구성 값에 대한 일부 비즈니스 규칙 및 처리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="31540-173">ASP.NET Core에서 구성 값을 수신하는 클래스 계층구조를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="31540-174">이러한 클래스는 다음과 같은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31540-174">These classes:</span></span>

* <span data-ttu-id="31540-175">부모 클래스에서 상속할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="31540-176">캡처하려는 `public` 구성 구조에 대한 속성 및 형식 참조와 일치하는 속성을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="31540-177">이전 *appsettings.json* 샘플의 경우 다음 클래스를 정의하여 값을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

<span data-ttu-id="31540-178">이 클래스 계층 구조는 `Startup.ConfigureServices` 메서드에 다음 줄을 추가하여 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="31540-179">앱의 나머지 부분에서는 클래스에 입력 매개 변수를 `@inject` 추가하거나 유형의 `IOptions<MyConfig>` Razor 템플릿에 지시문을 추가하여 강력한 형식의 구성 설정을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="31540-180">속성은 `IOptions<MyConfig>.Value` 구성 `MyConfig` 설정에서 채워진 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="31540-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="31540-181">옵션 기능에 대한 자세한 내용은 ASP.NET 핵심 문서의 [옵션 패턴에서](/aspnet/core/fundamentals/configuration/options#options-interfaces) 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31540-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="31540-182">[이전](middleware.md)
>[다음](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="31540-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
