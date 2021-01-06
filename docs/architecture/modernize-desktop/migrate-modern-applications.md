---
title: 최신 데스크톱 응용 프로그램 마이그레이션
description: 최신 데스크톱 응용 프로그램에 대 한 마이그레이션 프로세스에 대해 알아야 하는 모든 것입니다.
ms.date: 05/12/2020
ms.openlocfilehash: f7862d6379eeeb737c386b5ffeaab938d258b046
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "97866659"
---
# <a name="migrating-modern-desktop-applications"></a><span data-ttu-id="956ef-103">최신 데스크톱 응용 프로그램 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="956ef-103">Migrating Modern Desktop applications</span></span>

<span data-ttu-id="956ef-104">이 장에서는 기존 응용 .NET Framework 프로그램을 .NET Core로 마이그레이션할 때 직면 하는 가장 일반적인 문제 및 문제를 탐색 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-104">In this chapter, we're exploring the most common issues and challenges you can face when migrating an existing application from .NET Framework to .NET Core.</span></span>

<span data-ttu-id="956ef-105">복잡 한 데스크톱 응용 프로그램은 격리에서 작동 하지 않으며, 로컬 컴퓨터 또는 원격 서버에 상주할 수 있는 하위 시스템에 대 한 일종의 상호 작용이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-105">A complex desktop application doesn't work in isolation and needs some kind of interaction with subsystems that may reside on the local machine or on a remote server.</span></span> <span data-ttu-id="956ef-106">로컬 또는 원격으로 지 속성 저장소로 연결 하는 일종의 데이터베이스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-106">It will probably need some kind of database to connect as a persistence storage either locally or remotely.</span></span> <span data-ttu-id="956ef-107">인터넷 및 서비스 지향 아키텍처의 발생으로 응용 프로그램을 원격 서버 또는 클라우드에 있는 일종의 서비스에 연결 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-107">With the raise of Internet and service-oriented architectures, it's common to have your application connected to some sort of service residing on a remote server or in the cloud.</span></span> <span data-ttu-id="956ef-108">일부 기능을 구현 하려면 컴퓨터 파일 시스템에 액세스 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-108">You may need to access the machine file system to implement some functionality.</span></span> <span data-ttu-id="956ef-109">또는 응용 프로그램 외부에 있는 COM 개체 내에 있는 기능을 사용 하는 경우, 예를 들어, 앱에서 Office 어셈블리를 통합 하는 경우 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-109">Alternatively, maybe you're using a piece of functionality that resides inside a COM object outside your application, which is a common scenario if, for example, you're integrating Office assemblies in your app.</span></span>

<span data-ttu-id="956ef-110">뿐만 아니라 .NET Framework 및 .NET Core에 의해 노출 되는 API 표면의 차이가 있으며 .NET Framework에서 사용할 수 있는 일부 기능은 .NET Core에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-110">Besides, there are differences in the API surface that is exposed by .NET Framework and .NET Core, and some features that are available on .NET Framework aren't available on .NET Core.</span></span> <span data-ttu-id="956ef-111">따라서 마이그레이션을 계획할 때이를 파악 하 고이를 고려 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-111">So, it's important for you to know and take them into account when planning a migration.</span></span>

## <a name="configuration-files"></a><span data-ttu-id="956ef-112">구성 파일</span><span class="sxs-lookup"><span data-stu-id="956ef-112">Configuration files</span></span>

<span data-ttu-id="956ef-113">구성 파일은 런타임에 읽고 응용 프로그램의 동작 (예: 데이터베이스를 찾을 위치 또는 루프를 실행할 횟수)에 영향을 주는 속성 집합을 저장할 수 있는 가능성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-113">Configuration files offer the possibility to store sets of properties that are read at run time and affect the behavior of our apps, such as where to locate a database or how many times to execute a loop.</span></span> <span data-ttu-id="956ef-114">이 기술의 장점은 recode 하 고 다시 컴파일하지 않아도 응용 프로그램의 일부 측면을 수정할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-114">The beauty of this technique is that you can modify some aspects of the application without the need to recode and recompile.</span></span> <span data-ttu-id="956ef-115">예를 들어, 특정 구성 값 집합 및 다른 구성 값을 사용 하는 개발 환경에서 동일한 앱 코드를 실행 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-115">This comes in handy when, for example, the same app code runs on a development environment with a certain set of configuration values and in production with a different one.</span></span>

### <a name="configuration-on-net-framework"></a><span data-ttu-id="956ef-116">.NET Framework 구성</span><span class="sxs-lookup"><span data-stu-id="956ef-116">Configuration on .NET Framework</span></span>

