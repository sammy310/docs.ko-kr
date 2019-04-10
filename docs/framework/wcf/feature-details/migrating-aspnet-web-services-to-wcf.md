---
title: ASP.NET 웹 서비스를 WCF로 마이그레이션
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 703088cdaae69d90d71fb950912538ea0662229b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211090"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>ASP.NET 웹 서비스를 WCF로 마이그레이션
ASP.NET은 .NET Framework 클래스 라이브러리 및 웹 서비스 빌드를 위한 도구뿐 아니라 인터넷 정보 서비스(IIS) 내 호스팅 서비스에 대한 기능도 제공합니다. Windows Communication Foundation (WCF)는.NET Framework 클래스 라이브러리, 도구 및 호스팅 기능 하므로 소프트웨어 엔터티가 웹 서비스에서 사용 되는 포함 하는 모든 프로토콜을 사용 하 여 통신을 제공 합니다.  ASP.NET 웹 서비스를 WCF로 마이그레이션에 새로운 기능 및 WCF에 고유한 향상 된 기능을 활용 하려면 응용을 프로그램 수 있습니다.  
  
 WCF에 ASP.NET 웹 서비스를 기준으로 하는 몇 가지 중요 한 장점이 있습니다. ASP.NET 웹 서비스 도구는 웹 서비스 구축을 위한 전적으로, WCF 소프트웨어 엔터티가 서로 통신할 수 있어야 하는 경우 사용할 수 있는 도구를 제공 합니다. 따라서 여러 소프트웨어 통신 시나리오를 적용하는 데 개발자가 알아야 하는 기술의 수가 적어지기 때문에 결과적으로는 소프트웨어 개발 프로젝트를 완료하는 데 필요한 시간뿐 아니라 소프트웨어 개발 리소스 비용을 줄일 수 있습니다.  
  
 웹 서비스 개발 프로젝트에 대해서도 WCF는 ASP.NET 웹 서비스 지원 보다 더 많은 웹 서비스 프로토콜을 지원합니다. 이러한 추가 프로토콜은 무엇보다도 신뢰할 수 있는 세션 및 트랜잭션이 사용되는 더욱 정교한 솔루션을 제공합니다.  
  
 WCF는 ASP.NET 웹 서비스 보다 메시지 전송에 대 한 자세한 프로토콜을 지원 합니다. ASP.NET 웹 서비스는 HTTP(Hypertext Transfer Protocol)를 사용하여 메시지 보내기만 지원합니다. WCF는 프로토콜 TCP (Transmission Control), 명명 된 파이프, Microsoft 메시지 큐 (MSMQ) 뿐만 아니라 HTTP를 사용 하 여 메시지 보내기를 지원 합니다. 더 중요 한 WCF 추가 전송 프로토콜을 지원 하도록 확장할 수 있습니다. 따라서 WCF를 사용 하 여 개발 하는 소프트웨어는 다양 한 잠재적 투자 수익을 높입니다 다른 소프트웨어와 함께 사용할 수 있습니다.  
  
 배포에 대 한 훨씬 더 풍부한 기능을 제공 하는 WCF 및 ASP.NET 웹 서비스 보다 응용 프로그램 관리를 제공 합니다. ASP.NET에도 있는 구성 시스템 외에도 WCF 제공 구성 편집기, 중간, 추적 뷰어, 메시지 로깅, 다양 한 성능 카운터의 수에 관계 없이 송수신 보낸에서 활동 추적 및 Windows Management Instrumentation을 지원 합니다.  
  
 를 사용 하는 몇 가지 옵션이 있습니다 ASP.NET 웹 서비스 사용을 고려 하는 경우 ASP.NET 웹 기준으로 하는 WCF의 이러한 잠재적 이점을 서비스를 지정 합니다.  
  
-   ASP.NET 웹 서비스를 사용 하는 이점은 WCF에서 계속 합니다.  
  
-   나중에 WCF를 채택할 의향을 갖고 ASP.NET 웹 서비스를 계속 사용 합니다. 이 섹션의에서 항목에서는 향후 WCF 응용 프로그램과 함께 새 ASP.NET 웹 서비스 응용 프로그램을 사용할 수 있는 가능성을 최대화 하는 방법에 설명 합니다. 이 섹션의 항목에는 또한 새 ASP.NET 웹 손쉽게 WCF로 마이그레이션하려는 서비스를 빌드하는 방법을 설명 합니다. 그러나 서비스 보안이 중요 하거나 신뢰성 또는 트랜잭션 보증이 필요 하거나 또는 사용자 지정 하는 경우 관리 기능을 하는 생성 될 WCF를 채택 하는 방법이 더 나을 것입니다. WCF는 이러한 시나리오에 정확 하 게 설계 되었습니다.  
  
-   기존 ASP.NET 웹 서비스 응용 프로그램을 유지 하면서 새로운 개발에 대 한 WCF를 채택 합니다. 이 선택이 최선의 선택일 가능성이 큽니다. WCF의 혜택을 사용 하 여 기존 응용 프로그램을 수정 하는 비용을 절약 하는 동안 생성 합니다. 이 시나리오에서는 새 WCF 응용 프로그램 기존 ASP.NET 응용 프로그램과 공존할 수 있습니다. 새 WCF 응용 프로그램은 기존 ASP.NET 웹 서비스를 사용할 수 하 고 WCF를 사용 하 여 기존 ASP.NET 응용 프로그램을 WCF ASP.NET 호환 모드 덕분에 새 작업 기능을 프로그래밍할 수 있습니다.  
  
-   WCF를 채택 하 고 WCF 기존 ASP.NET 웹 서비스 응용 프로그램을 마이그레이션하십시오. WCF에서 제공 하는 기능을 사용 하 여 기존 응용 프로그램을 강화 하기 위해 또는 더 강력한 WCF 응용 프로그램을 새 기존 ASP.NET 웹 서비스의 기능을 재현 하려면이 옵션을 선택할 수 있습니다.  
  
> [!NOTE]
>  WCF 서비스를 호스팅하는 경우 주의 기울여야 합니다 iis 5.x 및 ASP.NET을 제거 합니다. IIS에서 WCF 서비스 호스트 되는 경우 ASP.NET이 제거 된 경우 5.x를 서비스에 대 한 코드를 요청할 수 있습니다. IIS를 실행 하는 운영 체제에서 ASP.NET을 제거 하는 경우 5.x 및 WCF 제거 하 고,.svc 확장명을 가진 파일을 텍스트 파일로 간주 되므로, 소스 코드를 포함 하 여 콘텐츠를 요청자에 게 반환 됩니다.  
  
 이 섹션에서는 이러한 옵션을 자세히 설명, ASP.NET 웹 서비스와 WCF 비교 및 ASP.NET 웹 서비스 코드를 WCF로 마이그레이션하는 방법에 지침을 제공 합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Communication Foundation 채택에 대한 기대: 향후 마이그레이션 간소화](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
- [Windows Communication Foundation 채택에 대한 기대: 향후 통합 간소화](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
- [Windows Communication Foundation 채택](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)
- [용도와 사용되는 표준을 기반으로 ASP.NET 웹 서비스와 WCF 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
- [개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
