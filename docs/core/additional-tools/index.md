---
title: 추가 도구
description: .NET Core 기능을 지원하고 확장하는, 설치 가능한 추가 도구에 대한 개요입니다.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: f563dff312442cbf068d52d08992621e3d6f1460
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699003"
---
# <a name="net-core-additional-tools-overview"></a><span data-ttu-id="2e9b8-103">.NET Core 추가 도구 개요</span><span class="sxs-lookup"><span data-stu-id="2e9b8-103">.NET Core additional tools overview</span></span>

<span data-ttu-id="2e9b8-104">이 섹션에서는 .NET Core CLI 외에 .NET Core 기능을 지원하고 확장하는 도구 목록을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the .NET Core CLI.</span></span>

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="2e9b8-105">.NET Core 제거 도구</span><span class="sxs-lookup"><span data-stu-id="2e9b8-105">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="2e9b8-106">[.NET Core 제거 도구](https://github.com/dotnet/cli-lab/releases)(`dotnet-core-uninstall`)를 사용하면 지정한 버전만 유지되도록 시스템에서 .NET Core SDK 및 런타임을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-106">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you clean up .NET Core SDKs and Runtimes on a system such that only the specified versions remain.</span></span> <span data-ttu-id="2e9b8-107">제거되는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-107">A collection of options is available to specify which versions are uninstalled.</span></span>

## <a name="net-core-diagnostic-tools"></a><span data-ttu-id="2e9b8-108">.NET Core 진단 도구</span><span class="sxs-lookup"><span data-stu-id="2e9b8-108">.NET Core diagnostic tools</span></span>

<span data-ttu-id="2e9b8-109">[dotnet-counters](../diagnostics/dotnet-counters.md)는 1단계 상태 모니터링 및 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-109">[dotnet-counters](../diagnostics/dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span>

<span data-ttu-id="2e9b8-110">[dotnet-dump](../diagnostics/dotnet-dump.md)는 네이티브 디버거 없이 Windows 및 Linux 코어 덤프를 수집하고 분석하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-110">[dotnet-dump](../diagnostics/dotnet-dump.md) provides a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

<span data-ttu-id="2e9b8-111">[dotnet-gcdump](../diagnostics/dotnet-gcdump.md)로 라이브 .NET 프로세스의 GC(가비지 수집기) 덤프를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-111">[dotnet-gcdump](../diagnostics/dotnet-gcdump.md) provides a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

<span data-ttu-id="2e9b8-112">[dotnet-trace](../diagnostics/dotnet-trace.md)는 앱이 느리게 실행되는 이유를 확인해야 하는 시나리오에서 도움이 될 수 있는 프로파일링 데이터를 앱에서 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-112">[dotnet-trace](../diagnostics/dotnet-trace.md) collects profiling data from your app that can help in scenarios where you need to find out what causes an app to run slow.</span></span>

## <a name="wcf-web-service-reference-tool"></a><span data-ttu-id="2e9b8-113">WCF Web Service Reference 도구</span><span class="sxs-lookup"><span data-stu-id="2e9b8-113">WCF Web Service Reference tool</span></span>

<span data-ttu-id="2e9b8-114">WCF(Windows Communication Foundation) [Web Service Reference 도구](wcf-web-service-reference-guide.md)는 [Visual Studio 2017 버전 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-114">The WCF (Windows Communication Foundation) [Web Service Reference tool](wcf-web-service-reference-guide.md) is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools).</span></span> <span data-ttu-id="2e9b8-115">이 도구는 WSDL 파일, 네트워크 위치 또는 현재 솔루션의 웹 서비스에서 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-115">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file.</span></span> <span data-ttu-id="2e9b8-116">웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET Core와 호환되는 소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-116">It generates a source file compatible with .NET Core, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span>

## <a name="wcf-dotnet-svcutil-tool"></a><span data-ttu-id="2e9b8-117">WCF dotnet-svcutil 도구</span><span class="sxs-lookup"><span data-stu-id="2e9b8-117">WCF dotnet-svcutil tool</span></span>

<span data-ttu-id="2e9b8-118">WCF [dotnet-svcutil 도구](dotnet-svcutil-guide.md)는 WSDL 파일 또는 네트워크 위치의 웹 서비스에서 메타데이터를 검색하는 .NET 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-118">The WCF [dotnet-svcutil tool](dotnet-svcutil-guide.md) is a .NET tool that retrieves metadata from a web service on a network location or from a WSDL file.</span></span> <span data-ttu-id="2e9b8-119">웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET Core와 호환되는 소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-119">It generates a source file compatible with .NET Core, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span>

<span data-ttu-id="2e9b8-120">**dotnet-svcutil** 도구는 Visual Studio 2017 버전 15.5와 함께 처음 제공된 [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio 연결 서비스 공급자를 대체하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-120">The **dotnet-svcutil** tool is an alternative to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider, which first shipped with Visual Studio 2017 version 15.5.</span></span> <span data-ttu-id="2e9b8-121">.NET 도구인 **dotnet-svcutil** 도구는 Linux, macOS 및 Windows에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-121">The **dotnet-svcutil** tool, as a .NET tool, is available on Linux, macOS, and Windows.</span></span>

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a><span data-ttu-id="2e9b8-122">WCF dotnet-svcutil.xmlserializer 도구</span><span class="sxs-lookup"><span data-stu-id="2e9b8-122">WCF dotnet-svcutil.xmlserializer tool</span></span>

<span data-ttu-id="2e9b8-123">.NET Framework에서 svcutil 도구를 사용하여 serialization 어셈블리를 미리 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-123">On the .NET Framework, you can pre-generate a serialization assembly using the svcutil tool.</span></span> <span data-ttu-id="2e9b8-124">WCF [dotnet-svcutil.xmlserializer 도구](dotnet-svcutil.xmlserializer-guide.md)는 .NET Core에서 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-124">The WCF [dotnet-svcutil.xmlserializer tool](dotnet-svcutil.xmlserializer-guide.md) provides similar functionality on .NET Core.</span></span> <span data-ttu-id="2e9b8-125">WCF 서비스 계약에서 사용되고 <xref:System.Xml.Serialization.XmlSerializer>를 통해 직렬화할 수 있는 클라이언트 애플리케이션의 형식에 대해 C# serialization 코드를 미리 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-125">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="2e9b8-126">이렇게 하면 해당 형식의 개체를 직렬화 또는 역직렬화할 때 XML serialization의 시작 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-126">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="xml-serializer-generator"></a><span data-ttu-id="2e9b8-127">XML Serializer Generator</span><span class="sxs-lookup"><span data-stu-id="2e9b8-127">XML Serializer Generator</span></span>

<span data-ttu-id="2e9b8-128">.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 라이브러리용 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-128">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="2e9b8-129"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-129">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="generating-self-signed-certificates"></a><span data-ttu-id="2e9b8-130">자체 서명된 인증서 생성</span><span class="sxs-lookup"><span data-stu-id="2e9b8-130">Generating Self-Signed Certificates</span></span>

<span data-ttu-id="2e9b8-131">[dotnet dev-certs](self-signed-certificates-guide.md)를 사용하여 개발 및 테스트 시나리오를 위한 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e9b8-131">You can use [dotnet dev-certs](self-signed-certificates-guide.md) to create self-signed certificates for development and testing scenarios.</span></span>
