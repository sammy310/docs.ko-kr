---
title: 관리되는 애플리케이션에서의 호스팅
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 759257edf89d1af5c453bb98f41361b54cf113ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597347"
---
# <a name="hosting-in-a-managed-application"></a>관리되는 애플리케이션에서의 호스팅
WCF (Windows Communication Foundation) 서비스는 모든 .NET Framework 응용 프로그램에서 호스팅될 수 있습니다. 자체 호스팅 서비스는 배포하는 데 최소한의 인프라를 필요로 하기 때문에 가장 유연한 호스팅 옵션입니다. 그러나 관리 되는 응용 프로그램은 인터넷 정보 서비스 (IIS) 및 Windows 서비스와 같은 WCF의 다른 호스팅 옵션에 대 한 고급 호스팅 및 관리 기능을 제공 하지 않기 때문에 가장 강력한 호스팅 옵션 이기도 합니다.  
  
 자체 호스팅 서비스를 만들려면 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만들고 열어, 여기서 서비스의 메시지 수신 대기를 시작합니다. 자세한 내용은 [방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](../how-to-host-a-wcf-service-in-a-managed-application.md)을 참조 하세요.  
  
 계약을 정의 하 고, 계약을 구현 하 고, 관리 되는 응용 프로그램 내에서 서비스를 호스트 하는 방법에 대 한 전체 예제는 [시작 자습서](../getting-started-tutorial.md) 및 [자체 호스트](../samples/self-host.md)를 참조 하세요.  
  
 다음 단원에서는 이 호스팅 옵션을 사용하는 일반적인 시나리오에 대해 설명합니다.  
  
## <a name="console-applications"></a>콘솔 애플리케이션  
 자체 호스팅을 사용 하는 일반적인 시나리오는 콘솔 응용 프로그램 내에서 실행 되는 WCF 서비스입니다. 콘솔 응용 프로그램 내에서 WCF 서비스를 호스트 하는 것은 일반적으로 서비스의 개발 단계에서 유용 합니다. 이 경우 쉽게 디버깅을 수행할 수 있으며, 애플리케이션 내에서 발생하는 상황을 확인하기 위한 추적 정보를 손쉽게 얻을 수 있으며, 새 위치에 서비스를 복사하여 이동하기 용이합니다.  
  
## <a name="rich-client-applications"></a>리치 클라이언트 애플리케이션  
 자체 호스팅을 사용 하는 다른 일반적인 시나리오는 Windows Presentation Foundation (WPF) 또는 Windows Forms (WinForms)를 기반으로 하는 클라이언트 응용 프로그램 등 다양 한 클라이언트 응용 프로그램입니다. 이 호스팅 옵션을 사용 하면 WPF 및 WinForms 응용 프로그램과 같은 리치 클라이언트 응용 프로그램에서 외부 대상과 통신할 수 있습니다. 예를 들어, 사용자 인터페이스에 WPF를 사용 하 고 다른 클라이언트가이 서비스에 연결 하 여 정보를 공유할 수 있도록 하는 WCF 서비스를 호스트 하는 피어 투 피어 공동 작업 클라이언트가 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [서비스 호스팅](../hosting-services.md)
- [초보자를 위한 자습서](../getting-started-tutorial.md)