<span data-ttu-id="956ef-117">.NET Framework 데스크톱 응용 프로그램을 사용 하는 경우  <xref:System.Configuration.AppSettingsSection> `System.Configuration` 네임 스페이스에서 클래스를 통해 액세스 하는app.config파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-117">If you have a working .NET Framework desktop application, chances are you have an *app.config* file accessed through the <xref:System.Configuration.AppSettingsSection> class from the `System.Configuration` namespace.</span></span>

<span data-ttu-id="956ef-118">.NET Framework 인프라 내에서 부모 로부터 속성을 상속 하는 구성 파일의 계층이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-118">Within the .NET Framework infrastructure, there's a hierarchy of configuration files that inherit properties from its parents.</span></span> <span data-ttu-id="956ef-119">모든 하위 구성 파일에서 사용 되거나 재정의 될 수 있는 여러 속성 및 구성 섹션을 정의 하는 *machine.config* 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-119">You can find a *machine.config* file that defines many properties and configuration sections that can be used or overridden in any descendant configuration file.</span></span>

### <a name="configuration-on-net-core"></a><span data-ttu-id="956ef-120">.NET Core에 대 한 구성</span><span class="sxs-lookup"><span data-stu-id="956ef-120">Configuration on .NET Core</span></span>

<span data-ttu-id="956ef-121">.NET Core 세계에는 *machine.config* 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-121">In the .NET Core world, there's no *machine.config* file.</span></span> <span data-ttu-id="956ef-122">이전에 만든 네임 스페이스를 계속 사용할 수 있지만 최신 버전으로 전환 하는 것이 좋습니다 .이를 통해 향상 된 기능을 향상 시킬 수 있습니다 <xref:System.Configuration> <xref:Microsoft.Extensions.Configuration> .</span><span class="sxs-lookup"><span data-stu-id="956ef-122">And even though you can continue to use the old fashioned <xref:System.Configuration> namespace, you may consider switching to the modern <xref:Microsoft.Extensions.Configuration>, which offers a good number of enhancements.</span></span>

<span data-ttu-id="956ef-123">구성 API는 구성을 로드 하는 데 사용할 데이터 원본을 정의 하는 구성 공급자 개념을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-123">The configuration API supports the concept of configuration provider, which defines the data source to be used to load the configuration.</span></span> <span data-ttu-id="956ef-124">다음과 같은 다양 한 종류의 기본 제공 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-124">There are different kinds of built-in providers, such as:</span></span>

- <span data-ttu-id="956ef-125">메모리 내 .NET 개체</span><span class="sxs-lookup"><span data-stu-id="956ef-125">In-memory .NET objects</span></span>
- <span data-ttu-id="956ef-126">INI 파일</span><span class="sxs-lookup"><span data-stu-id="956ef-126">INI files</span></span>
- <span data-ttu-id="956ef-127">JSON 파일</span><span class="sxs-lookup"><span data-stu-id="956ef-127">JSON files</span></span>
- <span data-ttu-id="956ef-128">XML 파일</span><span class="sxs-lookup"><span data-stu-id="956ef-128">XML files</span></span>
- <span data-ttu-id="956ef-129">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="956ef-129">Command-line arguments</span></span>
- <span data-ttu-id="956ef-130">환경 변수</span><span class="sxs-lookup"><span data-stu-id="956ef-130">Environment variables</span></span>
- <span data-ttu-id="956ef-131">암호화 된 사용자 저장소</span><span class="sxs-lookup"><span data-stu-id="956ef-131">Encrypted user store</span></span>

 <span data-ttu-id="956ef-132">또는 직접 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-132">Or you can build your own.</span></span>

<span data-ttu-id="956ef-133">새 구성에서는 다중 수준 계층으로 그룹화 할 수 있는 이름-값 쌍 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-133">The new configuration allows a list of name-value pairs that can be grouped into a multi-level hierarchy.</span></span> <span data-ttu-id="956ef-134">저장 된 값은 문자열에 매핑되고, 사용자 지정 일반 POCO (CLR object) 개체로 설정을 deserialize 할 수 있는 기본 제공 바인딩 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-134">Any stored value maps to a string, and there's built-in binding support that allows you to deserialize settings into a custom plain old CLR object (POCO) object.</span></span>

<span data-ttu-id="956ef-135"><xref:Microsoft.Extensions.Configuration.ConfigurationBuilder>개체를 사용 하면 우선 순위를 결정 하는 우선 순위 규칙을 사용 하 여 응용 프로그램에 필요한 수 만큼의 구성 공급자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-135">The <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder> object lets you add as many configuration providers you may need for your application, using a precedence rule to resolve preference.</span></span> <span data-ttu-id="956ef-136">따라서 코드에 추가 하는 마지막 공급자는 다른 공급자를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-136">So, the last provider you add in your code will override the others.</span></span> <span data-ttu-id="956ef-137">이 기능은 개발, 테스트 및 프로덕션 환경에 대해 서로 다른 구성을 정의 하 고 코드 내의 단일 함수에서 관리할 수 있기 때문에 다양 한 실행 환경을 관리 하는 데 유용한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-137">This is a great feature for managing different environments for execution since you can define different configurations for development, testing and production environments, and manage them on a single function inside your code.</span></span>

