---
title: .NET Framework의 구성 파일 스키마
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: ab6f12be01899f5b7e54a7ec2d9675d502d88bc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555135"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="a4fcd-102">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a4fcd-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="a4fcd-103">구성 파일은 설정을 변경하고 응용 프로그램을 위한 정책을 설정하는 데 사용할 수 있는 표준 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="a4fcd-104">.NET Framework 구성 스키마는 응용 프로그램의 동작을 제어하기 위해 구성 파일에 사용할 수 있는 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="a4fcd-105">이 섹션의 목차에는 시작, 런타임, 네트워크 및 구성 설정의 다른 형식에 대한 스키마 계층 구조가 반영되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="a4fcd-106">구성 파일의 형식, 형식 및 위치에 대 한 자세한 내용은 [앱 구성](../index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-106">For information about the types, format, and location of configuration files, see [Configure apps](../index.md).</span></span> <span data-ttu-id="a4fcd-107">구성 파일을 직접 편집하려면 먼저 XML에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4fcd-108">구성 파일에서 XML 태그 및 특성은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a4fcd-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a4fcd-109">In this section</span></span>

<span data-ttu-id="a4fcd-110">[**\<configuration>** 요소인](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-110">[**\<configuration>** Element](configuration-element.md)</span></span>\
<span data-ttu-id="a4fcd-111">모든 구성 파일의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-111">The top-level element for all configuration files.</span></span>

<span data-ttu-id="a4fcd-112">[**\<assemblyBinding>** 요소인](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="a4fcd-113">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-113">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="a4fcd-114">[**\<linkedConfiguration>** 요소인](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span></span>\
<span data-ttu-id="a4fcd-115">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-115">Specifies a configuration file to include.</span></span>

<span data-ttu-id="a4fcd-116">[시작 설정 스키마](./startup/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-116">[Startup Settings Schema](./startup/index.md)</span></span>\
<span data-ttu-id="a4fcd-117">사용할 공용 언어 런타임의 버전을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-117">Elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="a4fcd-118">[런타임 설정 스키마](./runtime/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-118">[Runtime Settings Schema](./runtime/index.md)</span></span>\
<span data-ttu-id="a4fcd-119">어셈블리 바인딩 및 런타임 동작을 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-119">Elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="a4fcd-120">[네트워크 설정 스키마](./network/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-120">[Network Settings Schema](./network/index.md)</span></span>\
<span data-ttu-id="a4fcd-121">.NET Framework 인터넷에 연결 하는 방법을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-121">Elements that specify how the .NET Framework connects to the internet.</span></span>

<span data-ttu-id="a4fcd-122">[암호화 설정 스키마](./cryptography/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-122">[Cryptography Settings Schema](./cryptography/index.md)</span></span>\
<span data-ttu-id="a4fcd-123">암호화 알고리즘을 구현 하는 클래스에 알고리즘 이름을 매핑하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-123">Elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="a4fcd-124">[구성 섹션 스키마](configuration-sections-schema.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-124">[Configuration Sections Schema](configuration-sections-schema.md)</span></span>\
<span data-ttu-id="a4fcd-125">사용자 지정 설정에 대 한 구성 섹션을 만들고 사용 하는 데 사용 되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-125">Elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="a4fcd-126">[추적 및 디버그 설정 스키마](./trace-debug/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-126">[Trace and Debug Settings Schema](./trace-debug/index.md)</span></span>\
<span data-ttu-id="a4fcd-127">추적 스위치 및 수신기를 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-127">Elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="a4fcd-128">[컴파일러 및 언어 공급자 설정 스키마](./compiler/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-128">[Compiler and Language Provider Settings Schema](./compiler/index.md)</span></span>\
<span data-ttu-id="a4fcd-129">사용 가능한 언어 공급자의 컴파일러 구성을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-129">Elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="a4fcd-130">[응용 프로그램 설정 스키마](application-settings-schema.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-130">[Application Settings Schema](application-settings-schema.md)</span></span>\
<span data-ttu-id="a4fcd-131">Windows Forms 또는 ASP.NET 응용 프로그램에서 응용 프로그램 범위 및 사용자 범위 설정을 저장 하 고 검색 하는 데 사용할 수 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-131">Elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="a4fcd-132">[앱 설정 스키마](./appsettings/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-132">[App Settings Schema](./appsettings/index.md)</span></span>\
<span data-ttu-id="a4fcd-133">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-133">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="a4fcd-134">[웹 설정 스키마](./web/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-134">[Web Settings Schema](./web/index.md)</span></span>\
<span data-ttu-id="a4fcd-135">ASP.NET가 IIS와 같은 호스트 응용 프로그램과 함께 작동 하는 방법을 구성 하기 위한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-135">Elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="a4fcd-136">*Aspnet.config* 파일에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-136">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="a4fcd-137">[Windows Forms 구성 스키마](winforms/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-137">[Windows Forms Configuration Schema](winforms/index.md)</span></span>\
<span data-ttu-id="a4fcd-138">다중 모니터 및 높은 DPI 지원과 같은 사용자 지정을 포함 하는 Windows Forms 응용 프로그램 구성 섹션의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-138">All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high-DPI support.</span></span>

<span data-ttu-id="a4fcd-139">[WCF 구성 스키마](./wcf/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-139">[WCF Configuration Schema](./wcf/index.md)</span></span>\
<span data-ttu-id="a4fcd-140">WCF 서비스 및 클라이언트 응용 프로그램을 구성 하는 데 사용할 수 있는 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-140">All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="a4fcd-141">[WCF 지시문 구문](./wcf-directive/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-141">[WCF Directive Syntax](./wcf-directive/index.md)</span></span>\
<span data-ttu-id="a4fcd-142">`@ServiceHost`.Svc 컴파일러에서 사용 하는 페이지 관련 특성을 정의 하는 지시문에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-142">Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="a4fcd-143">[WIF 구성 스키마](windows-identity-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="a4fcd-143">[WIF Configuration Schema](windows-identity-foundation/index.md)</span></span>\
<span data-ttu-id="a4fcd-144">WIF (Windows Identity Foundation) 구성 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-144">All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a4fcd-145">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a4fcd-145">Related sections</span></span>

<span data-ttu-id="a4fcd-146">[원격 설정 스키마](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4fcd-146">[Remoting Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span>\
<span data-ttu-id="a4fcd-147">리모팅을 구현하는 클라이언트 및 서버 응용 프로그램을 구성하는 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-147">Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="a4fcd-148">[ASP.NET Settings 스키마](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4fcd-148">[ASP.NET Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span>\
<span data-ttu-id="a4fcd-149">ASP.NET 웹 응용 프로그램의 동작을 제어하는 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-149">Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="a4fcd-150">[웹 서비스 설정 스키마](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4fcd-150">[Web Services Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span>\
<span data-ttu-id="a4fcd-151">ASP.NET 웹 서비스와 해당 클라이언트를 제어하는 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-151">Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="a4fcd-152">[.NET Framework 앱 구성](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4fcd-152">[Configuring .NET Framework Apps](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span></span>\
<span data-ttu-id="a4fcd-153">.NET Framework에서 보안, 어셈블리 바인딩 및 리모팅을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fcd-153">Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
