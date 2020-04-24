---
title: 부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
ms.openlocfilehash: 61291a07639c3f92a05f78dff49f6b20f1aee77e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645715"
---
# <a name="using-libraries-from-partially-trusted-code"></a>부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> 이 항목에서는 강력한 이름의 어셈블리의 동작을 다루며 [수준 1](security-transparent-code-level-1.md) 어셈블리에만 적용됩니다. [.NET](security-transparent-code-level-2.md) Framework 4 이상에서 보안 투명 코드, 수준 2 어셈블리는 강력한 이름의 영향을 받지 않습니다. 보안 시스템의 변경 사항에 대한 자세한 내용은 [보안 변경](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)을 참조하십시오.  
  
 해당 호스트 또는 샌드박스로부터 완전 신뢰 미만을 받는 애플리케이션은 라이브러리 작성자가 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성을 사용하여 특별히 허용하지 않는 한 관리되는 공유 라이브러리를 호출할 수 없습니다. 따라서 애플리케이션 작성자는 부분적으로 신뢰할 수 있는 컨텍스트에서 일부 라이브러리가 제공되지 않음을 알고 있어야 합니다. 기본적으로 부분 신뢰 [샌드박스에서](how-to-run-partially-trusted-code-in-a-sandbox.md) 실행되고 완전 신뢰 어셈블리 목록에 없는 모든 코드는 부분적으로 신뢰할 수 있습니다. 코드가 부분적으로 신뢰할 수 있는 컨텍스트에서 실행되거나 부분적으로 신뢰할 수 있는 코드에서 호출되지 않는 경우에는 이 섹션의 내용에 주의할 필요가 없습니다. 그러나 부분적으로 신뢰할 수 있는 코드와 상호 작용하거나 부분적으로 신뢰할 수 있는 컨텍스트에서 작동해야 하는 코드를 작성하는 경우 다음과 같은 요소를 고려해야 합니다.  
  
- 여러 애플리케이션에서 공유하려면 강력한 이름으로 라이브러리에 서명해야 합니다. 강력한 이름을 사용하면 코드를 전역 어셈블리 캐시에 배치하거나 샌드박싱 <xref:System.AppDomain>의 완전 신뢰 목록에 추가할 수 있으며, 소비자가 모바일 코드의 특정 부분이 실제로 사용자가 제공한 것인지 확인할 수 있습니다.  
  
- 기본적으로 강력한 이름의 [수준 1](security-transparent-code-level-1.md) 공유 라이브러리는 라이브러리 작성자가 아무 작업도 수행하지 않고도 완전 신뢰에 대한 암시적 [LinkDemand를](link-demands.md) 자동으로 수행합니다.  
  
- 호출자에게 완전 신뢰가 없는데 이러한 라이브러리를 호출하려고 하면 런타임에서 <xref:System.Security.SecurityException>이 발생하고 호출자가 라이브러리에 연결할 수 없습니다.  
  
- 자동 **LinkDemand를** 사용하지 않도록 설정하고 예외가 throw되지 않도록 하려면 **허용PartiallyTrustedCallersAttribute** 특성을 공유 라이브러리의 어셈블리 범위에 배치할 수 있습니다. 이 특성을 사용하면 부분적으로 신뢰할 수 있는 관리 코드에서 라이브러리를 호출할 수 있습니다.  
  
- 이 특성을 사용하여 라이브러리 액세스 권한이 부여된, 부분적으로 신뢰할 수 있는 코드에는 여전히 <xref:System.AppDomain>에서 정의된 추가 제한 사항이 적용됩니다.  
  
- 부분적으로 신뢰할 수 있는 코드가 **AllowPartiallyTrustedCallersAttribute** 특성이 없는 라이브러리를 호출하는 프로그래밍 방식은 없습니다.  
  
 특정 응용 프로그램에 전용 라이브러리는 강력한 이름이나 **AllowPartiallyTrustedCallersAttribute** 특성이 필요하지 않으며 응용 프로그램 외부의 악의적인 코드에서 참조할 수 없습니다. 이러한 코드는 개발자가 특별한 작업을 수행하지 않아도 부분적으로 신뢰할 수 있는 모바일 코드에서 의도적이나 실수로 악용할 수 없도록 보호됩니다.  
  
 다음 형식의 코드에 대해서는 부분적으로 신뢰할 수 있는 코드가 사용할 수 있도록 명시적으로 설정하는 것이 좋습니다.  
  
- 보안 취약점에 대해 부지런히 테스트되었으며 [보안 코딩 지침에](../../standard/security/secure-coding-guidelines.md)설명된 지침을 준수하는 코드입니다.  
  
- 부분적으로 신뢰할 수 있는 시나리오를 위해 특별히 작성된 강력한 이름의 코드 라이브러리  
  
- 인터넷에서 다운로드된 코드에서 호출하는 강력한 이름으로 서명된 모든 구성 요소(부분적으로 또는 완전히 신뢰할 수 있는지에 관계없음)  
  
> [!NOTE]
> .NET Framework 클래스 라이브러리의 일부 클래스에는 **AllowPartiallyTrustedCallersAttribute** 특성이 없으며 부분적으로 신뢰할 수 있는 코드에서 호출할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목

- [코드 액세스 보안](code-access-security.md)
