---
title: 기본 프로그래밍 수명 주기
description: WCF 응용 프로그램을 빌드하는 작업에 대해 알아봅니다. WCF를 사용 하면 앱이 동일한 컴퓨터, 네트워크 또는 다른 응용 프로그램 플랫폼에서 통신할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: c672827fff780fd263f5355520bb6ccf02bb902e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245533"
---
# <a name="basic-programming-lifecycle"></a>기본 프로그래밍 수명 주기
WCF (Windows Communication Foundation)를 사용 하면 응용 프로그램이 동일한 컴퓨터, 인터넷 또는 다른 응용 프로그램 플랫폼에 있든 간에 통신할 수 있습니다. 이 항목에서는 WCF 응용 프로그램을 빌드하는 데 필요한 작업에 대해 간략하게 설명 합니다. 작동 하는 샘플 응용 프로그램은 [시작 자습서](getting-started-tutorial.md)를 참조 하세요.  
  
## <a name="the-basic-tasks"></a>기본 작업  
 수행할 기본 작업 순서는 다음과 같습니다.  
  
1. 서비스 계약을 정의합니다. 서비스 계약은 서비스 서명, 서비스 교환 날짜 및 계약에 필요한 기타 데이터를 지정합니다. 자세한 내용은 [서비스 계약 디자인](designing-service-contracts.md)을 참조 하세요.  
  
2. 계약을 구현합니다. 서비스 계약을 구현하려면 계약을 구현하는 클래스를 만들고 런타임에 필요한 사용자 지정 동작을 지정합니다. 자세한 내용은 [서비스 계약 구현](implementing-service-contracts.md)을 참조 하세요.  
  
3. 엔드포인트 및 기타 동작 정보를 지정하여 서비스를 구성합니다. 자세한 내용은 [서비스 구성](configuring-services.md)을 참조 하세요.  
  
4. 서비스를 호스트합니다. 자세한 내용은 [호스팅 서비스](hosting-services.md)를 참조 하세요.  
  
5. 클라이언트 애플리케이션을 빌드합니다. 자세한 내용은 [클라이언트 빌드](building-clients.md)를 참조 하세요.  
  
 이 단원의 항목은 이 순서를 따르지만 일부 시나리오에서는 첫 번째 단계부터 시작하지 않는 경우도 있습니다. 예를 들어 기존 서비스에 대한 클라이언트를 빌드하려면 5단계에서 시작합니다. 다른 사용자가 사용할 서비스를 빌드하는 경우 5단계를 건너뜁니다.  
  
 서비스 계약 개발에 대해 잘 알고 있으면 [확장성 소개를](introduction-to-extensibility.md)읽을 수도 있습니다. 서비스에 문제가 있는 경우 [WCF 문제 해결 퀵 스타트](wcf-troubleshooting-quickstart.md) 를 확인 하 여 다른 사용자가 동일 하거나 유사한 문제를 발생 하는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목

- [서비스 계약 구현](implementing-service-contracts.md)