### <a name="migrating-configuration-files"></a><span data-ttu-id="956ef-138">구성 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="956ef-138">Migrating Configuration files</span></span>

<span data-ttu-id="956ef-139">기존 app.config XML 파일을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-139">You can continue to use your existing app.config XML file.</span></span> <span data-ttu-id="956ef-140">그러나이 기회를 통해 .NET Core에 대 한 여러 향상 된 기능을 활용 하 여 구성을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-140">However, you could take this opportunity to migrate your configuration to benefit from the several enhancements made on .NET Core.</span></span>

<span data-ttu-id="956ef-141">이전 스타일의 *app.config* 에서 새 구성 파일로 마이그레이션하려면 XML 형식과 JSON 형식 중에서 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-141">To migrate from an old-style *app.config* to a new configuration file, you should choose between an XML format and a JSON format.</span></span>

<span data-ttu-id="956ef-142">XML을 선택 하면 간단 하 게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-142">If you choose XML, the conversion is straightforward.</span></span> <span data-ttu-id="956ef-143">내용이 동일 하므로 *app.config* 파일의 이름을 XML 확장명을 사용 하는 파일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-143">Since the content is the same, just rename the *app.config* file to a file with XML extension.</span></span> <span data-ttu-id="956ef-144">그런 다음 AppSettings를 참조 하는 코드를 클래스를 사용 하도록 변경 합니다 `ConfigurationBuilder` .</span><span class="sxs-lookup"><span data-stu-id="956ef-144">Then, change the code that references AppSettings to use the `ConfigurationBuilder` class.</span></span> <span data-ttu-id="956ef-145">이렇게 변경 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-145">This change should be easy.</span></span>

