---
title: 추가 CLI 도구
description: .NET Core 기능을 지원하고 확장하는, 설치 가능한 추가 도구에 대한 개요입니다.
author: mlacouture
ms.date: 12/02/2019
ms.custom: mvc
ms.openlocfilehash: 1f066523a24d4e1fd7aaaa5a19e8d6c9d72d35af
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714530"
---
# <a name="net-core-additional-tools-overview"></a>.NET Core 추가 도구 개요

이 섹션에서는 [.NET Core CLI (명령줄 인터페이스)](../tools/index.md) 도구 외에 .NET Core 기능을 지원하고 확장하는 도구 목록을 컴파일합니다.

## <a name="net-core-uninstall-tooluninstall-toolmd"></a>[.NET Core 제거 도구](uninstall-tool.md)

[.NET Core 제거 도구](https://dotnet.microsoft.com/download/dotnet-core/uninstall-tool)(`dotnet-core-uninstall`)를 사용하면 지정한 버전만 유지되도록 시스템에서 .NET Core SDK 및 런타임을 정리할 수 있습니다. 제거되는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web Service Reference 도구](wcf-web-service-reference-guide.md)

WCF(Windows Communication Foundation) Web Service Reference는 [Visual Studio 2017 버전 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools)에서 처음 공개된 Visual Studio 연결된 서비스 공급자입니다. 이 도구는 WSDL 파일, 네트워크 위치 또는 현재 솔루션의 웹 서비스에서 메타데이터를 검색합니다. 웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET Core와 호환되는 소스 파일을 생성합니다.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[WCF dotnet-svcutil 도구](dotnet-svcutil-guide.md)

WCF(Windows Communication Foundation) dotnet-svcutil 도구는 WSDL 파일 또는 네트워크 위치의 웹 서비스에서 메타데이터를 검색하는 .NET Core CLI 도구입니다. 웹 서비스 작업에 액세스하는 데 사용할 수 있는 메서드로 WCF 프록시 클래스를 정의하여 .NET Core와 호환되는 소스 파일을 생성합니다.

**dotnet-svcutil** 도구는 Visual Studio 2017 버전 15.5와 함께 처음 제공된 [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio 연결 서비스 공급자에 대한 대체 옵션입니다. .NET Core CLI 도구인 **dotnet-svcutil** 도구는 Linux, macOS, Windows에서 플랫폼 간에 사용할 수 있습니다.

## <a name="wcf-dotnet-svcutilxmlserializer-tooldotnet-svcutilxmlserializer-guidemd"></a>[WCF dotnet-svcutil.xmlserializer 도구](dotnet-svcutil.xmlserializer-guide.md)

.NET Framework에서 svcutil 도구를 사용하여 serialization 어셈블리를 미리 생성할 수 있습니다. dotnet-svcutil.xmlserializer NuGet 패키지는 .NET Core에서 유사한 기능을 제공합니다. WCF 서비스 계약에서 사용되고 <xref:System.Xml.Serialization.XmlSerializer>를 통해 직렬화할 수 있는 클라이언트 애플리케이션의 형식에 대해 C# serialization 코드를 미리 생성합니다. 이렇게 하면 해당 형식의 개체를 직렬화 또는 역직렬화할 때 XML serialization의 시작 성능이 향상됩니다.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML Serializer Generator](xml-serializer-generator.md)

.NET Framework용 [Xml Serializer Generator(sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md)와 마찬가지로, [Microsoft.XmlSerializer.Generator NuGet 패키지](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator)는 .NET Core 및 .NET Standard 라이브러리용 솔루션입니다. <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 해당 형식의 개체를 직렬화하거나 역직렬화할 때 XML serialization의 시작 성능을 향상시키기 위해 어셈블리에 포함된 형식의 XML serialization 어셈블리를 만듭니다.
