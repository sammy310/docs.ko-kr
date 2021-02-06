---
description: '자세한 정보: 채택 Windows Communication Foundation'
title: Windows Communication Foundation 채택
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: c8d5808b246e40b504d2d07dcdd6dc3fd622361d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643919"
---
# <a name="adopt-windows-communication-foundation"></a>Windows Communication Foundation 채택

ASP.NET를 사용 하 여 개발 된 기존 응용 프로그램을 계속 유지 하면서 새로운 개발에 WCF (Windows Communication Foundation)를 사용 하도록 선택할 수 있습니다. WCF는 어떤 시나리오에서 .NET Framework로 빌드된 응용 프로그램과의 통신을 용이 하 게 하는 데 가장 적합 한 선택 이기 때문에 ASP.NET 수 없는 방식으로 다양 한 소프트웨어 통신 문제를 해결 하기 위한 표준 도구로 사용할 수 있습니다.

새 WCF 응용 프로그램은 기존 ASP.NET 웹 서비스와 동일한 컴퓨터에 배포할 수 있습니다. 기존 ASP.NET 웹 서비스가 2.0 이전 버전의 .NET Framework을 사용 하는 경우 ASP.NET IIS 등록 도구를 사용 하 여 새 WCF 응용 프로그램을 호스팅할 IIS 응용 프로그램에 .NET Framework 2.0를 선택적으로 배포할 수 있습니다. 이 도구는 [ASP.NET Aspnet_regiis.exe (Iis 등록 도구)](/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))에 설명 되어 있으며 iis 6.0 관리 콘솔에 기본 제공 되는 사용자 인터페이스를 포함 합니다.

WCF는 ASP.NET 호환 모드에서 실행 되도록 구성 된 WCF 서비스를 IIS의 기존 ASP.NET 웹 서비스 응용 프로그램에 추가 하 여 기존 ASP.NET 웹 서비스에 새 기능을 추가 하는 데 사용할 수 있습니다. ASP.NET 호환성 모드로 인해 새 WCF 서비스의 코드는 클래스를 사용 하 여 기존 ASP.NET 코드와 동일한 응용 프로그램 상태 정보에 액세스 하 고 업데이트할 수 있습니다 <xref:System.Web.HttpContext> . 또한 애플리케이션은 동일한 클래스 라이브러리를 공유할 수도 있습니다.

WCF 클라이언트는 ASP.NET 웹 서비스를 사용할 수 있습니다. ASP.NET 웹 서비스 클라이언트는를 사용 하 여 구성 된 WCF 서비스를 <xref:System.ServiceModel.BasicHttpBinding> 사용할 수 있습니다. ASP.NET 웹 서비스는 WCF 응용 프로그램과 함께 사용할 수 있으며 WCF는 기존 ASP.NET 웹 서비스에 기능을 추가 하는 데도 사용할 수 있습니다. Wcf 및 ASP.NET 웹 서비스를 함께 사용할 수 있는 이러한 모든 방법을 고려 하 여 WCF에서 제공 하 고 ASP.NET 웹 서비스에서 제공 하지 않는 기능이 필요한 경우에만 ASP.NET 웹 서비스를 WCF로 마이그레이션할 수 있습니다.

필요한 경우에도 한 기술에서 다른 기술로 코드를 마이그레이션하는 것은 거의 적절 하지 않은 방법입니다. 새 기술을 채택 하는 이유는 이전 기술로 충족 될 수 없는 새로운 요구 사항을 충족 하는 것입니다 .이 경우에는 새로 확장 된 요구 사항 집합을 충족 하도록 새 솔루션을 설계 하는 것이 좋습니다. 새롭게 디자인할 경우 기존 시스템에 대한 사용자 경험과 시스템이 디자인된 이후 얻은 지식을 활용할 수 있습니다. 또한 새 플랫폼에서 기존 디자인을 재현하지 않고 새 기술의 전체 기능을 사용할 수도 있습니다. 새 디자인의 주요 요소를 프로토타입 하 고 나면 새 디자인 내에서 기존 시스템의 코드를 더 쉽게 다시 사용할 수 있게 됩니다.

## <a name="see-also"></a>참고 항목

- [방법: 메타데이터 검색 및 규정 준수 서비스 구현](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
