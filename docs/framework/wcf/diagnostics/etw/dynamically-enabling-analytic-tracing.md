---
title: 동적으로 분석 추적을 사용하도록 설정
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: 22d122f802e82c2aa04d72a996cb872e06fcaeaa
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674950"
---
# <a name="dynamically-enabling-analytic-tracing"></a>동적으로 분석 추적을 사용하도록 설정
Windows 운영 체제에 포함된 도구와 함께 ETW(Event Tracing for Windows)를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정할 수 있습니다. 모든 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF(Windows 통신 재단) 서비스의 경우 응용 프로그램의 Web.config 파일을 수정하거나 서비스를 다시 시작하지 않고도 분석 추적을 동적으로 활성화하고 비활성화할 수 있습니다. 그러면 애플리케이션을 중지하지 않고도 추적 이벤트를 내보낼 수 있습니다.  
  
 WCF 추적 옵션도 비슷한 방식으로 구성할 수 있습니다. 예를 들어 애플리케이션을 중지하지 않고도 심각도 수준을 **Error** 에서 **Information** 으로 변경할 수 있습니다. 이 작업은 다음과 같은 도구를 사용하여 수행할 수 있습니다.  
  
- **Logman** – 추적 데이터를 구성, 제어 및 쿼리하기 위한 명령줄 도구입니다. 자세한 내용은 [로그맨 추적 및](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788036(v=ws.10)) [로그맨 업데이트 추적](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788128(v=ws.10))을 참조하십시오.  
  
- **EventViewer** - 추적 결과를 보기 위한 Windows 그래픽 관리 도구입니다. 자세한 내용은 Windows 및 이벤트 [뷰어에](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766042(v=ws.11)) [대한 WCF 서비스 및 이벤트 추적을](../../samples/wcf-services-and-event-tracing-for-windows.md) 참조하십시오.  
  
- **Perfmon** – 카운터를 사용하여 추적이 시스템 성능에 미치는 영향과 추적 카운터를 모니터링하는 Windows 그래픽 관리 도구입니다. 자세한 내용은 [데이터 수집기 집합 을 수동으로 작성을](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766404(v=ws.11))참조하십시오.  
  
### <a name="keywords"></a>키워드  
 일반적으로 <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> 클래스를 사용하는 경우 .NET Framework 추적 메시지가 심각도 수준(예: Error, Warning 및 Information)을 기준으로 필터링됩니다. ETW는 이러한 심각도 수준 개념을 지원할 뿐 아니라 키워드를 사용하는 새롭고 유연한 필터 메커니즘도 지원합니다. 키워드는 추적 이벤트를 통해 각 이벤트가 무엇을 의미하는지에 대한 추가 컨텍스트를 제공하는 데 사용할 수 있는 임의의 텍스트 값입니다.  
  
 WCF 분석 추적의 경우 각 추적 이벤트에는 두 가지 유형의 키워드가 있습니다. 첫 번째는 각 이벤트에 하나 이상 있는 시나리오 키워드입니다. 이러한 키워드는 각 이벤트가 지원하는 시나리오를 나타냅니다. 시나리오 키워드는 세 가지가 있는데, 각 키워드는 다음 표와 같이 고유한 용도로 설계되었습니다. 키워드를 사용한 필터링은 WCF 서비스를 방해하지 않고 동적으로 변경할 수 있습니다. 즉, 현재 추적 시나리오와 수집되는 추적 정보의 양을 동적으로 변경할 수 있습니다. 예를 들어 `HealthMonitoring` 을 `Troubleshooting` 으로 변경하고 추적 이벤트 세분성을 높일 수 있습니다.  
  
|키워드|Description|  
|-------------|-----------------|  
|`HealthMonitoring`|서비스의 작업을 모니터링할 수 있는 매우 간단한 최소한의 추적입니다.|  
|`EndToEndMonitoring`|메시지 흐름 추적을 지원하는 데 사용되는 이벤트입니다.|  
|`Troubleshooting`|WCF의 확장성 지점을 둘러싼 보다 세분화된 이벤트입니다.|  
  
 두 번째 키워드 그룹은 이벤트를 내보낸 .NET Framework의 구성 요소를 정의합니다.  
  
|키워드|Description|  
|-------------|-----------------|  
|`UserEvents`|.NET 프레임워크가 아닌 사용자 코드에서 내보낸 이벤트입니다.|  
|`ServiceModel`|WCF 런타임에서 내보낸 이벤트입니다.|  
|`ServiceHost`|서비스 호스트에서 내보내는 이벤트입니다.|  
|`WCFMessageLogging`|WCF 메시지 로깅 이벤트입니다.|  
  
## <a name="see-also"></a>참고 항목

- [WCF Services and Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
