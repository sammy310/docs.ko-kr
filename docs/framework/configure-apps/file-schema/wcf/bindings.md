---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: 479941593b1abefe637525703140b02917c6692b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316793"
---
# <a name="bindings"></a>\<bindings>

사용할 수는 `bindings` 표준 및 사용자 지정 바인딩의 Windows Communication Foundation (WCF)에 대 한 컬렉션을 구성 하는 요소입니다. 각 항목은 고유한 `binding`으로 식별될 수 있는 `name` 요소입니다. 서비스에서는 `name`을 통해 바인딩을 연결하여 바인딩을 사용합니다. [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다. 기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.  
  
## <a name="system-provided-bindings"></a>시스템 제공 바인딩
 
 시스템 제공 바인딩은 WCF 메시지 스택의 복잡성을 숨깁니다. 시스템 제공 바인딩을 사용하는 응용 프로그램은 스택을 완전히 제어할 필요가 없습니다. 각 시스템 제공 바인딩에는 바인딩이 처리하는 사용 시나리오에 가장 적합한 특성이 노출됩니다.  
  
 각 시스템 제공 바인딩의 구성 섹션은 바인딩 구성에 사용되는 일부 구성을 정의할 수 있습니다. 각 구성은 고유한 이름으로 식별됩니다.  
  
 시스템 제공 바인딩에 요소나 특성을 추가할 수는 없습니다. 그렇게 하려면 구현 해야에 설명 된 대로 사용자 지정 바인딩을 합니다 [사용자 지정 바인딩](#custom-bindings) 섹션입니다. 시스템 제공 바인딩을 완벽 하 게 모방 하 고 사용자 응용 프로그램을 통해 제어 하려는 몇 가지 설정을 추가 하는 사용자 지정 바인딩을 정의 하는 것이 가능 합니다.  
  
 시스템 제공 바인딩 목록은 참조 하세요 [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md)합니다.  
  
## <a name="custom-bindings"></a>사용자 지정 바인딩

 사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다. 개별 바인딩에서는 스택에 나타나는 순서대로 스택 요소의 구성 요소를 지정함으로써 메시지 스택을 정의하며, 각 요소를 정의 하 고 스택의 한 요소를 구성 합니다. 각 사용자 지정 바인딩에는 `transport` 요소가 하나만 있어야 합니다. 이 요소가 없으면 메시징 스택이 완전하지 않습니다.  
  
 스택에서 요소가 나타나는 순서는 작업이 메시지에 적용되는 순서이므로 중요합니다. 다음과 같은 스택 요소 순서를 사용해야 합니다.  
  
1. Transactions(선택적)  
  
2. Reliable messaging (선택적)  
  
3. Security(선택적)  
  
4. 인코더  
  
5. 전송  
  
 사용자 지정 바인딩은 `name` 특성으로 식별됩니다. 사용자 지정 바인딩에 대 한 자세한 내용은 참조 하세요. [사용자 지정 바인딩을](../../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>  
- [바인딩](../../../../../docs/framework/wcf/bindings.md)  
- [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
- [\<binding>](../../../../../docs/framework/misc/binding.md)