<span data-ttu-id="956ef-146">JSON 형식을 사용 하려고 하지만 직접 마이그레이션하지 않으려는 경우 *app.config* 파일을 json 구성 파일로 변환할 수 있는 [config2json](https://www.nuget.org/packages/dotnet-config2json/) 라는 도구가 .net Core에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-146">If you want to use a JSON format and you don't want to migrate by hand, there's a tool called [dotnet-config2json](https://www.nuget.org/packages/dotnet-config2json/) available on .NET Core that can convert an *app.config* file to a JSON configuration file.</span></span>

<span data-ttu-id="956ef-147">*machine.config* 파일에 정의 된 구성 섹션을 사용 하는 경우 몇 가지 문제가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-147">You may also come across some issues when using configuration sections that were defined in the *machine.config* file.</span></span> <span data-ttu-id="956ef-148">예를 들어 다음 구성을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="956ef-148">For example, consider the following configuration:</span></span>

```xml
<configuration>
    <system.diagnostics>
        <switches>
            <add name="General" value="4" />
        </switches>
        <trace autoflush="true" indentsize="2">
            <listeners>
                <add name="myListener"
                     type="System.Diagnostics.TextWriterTraceListener,
                           System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
                     initializeData="MyListener.log"
                     traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />
            </listeners>
        </trace>
    </system.diagnostics>
</configuration>
```

<span data-ttu-id="956ef-149">이 구성을 .NET Core로 사용 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-149">If you take this configuration to a .NET Core, you'll get an exception:</span></span>

<span data-ttu-id="956ef-150">인식할 수 없는 구성 섹션 시스템 진단</span><span class="sxs-lookup"><span data-stu-id="956ef-150">Unrecognized configuration section system.diagnostics</span></span>

<span data-ttu-id="956ef-151">이 예외는 해당 섹션을 처리 하는 어셈블리와 해당 섹션이 현재 존재 하지 않는 *machine.config* 파일에 정의 되어 있기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-151">This exception occurs because that section and the assembly responsible for handling that section was defined in the *machine.config* file, which now doesn't exist.</span></span>

<span data-ttu-id="956ef-152">문제를 쉽게 해결 하려면 이전 *machine.config* 에서 섹션 정의를 새 구성 파일에 복사 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-152">To easily fix the issue, you can copy the section definition from your old *machine.config* to your new configuration file:</span></span>

```xml
<configSections>
    <section name="system.diagnostics"
             type="System.Diagnostics.SystemDiagnosticsSection,
                   System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
</configSections>
```

## <a name="accessing-databases"></a><span data-ttu-id="956ef-153">데이터베이스 액세스</span><span class="sxs-lookup"><span data-stu-id="956ef-153">Accessing databases</span></span>

<span data-ttu-id="956ef-154">거의 모든 데스크톱 응용 프로그램에는 일종의 데이터베이스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-154">Almost every desktop application needs some kind of database.</span></span> <span data-ttu-id="956ef-155">데스크톱의 경우 데스크톱 앱과 데이터베이스 엔진 간의 직접 연결을 사용 하 여 클라이언트-서버 아키텍처를 찾는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-155">For desktop, it's common to find client-server architectures with a direct connection between the desktop app and the database engine.</span></span> <span data-ttu-id="956ef-156">이러한 데이터베이스는 여러 사용자 간에 정보를 공유 해야 하는 필요성에 따라 로컬 또는 원격 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-156">These databases can be local or remote depending on the need to share information between different users.</span></span>

<span data-ttu-id="956ef-157">코드 관점에서 개발자에 게 데이터베이스 연결, 쿼리 및 업데이트를 허용 하는 여러 기술 및 프레임 워크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-157">From the code perspective, there have been many technologies and frameworks to give the developer the possibility to connect, query, and update a database.</span></span>

<span data-ttu-id="956ef-158">Windows 데스크톱 응용 프로그램에 대해 이야기할 때 찾을 수 있는 가장 일반적인 데이터베이스 예는 Microsoft Access 및 Microsoft SQL Server입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-158">The most common examples of database you can find when talking about Windows Desktop application are Microsoft Access and Microsoft SQL Server.</span></span> <span data-ttu-id="956ef-159">데스크톱에 대 한 20 년간의 경험을 보유 하 고 있는 경우 ODBC, OLEDB, RDO, ADO, ADO.NET, LINQ 및 Entity Framework 같은 이름이 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-159">If you have more than 20 years of experience programming for the desktop, names like ODBC, OLEDB, RDO, ADO, ADO.NET, LINQ, and Entity Framework will sound familiar.</span></span>

### <a name="odbc"></a><span data-ttu-id="956ef-160">ODBC</span><span class="sxs-lookup"><span data-stu-id="956ef-160">ODBC</span></span>

<span data-ttu-id="956ef-161">Microsoft에서 `System.Data.Odbc` .NET Standard 2.0와 호환 되는 라이브러리를 제공 하므로 .Net Core에서 ODBC를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-161">You can continue to use ODBC on .NET Core since Microsoft is providing the `System.Data.Odbc` library compatible with .NET Standard 2.0.</span></span>

### <a name="ole-db"></a><span data-ttu-id="956ef-162">OLE DB</span><span class="sxs-lookup"><span data-stu-id="956ef-162">OLE DB</span></span>

<span data-ttu-id="956ef-163">[OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85))   는 일관 된 방식으로 다양 한 데이터 원본에 액세스할 수 있는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-163">[OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85)) has been a great way to access various data sources in a uniform manner.</span></span> <span data-ttu-id="956ef-164">그러나 Windows 전용 기술인 COM을 기반으로 하 고 .NET Core와 같은 플랫폼 간 기술에는 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-164">But it was based on COM, which is a Windows-only technology, and as such wasn't the best fit for a cross-platform technology such as .NET Core.</span></span> <span data-ttu-id="956ef-165">SQL Server 버전 2014 이상 에서도 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-165">It's also unsupported in SQL Server versions 2014 and later.</span></span> <span data-ttu-id="956ef-166">이러한 이유로 OLE DB는 .NET Core에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-166">For those reasons, OLE DB won't be supported by .NET Core.</span></span>

### <a name="adonet"></a><span data-ttu-id="956ef-167">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="956ef-167">ADO.NET</span></span>

<span data-ttu-id="956ef-168">.NET Core에서 기존 데스크톱 코드의 ADO.NET를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-168">You can still use ADO.NET from your existing desktop code on .NET Core.</span></span> <span data-ttu-id="956ef-169">일부 NuGet 패키지를 업데이트 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-169">You just need to update some NuGet packages.</span></span>

### <a name="ef-core-vs-ef6"></a><span data-ttu-id="956ef-170">EF Core와 EF6 비교</span><span class="sxs-lookup"><span data-stu-id="956ef-170">EF Core vs. EF6</span></span>

<span data-ttu-id="956ef-171">현재 지원 되는 Entity Framework (EF), Entity Framework 6 (EF6) 및 EF Core의 두 가지 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-171">There are two currently supported versions of Entity Framework (EF), Entity Framework 6 (EF6) and EF Core.</span></span>

<span data-ttu-id="956ef-172">.NET Framework 환경의 일부로 출시 된 최신 기술은 Entity Framework 이며 6.4는 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-172">The latest technology released as part of the .NET Framework world is Entity Framework, with 6.4 being the latest version.</span></span> <span data-ttu-id="956ef-173">Microsoft는 .NET Core를 출시 하 여 Entity Framework 및 Entity Framework Core를 기반으로 새 데이터 액세스 스택을 릴리스 했습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-173">With the launch of .NET Core, Microsoft also released a new data access stack based on Entity Framework and called Entity Framework Core.</span></span>

