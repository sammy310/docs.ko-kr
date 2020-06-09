---
title: 인터넷 정보 서비스에서의 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: baf13af39fe575a75f1304b21f3b4ad70dd370ab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597321"
---
# <a name="host-in-internet-information-services"></a>인터넷 정보 서비스 호스트

WCF (Windows Communication Foundation) 서비스를 호스팅하는 한 가지 옵션은 인터넷 정보 서비스 (IIS) 응용 프로그램 내에 있습니다. 이 호스팅 모델은 ASMX (ASP.NET and ASP.NET Web services) 웹 서비스에서 사용 하는 모델과 유사 합니다.

## <a name="versions-of-iis"></a>IIS 버전

WCF는 다음 운영 체제에 대해 다음 버전의 IIS에서 호스팅될 수 있습니다.

- Windows XP s p 2의 IIS 5.1. 이 환경은 나중에 Windows Server 2003와 같은 서버 운영 체제에 배포 되는 IIS에서 호스팅되는 응용 프로그램을 디자인 하 고 개발 하는 데 유용 합니다.

- Windows Server 2003의 IIS 6.0. IIS 6.0은 향상된 확장성, 안정성 및 응용 프로그램 격리 기능을 제공하는 고급 프로세스 모델을 사용합니다. 이 환경은 HTTP 통신을 독점적으로 사용 하는 WCF 서비스의 프로덕션 배포에 적합 합니다.

- Windows Vista 및 Windows Server 2008의 IIS 7.0. IIS 7.0는 IIS 6.0와 동일한 고급 프로세스 모델을 제공 하지만 WAS (Windows Process Activation Service)를 사용 하 여 HTTP 이외의 프로토콜을 통해 활성화 및 네트워크 통신을 허용 합니다. 이 환경은 WCF에서 지원 되는 모든 네트워크 프로토콜 (HTTP, net.tcp, net.pipe 및 net.pipe 포함)을 통해 통신 하는 WCF 서비스를 개발 하는 데 적합 합니다. WAS에 대 한 자세한 내용은 [Windows Process Activation Service에서 호스팅](hosting-in-windows-process-activation-service.md)을 참조 하세요.

- [Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10)) 은 IIS 7.0 및 WAS (Windows Process Activation Service)를 사용 하 여 여 net4 WCF 및 WF 서비스를 위한 풍부한 응용 프로그램 호스팅 환경을 제공 합니다. 이러한 기능에는 프로세스 수명 주기 관리, 프로세스 재활용, 공유 호스팅, 빠른 오류 보호, 프로세스 분리, 요청 시 활성화, 상태 모니터링 등이 포함됩니다. 자세한 내용은 [Appfabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10)) 및 [appfabric 호스팅 개념](https://docs.microsoft.com/previous-versions/appfabric/ee677371(v=azure.10))을 참조 하세요.

## <a name="benefits-of-iis-hosting"></a>IIS 호스팅의 이점

IIS에서 WCF 서비스를 호스팅하면 다음과 같은 여러 가지 이점이 있습니다.

- IIS에서 호스팅되는 WCF 서비스는 ASP.NET 응용 프로그램 및 ASMX를 비롯 한 다른 유형의 IIS 응용 프로그램과 마찬가지로 배포 및 관리 됩니다.

- IIS는 프로세스 활성화, 상태 관리 및 재활용 기능을 제공하여 호스트된 애플리케이션의 신뢰성이 향상됩니다.

- ASP.NET와 마찬가지로 ASP.NET에서 호스트 되는 WCF 서비스는 서버 밀도 및 확장성 향상을 위해 여러 응용 프로그램이 공통 작업자 프로세스에 상주 하는 ASP.NET 공유 호스팅 모델을 활용할 수 있습니다.

- IIS에서 호스팅되는 WCF 서비스는 호스트 된 서비스의 개발 및 배포를 간소화 하는 ASP.NET 2.0와 동일한 동적 컴파일 모델을 사용 합니다.

IIS에서 WCF 서비스를 호스팅하도록 결정할 때 IIS 5.1 및 IIS 6.0은 HTTP 통신 으로만 제한 됩니다. 호스팅 환경을 선택 하는 방법에 대 한 자세한 내용은 [호스팅 서비스](../hosting-services.md)를 참조 하세요.

## <a name="deploy-an-iis-hosted-wcf-service"></a>IIS에서 호스트 되는 WCF 서비스 배포

IIS에서 호스트 하는 WCF 서비스의 개발 및 배포는 다음과 같은 작업으로 구성 됩니다.

- IIS, ASP.NET, WCF 및 WCF HTTP 활성화 구성 요소가 제대로 설치 되 고 등록 되었는지 확인 합니다.

- 새 IIS 응용 프로그램을 만들거나 기존 ASP.NET 응용 프로그램을 다시 사용 합니다.

- WCF 서비스에 대 한 .svc 파일을 만듭니다.

- IIS 애플리케이션에 서비스 구현을 배포합니다.

- WCF 서비스를 구성 합니다.

이러한 각 작업에 대 한 설명은 [인터넷 정보 서비스 호스팅된 WCF 서비스 배포](deploying-an-internet-information-services-hosted-wcf-service.md)를 참조 하세요.

## <a name="wcf-services-and-aspnet"></a>WCF 서비스 및 ASP.NET

WCF 서비스는 서비스에서 ASP.NET 웹 응용 프로그램 플랫폼에서 제공 하는 기능을 모두 활용할 수 있는 ASP.NET 또는 ASP.NET 호환성 모드에서 함께 호스팅될 수 있습니다. 이러한 기능에 대 한 설명은 [WCF 서비스 및 ASP.NET](wcf-services-and-aspnet.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- [ServiceHostFactory를 사용하여 호스팅 확장명](../extending/extending-hosting-using-servicehostfactory.md)
- [인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포](deploying-an-internet-information-services-hosted-wcf-service.md)
- [WCF 서비스 및 ASP.NET](wcf-services-and-aspnet.md)
- [인터넷 정보 서비스 호스팅을 위한 최선의 방법](internet-information-services-hosting-best-practices.md)
- [Windows Communication Foundation에 대해 Internet Information Services 7.0 구성](configuring-iis-for-wcf.md)
- [Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
