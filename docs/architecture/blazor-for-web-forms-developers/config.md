---
title: 앱 구성
description: BlazorConfigurationManager를 사용 하지 않고 앱을 구성 하는 방법을 알아봅니다.
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/01/2020
ms.openlocfilehash: a13f663c2c6908ba906e42cb939c3b8707b8cccd
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173317"
---
# <a name="app-configuration"></a><span data-ttu-id="64383-103">앱 구성</span><span class="sxs-lookup"><span data-stu-id="64383-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="64383-104">Web Forms에서 앱 구성을 로드 하는 기본적인 방법은 *web.config* 파일의 항목을 &mdash; 서버 또는 *web.config*에서 참조 하는 관련 구성 파일에 포함 하는 것입니다. 정적 개체를 사용 하 여 앱 `ConfigurationManager` 설정, 데이터 저장소 연결 문자열 및 앱에 추가 되는 기타 확장 된 구성 공급자와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="64383-105">다음 코드에 표시 된 것 처럼 앱 구성과의 상호 작용을 확인 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="64383-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="64383-106">ASP.NET Core 및 서버 쪽에서 Blazor 앱이 WINDOWS IIS 서버에서 호스팅되는 경우 *web.config* 파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="64383-107">그러나 `ConfigurationManager` 이 구성과 상호 작용 하지 않으며 다른 원본에서 더 많은 구조화 된 앱 구성을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="64383-108">구성이 수집 되는 방법 및 *web.config* 파일에서 구성 정보에 액세스 하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="64383-109">구성 원본</span><span class="sxs-lookup"><span data-stu-id="64383-109">Configuration sources</span></span>

<span data-ttu-id="64383-110">ASP.NET Core는 앱에 사용할 수 있는 많은 구성 원본을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="64383-111">프레임 워크는 기본적으로 이러한 기능을 가장 잘 제공 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="64383-112">ASP.NET Core 하 여 이러한 다양 한 원본에서 구성을 읽고 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="64383-113">나중에 동일한 구성 키에 대해 로드 된 값이 이전 값 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="64383-114">ASP.NET Core는 클라우드를 인식 하 고 연산자와 개발자에 게 더 쉽게 앱을 구성할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="64383-115">ASP.NET Core는 환경에서 인식 되며 또는 환경에서 실행 중인지 확인 `Production` `Development` 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="64383-116">환경 표시기는 `ASPNETCORE_ENVIRONMENT` 시스템 환경 변수에 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="64383-117">구성 된 값이 없는 경우 앱은 기본적으로 환경에서 실행 중으로 설정 됩니다 `Production` .</span><span class="sxs-lookup"><span data-stu-id="64383-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="64383-118">앱은 환경 이름을 기반으로 여러 소스에서 구성을 트리거하고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="64383-119">기본적으로 구성은 다음 리소스에서 나열 된 순서 대로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="64383-120">파일 *에appsettings.js* (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="64383-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="64383-121">*appsettings. {ENVIRONMENT_NAME}. json* 파일 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="64383-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="64383-122">디스크의 사용자 비밀 파일 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="64383-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="64383-123">환경 변수</span><span class="sxs-lookup"><span data-stu-id="64383-123">Environment variables</span></span>
1. <span data-ttu-id="64383-124">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="64383-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="64383-125">appsettings.js형식 및 액세스</span><span class="sxs-lookup"><span data-stu-id="64383-125">appsettings.json format and access</span></span>

<span data-ttu-id="64383-126">파일 *의appsettings.js* 는 다음 JSON 처럼 구조화 된 값이 있는 계층적 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

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

<span data-ttu-id="64383-127">위의 JSON을 사용 하 여 표시 되 면 구성 시스템은 자식 값을 평면화 하 고 정규화 된 계층적 경로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="64383-128">콜론 ( `:` ) 문자는 계층의 각 속성을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="64383-129">예를 들어 구성 키는 `section1:key0` `section1` 개체 리터럴의 값에 액세스 합니다 `key0` .</span><span class="sxs-lookup"><span data-stu-id="64383-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="64383-130">사용자 암호</span><span class="sxs-lookup"><span data-stu-id="64383-130">User secrets</span></span>

<span data-ttu-id="64383-131">사용자 암호는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-131">User secrets are:</span></span>

* <span data-ttu-id="64383-132">앱 개발 폴더 외부의 개발자 워크스테이션에서 JSON 파일에 저장 되는 구성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="64383-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="64383-133">환경에서 실행 될 때만 로드 `Development` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="64383-134">특정 앱과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-134">Associated with a specific app.</span></span>
* <span data-ttu-id="64383-135">.NET Core CLI의 명령을 사용 하 여 관리 `user-secrets` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="64383-136">다음 명령을 실행 하 여 암호 저장소에 대 한 앱을 구성 합니다 `user-secrets` .</span><span class="sxs-lookup"><span data-stu-id="64383-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="64383-137">이전 명령은 `UserSecretsId` 프로젝트 파일에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="64383-138">요소는 암호를 앱에 연결 하는 데 사용 되는 GUID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="64383-139">그런 다음 명령을 사용 하 여 비밀을 정의할 수 있습니다 `set` .</span><span class="sxs-lookup"><span data-stu-id="64383-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="64383-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="64383-141">위의 명령은 `Parent:ApiKey` 값을 사용 하 여 개발자의 워크스테이션에서 구성 키를 사용할 수 있도록 합니다 `12345` .</span><span class="sxs-lookup"><span data-stu-id="64383-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="64383-142">사용자 암호를 만들고, 저장 하 고, 관리 하는 방법에 대 한 자세한 내용은 [ASP.NET Core 문서에서 개발 중인 앱 비밀의 안전한 저장소](/aspnet/core/security/app-secrets) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64383-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="64383-143">환경 변수</span><span class="sxs-lookup"><span data-stu-id="64383-143">Environment variables</span></span>

