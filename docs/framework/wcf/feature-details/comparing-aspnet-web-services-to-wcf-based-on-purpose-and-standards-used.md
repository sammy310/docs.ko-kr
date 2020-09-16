---
title: 용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 1bd3a23d90680568bb2f909dec7902f967895495
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556670"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교
ASP.NET Web 서비스는 HTTP에서 SOAP(Simple Object Access Protocol)를 사용하여 메시지를 보내고 받는 애플리케이션을 빌드하기 위해 개발되었습니다. 메시지 구조는 XML 스키마를 사용하여 정의할 수 있으며 메시지를 .NET Framework 개체로 또는 그 반대로 쉽게 serialize하기 위한 도구가 제공됩니다. 이 기술은 자동으로 메타데이터를 생성하여 WSDL(웹 서비스 기술 언어)로 웹 서비스를 설명할 수 있으며 WSDL에서 웹 서비스용 클라이언트를 생성하기 위한 두 번째 도구가 제공됩니다.  
  
 WCF는 .NET Framework 응용 프로그램이 다른 소프트웨어 엔터티와 메시지를 교환할 수 있도록 하기 위한 것입니다. 기본적으로 SOAP가 사용되지만 메시지는 임의의 형식일 수 있으며 모든 전송 프로토콜을 사용하여 전달할 수 있습니다. 메시지 구조는 XML 스키마를 사용하여 정의할 수 있으며 메시지를 .NET Framework 개체로 또는 그 반대로 쉽게 serialize하기 위한 다양한 옵션이 제공됩니다. WCF는 WSDL에서 기술을 사용 하 여 빌드한 응용 프로그램을 설명 하는 메타 데이터를 자동으로 생성할 수 있으며, WSDL에서 이러한 응용 프로그램용 클라이언트를 생성 하기 위한 도구도 제공 합니다.  
  
 ASP.NET 웹 서비스에서 지 원하는 표준은 [ASP.NET를 사용 하 여 만든 XML Web services의 이점](/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100))에 설명 되어 있습니다. WCF에서 지원 되는 더 광범위 한 표준 목록은 [시스템 제공 상호 운용성 바인딩에서 지 원하는 웹 서비스 프로토콜](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)에 나와 있습니다.  
  
## <a name="see-also"></a>참조

- [개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교](comparing-aspnet-web-services-to-wcf-based-on-development.md)