<span data-ttu-id="956ef-174">EF 6.4 및 EF Core는 .NET Framework와 .NET Core 둘 다에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-174">You can use EF 6.4 and EF Core from both .NET Framework and .NET Core.</span></span> <span data-ttu-id="956ef-175">그렇다면 결정을 내리는 데 도움이 되는 결정 드라이버는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="956ef-175">So, what are the decision drivers to help to decide between the two?</span></span>

<span data-ttu-id="956ef-176">EF 6.3은 .NET Core에서 실행 되 고 플랫폼 간 작업을 수행할 수 있는 EF6의 첫 번째 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-176">EF 6.3 is the first version of EF6 that can run on .NET Core and work cross-platform.</span></span> <span data-ttu-id="956ef-177">실제로이 릴리스의 주요 목표는 EF6를 사용 하는 기존 응용 프로그램을 .NET Core로 쉽게 마이그레이션할 수 있도록 하는 것 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-177">In fact, the main goal of this release was to make it easier to migrate existing applications that use EF6 to .NET Core.</span></span>

<span data-ttu-id="956ef-178">EF Core는 EF6와 유사한 개발자 환경을 제공하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-178">EF Core was designed to provide a developer experience similar to EF6.</span></span> <span data-ttu-id="956ef-179">대부분의 상위 API가 그대로 유지되므로 EF6를 사용한 개발자에게는 EF Core가 친숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-179">Most of the top-level APIs remain the same, so EF Core will feel familiar to developers who have used EF6.</span></span>

