---
title: ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: 9cc5141805504bc46391105f475860b032f12d32
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600233"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어
<xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 클래스는 애플리케이션 수준에서 생성되는 인스턴스 또는 세션의 수를 제한하기 위해 사용할 수 있는 속성을 노출합니다. 이 동작을 사용 하 여 WCF (Windows Communication Foundation) 응용 프로그램의 성능을 세밀 하 게 조정할 수 있습니다.  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>서비스 인스턴스 및 동시 호출 제어  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 클래스를 통해 처리 중인 최대 메시지 수를 지정하려면 <xref:System.ServiceModel.ServiceHost> 속성을 사용하고, 서비스의 최대 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 개체 수를 지정하려면 <xref:System.ServiceModel.InstanceContext> 속성을 사용합니다.  
  
 일반적으로 이러한 속성에 대 한 설정을 결정 하는 작업은 로드에 대해 응용 프로그램을 실행 한 후에 발생 하므로 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 일반적으로 응용 프로그램 구성 파일에서 요소를 사용 하 여 속성에 대 한 설정을 지정 합니다 [\<serviceThrottling>](../../configure-apps/file-schema/wcf/servicethrottling.md) .  
  
 다음 코드 예제에서는 애플리케이션 구성 파일에서 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 클래스를 사용하여 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 속성을 1로 설정하는 간단한 예를 보여 줍니다. 실제 경험을 통해 특정 애플리케이션에 대한 최적의 설정을 결정합니다.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 정확한 런타임 동작은 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> 및 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성의 값에 따라 다르며, 이 속성은 각각 작업에서 한 번에 실행 가능한 메시지 수와 수신 채널 세션 수를 기준으로 <xref:System.ServiceModel.InstanceContext> 서비스의 수명을 제어합니다.  
  
 자세한 내용은 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
