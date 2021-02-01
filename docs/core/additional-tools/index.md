---
title: 추가 도구
description: .NET 기능을 지원하고 확장하는, 설치 가능한 추가 도구에 대한 개요입니다.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: 243f2da1c6f7809ac710c9700ea4cbde6f289295
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216397"
---
# <a name="net-additional-tools-overview"></a><span data-ttu-id="155f8-103">.NET 추가 도구 개요</span><span class="sxs-lookup"><span data-stu-id="155f8-103">.NET additional tools overview</span></span>

<span data-ttu-id="155f8-104">이 섹션에서는 .NET CLI 외에 .NET 기능을 지원하고 확장하는 도구 목록을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-104">This section compiles a list of tools that support and extend the .NET functionality, in addition to the .NET CLI.</span></span>

## <a name="net-uninstall-tool"></a><span data-ttu-id="155f8-105">.NET 제거 도구</span><span class="sxs-lookup"><span data-stu-id="155f8-105">.NET Uninstall Tool</span></span>

<span data-ttu-id="155f8-106">[.NET 제거 도구](https://github.com/dotnet/cli-lab/releases)(`dotnet-core-uninstall`)를 사용하면 지정한 버전만 유지되도록 시스템에서 .NET SDK 및 런타임을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-106">The [.NET Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you clean up .NET SDKs and Runtimes on a system such that only the specified versions remain.</span></span> <span data-ttu-id="155f8-107">제거되는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-107">A collection of options is available to specify which versions are uninstalled.</span></span>

## <a name="net-diagnostic-tools"></a><span data-ttu-id="155f8-108">.NET 진단 도구</span><span class="sxs-lookup"><span data-stu-id="155f8-108">.NET diagnostic tools</span></span>

<span data-ttu-id="155f8-109">[dotnet-counters](../diagnostics/dotnet-counters.md)는 1단계 상태 모니터링 및 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-109">[dotnet-counters](../diagnostics/dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span>

<span data-ttu-id="155f8-110">[dotnet-dump](../diagnostics/dotnet-dump.md)는 네이티브 디버거 없이 Windows 및 Linux 코어 덤프를 수집하고 분석하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-110">[dotnet-dump](../diagnostics/dotnet-dump.md) provides a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

<span data-ttu-id="155f8-111">[dotnet-gcdump](../diagnostics/dotnet-gcdump.md)로 라이브 .NET 프로세스의 GC(가비지 수집기) 덤프를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-111">[dotnet-gcdump](../diagnostics/dotnet-gcdump.md) provides a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

<span data-ttu-id="155f8-112">[dotnet-trace](../diagnostics/dotnet-trace.md)는 앱이 느리게 실행되는 이유를 확인해야 하는 시나리오에서 도움이 될 수 있는 프로파일링 데이터를 앱에서 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-112">[dotnet-trace](../diagnostics/dotnet-trace.md) collects profiling data from your app that can help in scenarios where you need to find out what causes an app to run slow.</span></span>

## <a name="net-install-tool-for-extension-authors"></a><span data-ttu-id="155f8-113">확장 프로그램 작성자를 위한 .NET 설치 도구</span><span class="sxs-lookup"><span data-stu-id="155f8-113">.NET Install tool for extension authors</span></span>

<span data-ttu-id="155f8-114">[확장 프로그램 작성자를 위한 .NET 설치 도구](https://github.com/dotnet/vscode-dotnet-runtime)는 VS Code 확장 프로그램 작성자를 위해 특별히 .NET 런타임 획득을 허용하는 Visual Studio Code 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-114">The [.NET Install tool for extension authors](https://github.com/dotnet/vscode-dotnet-runtime) is a Visual Studio Code extension that allows acquisition of the .NET runtime specifically for VS Code extension authors.</span></span> <span data-ttu-id="155f8-115">이 도구는 .NET에서 작성된 확장에 활용되며 확장(예: 언어 서버)을 부팅하기 위해 .NET이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-115">This tool is intended to be leveraged in extensions that are written in .NET and require .NET to boot pieces of the extension (for example, a language server).</span></span> <span data-ttu-id="155f8-116">확장은 사용자가 개발용 .NET을 설치하는 데 직접 사용하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-116">The extension is not intended to be used directly by users to install .NET for development.</span></span>

## <a name="wcf-web-service-reference-tool"></a><span data-ttu-id="155f8-117">WCF Web Service Reference 도구</span><span class="sxs-lookup"><span data-stu-id="155f8-117">WCF Web Service Reference tool</span></span>

<span data-ttu-id="155f8-118">WCF(Windows Communication Foundation) [Web Service Reference 도구](wcf-web-service-reference-guide.md)는 [Visual Studio 2017 버전 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-118">The WCF (Windows Communication Foundation) [Web Service Reference tool](wcf-web-service-reference-guide.md) is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools).</span></span> <span data-ttu-id="155f8-119">이 도구는 WSDL 파일, 네트워크 위치 또는 현재 솔루션의 웹 서비스에서 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-119">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file.</span></span> <span data-ttu-id="155f8-120">웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET과 호환되는 소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-120">It generates a source file compatible with .NET, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span>

## <a name="wcf-dotnet-svcutil-tool"></a><span data-ttu-id="155f8-121">WCF dotnet-svcutil 도구</span><span class="sxs-lookup"><span data-stu-id="155f8-121">WCF dotnet-svcutil tool</span></span>

<span data-ttu-id="155f8-122">WCF [dotnet-svcutil 도구](dotnet-svcutil-guide.md)는 WSDL 파일 또는 네트워크 위치의 웹 서비스에서 메타데이터를 검색하는 .NET 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-122">The WCF [dotnet-svcutil tool](dotnet-svcutil-guide.md) is a .NET tool that retrieves metadata from a web service on a network location or from a WSDL file.</span></span> <span data-ttu-id="155f8-123">웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET과 호환되는 소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-123">It generates a source file compatible with .NET, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span>

<span data-ttu-id="155f8-124">**dotnet-svcutil** 도구는 Visual Studio 2017 버전 15.5와 함께 처음 제공된 [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio 연결 서비스 공급자를 대체하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-124">The **dotnet-svcutil** tool is an alternative to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider, which first shipped with Visual Studio 2017 version 15.5.</span></span> <span data-ttu-id="155f8-125">.NET 도구인 **dotnet-svcutil** 도구는 Linux, macOS 및 Windows에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-125">The **dotnet-svcutil** tool, as a .NET tool, is available on Linux, macOS, and Windows.</span></span>

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a><span data-ttu-id="155f8-126">WCF dotnet-svcutil.xmlserializer 도구</span><span class="sxs-lookup"><span data-stu-id="155f8-126">WCF dotnet-svcutil.xmlserializer tool</span></span>

<span data-ttu-id="155f8-127">.NET Framework에서 svcutil 도구를 사용하여 serialization 어셈블리를 미리 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-127">On the .NET Framework, you can pre-generate a serialization assembly using the svcutil tool.</span></span> <span data-ttu-id="155f8-128">WCF [dotnet-svcutil.xmlserializer 도구](dotnet-svcutil.xmlserializer-guide.md) 는 .NET 5(및 .NET Core) 이상 버전에서 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-128">The WCF [dotnet-svcutil.xmlserializer tool](dotnet-svcutil.xmlserializer-guide.md) provides similar functionality on .NET 5 (and .NET Core) and later versions.</span></span> <span data-ttu-id="155f8-129">WCF 서비스 계약에서 사용되고 <xref:System.Xml.Serialization.XmlSerializer>를 통해 직렬화할 수 있는 클라이언트 애플리케이션의 형식에 대해 C# serialization 코드를 미리 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-129">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="155f8-130">이렇게 하면 해당 형식의 개체를 직렬화 또는 역직렬화할 때 XML serialization의 시작 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-130">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="xml-serializer-generator"></a><span data-ttu-id="155f8-131">XML Serializer Generator</span><span class="sxs-lookup"><span data-stu-id="155f8-131">XML Serializer Generator</span></span>

<span data-ttu-id="155f8-132">.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET 5(및 .NET Core) 이상 버전을 대상으로 하는 라이브러리용 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-132">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for libraries that target .NET 5 (and .NET Core) and later versions.</span></span> <span data-ttu-id="155f8-133"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-133">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="generating-self-signed-certificates"></a><span data-ttu-id="155f8-134">자체 서명된 인증서 생성</span><span class="sxs-lookup"><span data-stu-id="155f8-134">Generating Self-Signed Certificates</span></span>

<span data-ttu-id="155f8-135">[dotnet dev-certs](self-signed-certificates-guide.md)를 사용하여 개발 및 테스트 시나리오를 위한 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="155f8-135">You can use [dotnet dev-certs](self-signed-certificates-guide.md) to create self-signed certificates for development and testing scenarios.</span></span>