<span data-ttu-id="956ef-180">호환 되기는 하지만 결정 하기 전에 확인 해야 하는 구현에는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-180">Although compatible, there are differences on the implementation you should check before making a decision.</span></span>
<span data-ttu-id="956ef-181">자세한 내용은 [Compare EF Core & EF6](/ef/efcore-and-ef6/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="956ef-181">For more information, see [Compare EF Core & EF6](/ef/efcore-and-ef6/).</span></span>

<span data-ttu-id="956ef-182">EF Core를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-182">The recommendation is to use EF Core if:</span></span>

* <span data-ttu-id="956ef-183">이 앱을 사용하려면 .NET Core의 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-183">The app needs the capabilities of .NET Core.</span></span>
* <span data-ttu-id="956ef-184">EF Core는 앱에 필요한 모든 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-184">EF Core supports all of the features that the app requires.</span></span>

<span data-ttu-id="956ef-185">다음 조건이 모두 충족되면 EF6를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="956ef-185">Consider using EF6 if both of the following conditions are true:</span></span>

* <span data-ttu-id="956ef-186">앱은 Windows 및 .NET Framework 4.0 이상에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-186">The app will run on Windows and .NET Framework 4.0 or later.</span></span>
* <span data-ttu-id="956ef-187">EF6는 앱에 필요한 모든 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-187">EF6 supports all of the features that the app requires.</span></span>

### <a name="relational-databases"></a><span data-ttu-id="956ef-188">관계형 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="956ef-188">Relational databases</span></span>

#### <a name="sql-server"></a><span data-ttu-id="956ef-189">SQL Server</span><span class="sxs-lookup"><span data-stu-id="956ef-189">SQL Server</span></span>

<span data-ttu-id="956ef-190">몇 년 전에 데스크톱을 개발 하는 경우에는 SQL Server가 선택 된 데이터베이스 중 하나 였습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-190">SQL Server has been one of the databases of choice if you were developing for the desktop some years ago.</span></span> <span data-ttu-id="956ef-191">.NET Framework에서를 사용 하면 <xref:System.Data.SqlClient> 데이터베이스 관련 프로토콜을 캡슐화 하는 SQL Server 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-191">With the use of <xref:System.Data.SqlClient> in .NET Framework, you could access versions of SQL Server, which encapsulates database-specific protocols.</span></span>

<span data-ttu-id="956ef-192">.NET Core에서는 `SqlClient` .NET Framework에 있는 기존 클래스와 완전히 호환 되 고 라이브러리에 있는 새 클래스를 찾을 수 있습니다 <xref:Microsoft.Data.SqlClient> .</span><span class="sxs-lookup"><span data-stu-id="956ef-192">In .NET Core, you can find a new `SqlClient` class, fully compatible with the one existing in the .NET Framework but located in the <xref:Microsoft.Data.SqlClient> library.</span></span> <span data-ttu-id="956ef-193">단지 [Microsoft. SqlClient](https://www.nuget.org/packages/Microsoft.Data.SqlClient/) NuGet 패키지에 대 한 참조를 추가 하 고 네임 스페이스에 대 한 일부 이름을 지정 해야 하며 모든 것이 예상 대로 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-193">You just have to add a reference to the [Microsoft.Data.SqlClient](https://www.nuget.org/packages/Microsoft.Data.SqlClient/) NuGet package and do some renaming for the namespaces and everything should work as expected.</span></span>

#### <a name="microsoft-access"></a><span data-ttu-id="956ef-194">Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="956ef-194">Microsoft Access</span></span>

<span data-ttu-id="956ef-195">Microsoft Access는 정교 하 고 확장 가능한 SQL Server 필요 하지 않은 경우 몇 년 동안 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-195">Microsoft Access has been used for years when the sophisticated and more scalable SQL Server wasn't needed.</span></span> <span data-ttu-id="956ef-196">라이브러리를 사용 하 여 Microsoft Access에 계속 연결할 수 있습니다 <xref:System.Data.Odbc> .</span><span class="sxs-lookup"><span data-stu-id="956ef-196">You can still connect to Microsoft Access using the <xref:System.Data.Odbc> library.</span></span>

## <a name="consuming-services"></a><span data-ttu-id="956ef-197">서비스 사용</span><span class="sxs-lookup"><span data-stu-id="956ef-197">Consuming services</span></span>

<span data-ttu-id="956ef-198">서비스 지향 아키텍처의 발생으로 데스크톱 응용 프로그램은 클라이언트-서버 모델에서 3 계층 접근 방식으로 발전 하기 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-198">With the raise of service-oriented architectures, desktop applications began to evolve from a client-server model to the three-layer approach.</span></span> <span data-ttu-id="956ef-199">클라이언트-서버 접근 방식에서는 비즈니스 논리를 포함 하는 클라이언트에서 직접 데이터베이스 연결이 설정 됩니다 .이는 일반적으로 단일 EXE 파일 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-199">In the client-server approach, a direct database connection is established from the client holding the business logic usually inside a single EXE file.</span></span> <span data-ttu-id="956ef-200">반면 3 계층 접근 방식은 비즈니스 논리 및 데이터베이스 액세스를 구현 하는 중간 서비스 계층을 설정 하 여 더 나은 보안, 확장성 및 재사용을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-200">On the other hand, the three-layer approach establishes an intermediate service layer implementing business logic and database access allowing for better security, scalability, and reusability.</span></span> <span data-ttu-id="956ef-201">데이터의 데이터 집합으로 직접 작업 하는 대신 계층 접근 방식은 계약을 구현 하는 서비스 집합과 데이터 전송을 구현 하는 방법으로 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-201">Instead of working directly with datasets of data, the layer approach relies in a set of services implementing contracts and types objects as a way to implement data transfer.</span></span>

<span data-ttu-id="956ef-202">WCF 서비스를 사용 하는 데스크톱 응용 프로그램이 있고 .NET Core로 마이그레이션하려는 경우 몇 가지 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-202">If you have a desktop application using a WCF service and you want to migrate it to .NET Core, there are some things to consider.</span></span>

<span data-ttu-id="956ef-203">첫 번째는 서비스에 액세스 하는 구성을 확인 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-203">The first thing is how to resolve the configuration to access the service.</span></span> <span data-ttu-id="956ef-204">구성이 .NET Core에서 다르기 때문에 구성 파일에서 일부 업데이트를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-204">Because the configuration is different on .NET Core, you'll need to make some updates in your configuration file.</span></span>

<span data-ttu-id="956ef-205">둘째, Visual Studio 2019에 있는 새 도구를 사용 하 여 서비스 클라이언트를 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-205">Second, you'll need to regenerate the service client with the new tools present on Visual Studio 2019.</span></span> <span data-ttu-id="956ef-206">이 단계에서는 클라이언트가 기존 코드와 호환 되도록 동기 작업 생성을 활성화 하는 것을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-206">In this step, you must consider activating the generation of the synchronous operations to make the client compatible with your existing code.</span></span>

<span data-ttu-id="956ef-207">마이그레이션 후 .NET Core에 존재 하지 않는 라이브러리가 필요한 경우에는 [Microsoft. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) NuGet 패키지에 대 한 참조를 추가 하 고 누락 된 함수가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-207">After the migration, if you find that there are libraries you need that aren't present on .NET Core, you can add a reference to the [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) NuGet package and see if the missing functions are there.</span></span>

<span data-ttu-id="956ef-208">클래스를 사용 하 여 <xref:System.Net.WebRequest> 웹 서비스 호출을 수행 하는 경우 .Net Core에 대 한 몇 가지 차이점을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-208">If you're using the <xref:System.Net.WebRequest> class to perform web service calls, you may find some differences on .NET Core.</span></span> <span data-ttu-id="956ef-209">대신 시스템 .Net. Http HttpClient를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-209">The recommendation is to use the System.Net.Http.HttpClient instead.</span></span>

## <a name="consuming-a-com-object"></a><span data-ttu-id="956ef-210">COM 개체 사용</span><span class="sxs-lookup"><span data-stu-id="956ef-210">Consuming a COM Object</span></span>

<span data-ttu-id="956ef-211">현재 .NET Core와 함께 사용 하기 위해 Visual Studio 2019의 COM 개체에 대 한 참조를 추가할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-211">Currently, there's no way to add a reference to a COM object from Visual Studio 2019 to use with .NET Core.</span></span> <span data-ttu-id="956ef-212">따라서 프로젝트 파일을 수동으로 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-212">So, you have to manually modify the project file.</span></span>

<span data-ttu-id="956ef-213">`COMReference`다음 예제와 같이 프로젝트 파일 내에 구조를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-213">Insert a `COMReference` structure inside the project file like in the following example:</span></span>

```xml
<ItemGroup>
    <COMReference Include="MSHTML">
        <Guid>{3050F1C5-98B5-11CF-BB82-00AA00BDCE0B}\</Guid>
        <VersionMajor>4</VersionMajor>
        <VersionMinor>0</VersionMinor>
        <Lcid>0</Lcid>
        <WrapperTool>primary</WrapperTool>
        <Isolated>false</Isolated>
    </COMReference>
</ItemGroup>
```

## <a name="more-things-to-consider"></a><span data-ttu-id="956ef-214">고려해 야 할 사항</span><span class="sxs-lookup"><span data-stu-id="956ef-214">More things to consider</span></span>

<span data-ttu-id="956ef-215">.NET Framework 라이브러리에서 사용할 수 있는 몇 가지 기술은 .NET Core에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-215">Several technologies available to .NET Framework libraries aren't available for .NET Core.</span></span> <span data-ttu-id="956ef-216">코드가 이러한 기술 중 일부를 사용 하는 경우이 섹션에 설명 된 대체 방법을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-216">If your code relies on some of these technologies, consider the alternative approaches outlined in this section.</span></span>

<span data-ttu-id="956ef-217">[Windows 호환 기능 팩](../../core/porting/windows-compat-pack.md) 은 이전에 .NET Framework에만 사용할 수 있었던 api에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-217">The [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md) provides access to APIs that were previously available only for .NET Framework.</span></span> <span data-ttu-id="956ef-218">.NET Core 및 .NET Standard 프로젝트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-218">It can be used on .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="956ef-219">API 호환성에 대 한 자세한 내용은에서 주요 변경 사항 및 사용 되지 않는/레거시 Api에 대 한 설명서를 찾을 수 있습니다 <https://docs.microsoft.com/dotnet/core/compatibility/fx-core> .</span><span class="sxs-lookup"><span data-stu-id="956ef-219">For more information on API compatibility, you can find documentation about breaking changes and deprecated/legacy APIs at <https://docs.microsoft.com/dotnet/core/compatibility/fx-core>.</span></span>

### <a name="appdomains"></a><span data-ttu-id="956ef-220">AppDomain</span><span class="sxs-lookup"><span data-stu-id="956ef-220">AppDomains</span></span>

<span data-ttu-id="956ef-221">애플리케이션 도메인(AppDomains)은 앱을 서로 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-221">Application domains (AppDomains) isolate apps from one another.</span></span> <span data-ttu-id="956ef-222">Appdomain에는 런타임 지원이 필요 하 고 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-222">AppDomains require runtime support and are expensive.</span></span> <span data-ttu-id="956ef-223">추가 앱 도메인 만들기는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-223">Creating additional app domains isn't supported.</span></span> <span data-ttu-id="956ef-224">코드 격리의 경우 별도의 프로세스 또는 컨테이너를 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-224">For code isolation, we recommend separate processes or using containers as an alternative.</span></span> <span data-ttu-id="956ef-225">어셈블리를 동적으로 로드 하는 경우 새 클래스를 권장 합니다  <xref:System.Runtime.Loader.AssemblyLoadContext> .</span><span class="sxs-lookup"><span data-stu-id="956ef-225">For the dynamic loading of assemblies, we recommend the new <xref:System.Runtime.Loader.AssemblyLoadContext> class.</span></span>

<span data-ttu-id="956ef-226">.NET Framework에서 코드 마이그레이션을 더 쉽게 수행 하기 위해 .NET Core는 일부 AppDomain API 화면을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-226">To make code migration from .NET Framework easier, .NET Core exposes some of the AppDomain API surface.</span></span> <span data-ttu-id="956ef-227">일부 Api는 정상적으로 작동 합니다 (예:  <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType> ). 일부 멤버는 아무 작업도 수행 하지 않습니다 (예:)  <xref:System.AppDomain.SetCachePath%2A> . 그 중 일부는 throw <xref:System.PlatformNotSupportedException> 됩니다 (예:  <xref:System.AppDomain.CreateDomain%2A> ).</span><span class="sxs-lookup"><span data-stu-id="956ef-227">Some of the APIs function normally (for example, <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), some members do nothing (for example, <xref:System.AppDomain.SetCachePath%2A>), and some of them throw <xref:System.PlatformNotSupportedException> (for example, <xref:System.AppDomain.CreateDomain%2A>).</span></span>

### <a name="remoting"></a><span data-ttu-id="956ef-228">원격 통신</span><span class="sxs-lookup"><span data-stu-id="956ef-228">Remoting</span></span>

<span data-ttu-id="956ef-229">.NET Remoting은 더 이상 지원 되지 않는 AppDomain 간 통신에 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-229">.NET Remoting was used for cross-AppDomain communication, which is no longer supported.</span></span> <span data-ttu-id="956ef-230">또한 원격 통신에는 유지 관리 비용이 많이 드는 런타임 지원이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-230">Also, Remoting requires runtime support, which is expensive to maintain.</span></span> <span data-ttu-id="956ef-231">이러한 이유로 .net Remoting은 .NET Core에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-231">For these reasons, .NET Remoting isn't supported on .NET Core.</span></span>

<span data-ttu-id="956ef-232">프로세스 간 통신의 경우 또는 클래스와 같은 원격 기능 대신 IPC (프로세스 간 통신) 메커니즘을 고려해 야 합니다 <xref:System.IO.Pipes?displayProperty=nameWithType> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> .</span><span class="sxs-lookup"><span data-stu-id="956ef-232">For communication across processes, you should consider inter-process communication (IPC) mechanisms as an alternative to Remoting, such as the <xref:System.IO.Pipes?displayProperty=nameWithType> or the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> class.</span></span>

<span data-ttu-id="956ef-233">여러 컴퓨터에서 네트워크 기반 솔루션을 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="956ef-233">Across machines, use a network-based solution as an alternative.</span></span> <span data-ttu-id="956ef-234">HTTP와 같은 오버 헤드가 낮은 일반 텍스트 프로토콜을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-234">Preferably, use a low-overhead plaintext protocol, such as HTTP.</span></span> <span data-ttu-id="956ef-235">ASP.NET Core에서 사용하는 웹 서버인 Kestrel 웹 서버도 옵션이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-235">The Kestrel web server, the web server used by ASP.NET Core, is an option here.</span></span>

### <a name="code-access-security-cas"></a><span data-ttu-id="956ef-236">CAS(코드 액세스 보안)</span><span class="sxs-lookup"><span data-stu-id="956ef-236">Code Access Security (CAS)</span></span>

<span data-ttu-id="956ef-237">런타임이나 프레임 워크를 사용 하 여 관리 되는 응용 프로그램 또는 라이브러리가 사용 하거나 실행 하는 리소스를 제한 하는 샌드 박싱은 .NET Core에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-237">Sandboxing, which relies on the runtime or the framework to constrain which resources a managed application or library uses or runs, isn't supported on .NET Core.</span></span>

<span data-ttu-id="956ef-238">운영 체제에서 제공 하는 보안 경계 (예: 가상화, 컨테이너 또는 사용자 계정)를 사용 하 여 최소 권한 집합으로 프로세스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-238">Use security boundaries that are provided by the operating system, such as virtualization, containers, or user accounts for running processes with the minimum set of privileges.</span></span>

### <a name="security-transparency"></a><span data-ttu-id="956ef-239">보안 투명도</span><span class="sxs-lookup"><span data-stu-id="956ef-239">Security Transparency</span></span>

<span data-ttu-id="956ef-240">CAS와 마찬가지로 보안 투명도는 샌드박스 코드를 보안상 중요한 코드와 선언적인 방식으로 분리할 수 있지만 더 이상 보안 경계로서 지원되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-240">Similar to CAS, Security Transparency separates sandboxed code from security critical code in a declarative fashion but is no longer supported as a security boundary.</span></span>

<span data-ttu-id="956ef-241">최소 권한 집합으로 프로세스를 실행 하기 위해 가상화, 컨테이너 또는 사용자 계정과 같은 운영 체제에서 제공 하는 보안 경계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="956ef-241">Use security boundaries that are provided by the operating system, such as virtualization, containers, or user accounts for running processes with the least set of privileges.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="956ef-242">[이전](whats-new-dotnet-core.md )
>[다음](windows-migration.md)</span><span class="sxs-lookup"><span data-stu-id="956ef-242">[Previous](whats-new-dotnet-core.md )
[Next](windows-migration.md)</span></span>