<span data-ttu-id="64383-144">앱 구성에 로드 되는 다음 값 집합은 시스템의 환경 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="64383-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="64383-145">이제 모든 시스템 환경 변수 설정을 구성 API를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="64383-146">응용 프로그램 내에서 읽을 때 계층적 값은 콜론 문자로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="64383-147">그러나 일부 운영 체제에서는 콜론 문자 환경 변수 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="64383-148">ASP.NET Core는 이중 밑줄 ()이 있는 값에 액세스할 때 콜론으로 변환 하 여이 제한을 해결 `__` 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="64383-149">`Parent:ApiKey`위의 사용자 암호 섹션의 값은 환경 변수를 사용 하 여 재정의할 수 있습니다 `Parent__ApiKey` .</span><span class="sxs-lookup"><span data-stu-id="64383-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="64383-150">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="64383-150">Command-line arguments</span></span>

<span data-ttu-id="64383-151">앱이 시작 될 때 구성도 명령줄 인수로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="64383-152">이중 대시 ( `--` ) 또는 슬래시 ( `/` ) 표기법을 사용 하 여 설정할 구성 값의 이름과 구성할 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="64383-153">구문은 다음 명령과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="64383-154">반환 web.config</span><span class="sxs-lookup"><span data-stu-id="64383-154">The return of web.config</span></span>

<span data-ttu-id="64383-155">IIS의 Windows에 앱을 배포한 경우 *web.config* 파일은 여전히 앱을 관리 하도록 iis를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="64383-156">기본적으로 IIS는 ASP.NET Core 모듈 (간에 m)에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="64383-157">C l i m은 Kestrel 웹 서버 대신 앱을 호스트 하는 네이티브 IIS 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="64383-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="64383-158">이 *web.config* 섹션은 다음 XML 태그와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-158">This *web.config* section resembles the following XML markup:</span></span>

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

<span data-ttu-id="64383-159">요소에 요소를 중첩 하 여 앱 별 구성을 정의할 수 있습니다 `environmentVariables` `aspNetCore` .</span><span class="sxs-lookup"><span data-stu-id="64383-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="64383-160">이 섹션에 정의 된 값은 ASP.NET Core 앱에 환경 변수로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="64383-161">환경 변수는 해당 앱 시작 세그먼트에서 적절 하 게 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64383-161">The environment variables load appropriately during that segment of app startup.</span></span>

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

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="64383-162">앱에서 구성 읽기</span><span class="sxs-lookup"><span data-stu-id="64383-162">Read configuration in the app</span></span>

<span data-ttu-id="64383-163">ASP.NET Core는 인터페이스를 통해 앱 구성을 제공 <xref:Microsoft.Extensions.Configuration.IConfiguration> 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="64383-164">구성 Blazor 요소, Blazor 페이지 및 구성에 액세스 해야 하는 기타 ASP.NET Core 관리 클래스에서이 구성 인터페이스를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="64383-165">ASP.NET Core 프레임 워크는 이전에 구성 된 확인 된 구성으로이 인터페이스를 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="64383-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="64383-166">Blazor페이지 또는 구성 요소의 razor 태그에서 `IConfiguration` `@inject` 다음과 같이 *razor* 파일 상단에 지시문을 사용 하 여 개체를 주입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="64383-167">이 이전 문은 `IConfiguration` `Configuration` Razor 템플릿의 나머지 부분에서 개체를 변수로 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="64383-168">인덱서 매개 변수로 찾는 구성 설정 계층을 지정 하 여 개별 구성 설정을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="64383-169"><xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> `GetSection("section1")` 이전 예제에서 section1에 대 한 구성을 검색 하는 것과 유사한 구문을 사용 하 여 특정 위치의 키 컬렉션을 검색 하는 메서드를 사용 하 여 전체 구성 섹션을 페치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="64383-170">강력한 형식의 구성</span><span class="sxs-lookup"><span data-stu-id="64383-170">Strongly typed configuration</span></span>

<span data-ttu-id="64383-171">Web Forms에서는 <xref:System.Configuration.ConfigurationSection> 형식 및 관련 형식에서 상속 되는 강력한 형식의 구성 형식을 만들 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="64383-172">를 통해 `ConfigurationSection` 이러한 구성 값에 대 한 비즈니스 규칙 및 처리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="64383-173">ASP.NET Core에서 구성 값을 받을 클래스 계층 구조를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="64383-174">이러한 클래스:</span><span class="sxs-lookup"><span data-stu-id="64383-174">These classes:</span></span>

* <span data-ttu-id="64383-175">부모 클래스에서 상속할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="64383-176">`public`캡처할 구성 구조에 대 한 속성 및 형식 참조와 일치 하는 속성을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="64383-177">이전appsettings.js샘플 *에서* 다음 클래스를 정의 하 여 값을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

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

<span data-ttu-id="64383-178">이 클래스 계층 구조는 메서드에 다음 줄을 추가 하 여 채울 수 있습니다 `Startup.ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="64383-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="64383-179">응용 프로그램의 나머지 부분에서는 `@inject` `IOptions<MyConfig>` 강력한 형식의 구성 설정을 수신 하기 위해 형식의 Razor 템플릿에서 클래스 또는 지시문에 입력 매개 변수를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="64383-180">`IOptions<MyConfig>.Value`속성은 `MyConfig` 구성 설정에서 채워진 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64383-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="64383-181">옵션 기능에 대 한 자세한 내용은 [ASP.NET Core의 옵션 패턴](/aspnet/core/fundamentals/configuration/options#options-interfaces) 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64383-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="64383-182">[이전](middleware.md)
>[다음](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="64383-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
