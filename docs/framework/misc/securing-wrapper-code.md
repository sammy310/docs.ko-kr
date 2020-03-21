---
title: 래퍼 코드 보안
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], wrapper code
- wrapper code, securing
- secure coding, wrapper code
- code security, wrapper code
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
ms.openlocfilehash: 3d38a4d4fd33798cf5987f5ce67305725ad9daec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400934"
---
# <a name="securing-wrapper-code"></a>래퍼 코드 보안
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 특히 래퍼의 신뢰 수준이 래퍼를 사용하는 코드보다 더 높은 래퍼 코드는 고유한 보안 약점 집합을 초래할 수 있습니다. 호출자의 제한된 권한이 적절한 보안 검사에 포함되지 않은 경우 호출자 대신 수행되는 모든 작업은 악용되는 잠재적인 약점이 됩니다.  
  
 래퍼를 통해 호출자가 직접 수행할 수 없는 작업을 사용하도록 설정하지 마세요. 전체 스택 워크 요구와 반대인 제한된 보안 검사와 관련된 작업을 수행할 때는 특히 위험합니다. 단일 수준 검사가 관련된 경우 실제 호출자와 해당 API 요소 사이에 래퍼 코드를 삽입하면 보안 검사가 성공하지 않아야 할 때 쉽게 성공하여 보안이 약화될 수 있습니다.  
  
## <a name="delegates"></a>대리자  
 대리자 보안은 .NET Framework 버전마다 다릅니다.  이 섹션에서는 다양한 대리자 동작 및 관련된 보안 고려 사항을 설명합니다.  
  
### <a name="in-version-10-and-11-of-the-net-framework"></a>.NET Framework 버전 1.0 및 1.1  
 .NET Framework 버전 1.0 및 1.1에서는 대리자 작성자 및 대리자 호출자에 대해 다음과 같은 보안 동작을 수행합니다.  
  
- 대리자를 만들면 대리자 작성자의 권한 부여 집합에 대해 대리자 대상 메서드의 보안 링크 요구가 수행됩니다.  보안 동작을 충족하지 못하면 <xref:System.Security.SecurityException>이 발생합니다.  
  
- 대리자를 호출하면 대리자 호출자의 모든 기존 보안 요구가 수행됩니다.  
  
 사용자 코드가 해당 코드를 호출할 수 있는 덜 신뢰되는 코드에서 <xref:System.Delegate>를 가져오는 경우 덜 신뢰되는 코드가 권한을 에스컬레이션할 수 없도록 해야 합니다. 대리자를 가져와서 나중에 사용하는 경우 대리자를 만든 코드가 호출 스택에 없으며, 대리자의 코드에서 보호된 작업을 시도해도 해당 권한이 테스트되지 않습니다. 사용자 코드와 호출자 코드에 작성자보다 더 높은 권한이 있을 경우 작성자가 호출 스택에 포함되지 않아도 호출 경로를 조정할 수 있습니다.  
  
### <a name="in-version-20-and-later-versions-of-the-net-framework"></a>버전 2.0 및 이후 버전의 .NET 프레임워크  
 이전 버전과 달리 .NET Framework의 버전 2.0 및 이후 버전은 대리자를 만들고 호출할 때 대리자 작성자에 대한 보안 작업을 수행합니다.  
  
- 대리자를 만들면 대리자 작성자의 권한 부여 집합에 대해 대리자 대상 메서드의 보안 링크 요구가 수행됩니다.  보안 동작을 충족하지 못하면 <xref:System.Security.SecurityException>이 발생합니다.  
  
- 대리자를 만드는 동안 대리자 작성자의 권한 부여 집합도 캡처되어 대리자와 함께 저장됩니다.  
  
- 대리자를 호출하면 대리자 작성자와 호출자가 서로 다른 어셈블리에 속하는 경우 대리자 작성자의 캡처된 권한 부여 집합이 현재 컨텍스트의 모든 요구에 대해 먼저 평가됩니다.  다음에는 대리자 호출자의 모든 기존 보안 요구가 수행됩니다.  
  
## <a name="link-demands-and-wrappers"></a>링크 요구 및 래퍼  
 링크 요구를 포함하는 특수 보호 사례가 보안 인프라에서 강화되었지만 여전히 코드에서 보안 약점이 될 수 있습니다.  
  
 완전히 신뢰할 수 있는 코드가 [LinkDemand로](link-demands.md)보호되는 속성, 이벤트 또는 메서드를 호출하는 경우 호출에 대한 **LinkDemand** 권한 검사가 충족되면 호출이 성공합니다. 또한 완전히 신뢰할 수 있는 코드가 속성이름을 사용하고 리플렉션을 사용하여 **get** 접근자를 호출하는 클래스를 노출하는 경우 사용자 코드에 이 속성에 액세스할 권한이 없더라도 **get** 접근자호출이 성공합니다. **이는 LinkDemand가** 완전히 신뢰할 수 있는 코드인 즉각적인 호출자만 검사하기 때문입니다. 기본적으로 완전히 신뢰할 수 있는 코드는 사용자 코드에 해당 호출을 수행할 권한이 있는지 확인하지 않고 사용자 코드 대신 권한 있는 호출을 수행합니다.  
  
 이러한 보안 허점을 방지하기 위해 공통 언어 런타임은 **LinkDemand로**보호되는 메서드, 생성자, 속성 또는 이벤트에 대한 간접 호출에 대한 전체 스택 걷기 요구로 검사를 확장합니다. 이 보호를 사용할 경우 성능이 약간 저하되고 보안 검사의 의미 체계가 변경됩니다. 보다 신속한 단일 수준 검사는 성공했을 경우에도 전체 스택 워크 요구는 실패할 수 있습니다.  
  
## <a name="assembly-loading-wrappers"></a>어셈블리 로딩 래퍼  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>를 포함하여 관리 코드를 로드하는 데 사용되는 여러 메서드는 호출자의 증거와 함께 어셈블리를 로드합니다. 이러한 메서드를 래핑하는 경우 보안 시스템이 래퍼 호출자의 권한 대신 코드의 권한 부여를 사용하여 어셈블리를 로드할 수 있습니다. 덜 신뢰되는 코드가 래퍼 호출자의 권한보다 더 높은 권한이 부여된 코드를 로드할 수 있도록 허용하면 안 됩니다.  
  
 완전 신뢰 또는 잠재적인 호출자(인터넷 권한 수준 호출자 포함)보다 더 높은 신뢰 수준의 코드는 이런 방식으로 보안을 약화시킬 수 있습니다. 코드에 바이트 배열을 가져와 **어셈블리.Load에**전달하는 공용 메서드가 있는 경우 호출자 대신 어셈블리를 만들면 보안이 깨질 수 있습니다.  
  
 이 문제는 다음과 같은 API 요소에 적용됩니다.  
  
- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
## <a name="demand-vs-linkdemand"></a>Demand와 LinkDemand 비교  
 선언적 보안은 서로 비슷하지만 전혀 다른 검사를 수행하는 두 종류의 보안 검사를 제공합니다. 잘못 선택하면 보안이 약화되거나 성능이 저하될 수 있으므로 두 형태를 모두 이해해야 합니다.  
  
 선언적 보안은 다음과 같은 보안 검사를 제공합니다.  
  
- <xref:System.Security.Permissions.SecurityAction.Demand>는 코드 액세스 보안 스택 워크를 지정합니다. 성공하려면 스택의 모든 호출자에게 지정된 권한이나 ID가 있어야 합니다. 스택에 다른 호출이 포함될 수 있으므로 모든 호출에서 **요구가** 발생합니다. 메서드를 반복해서 호출하는 경우 이 보안 검사는 매번 발생합니다. **수요는** 유인 공격에 대한 좋은 보호입니다. 이를 통과하려는 무단 코드가 감지됩니다.  
  
- [LinkDemand는](link-demands.md) JIT(적시에) 컴파일 시간에 발생하며 즉시 호출자만 확인합니다. 이 보안 검사는 호출자의 호출자를 검사하지 않습니다. 이 검사가 성공하고 나면 호출자가 호출할 수 있는 횟수에 관계없이 추가 보안 오버헤드가 없습니다. 그러나 유인 공격으로부터 보호되지 않습니다. **LinkDemand를**사용하면 테스트를 통과하고 코드를 참조할 수 있는 모든 코드가 악의적인 코드가 인증된 코드를 사용하여 호출하도록 허용하여 보안을 깨뜨릴 수 있습니다. 따라서 가능한 모든 약점을 철저히 피할 수 있는 경우가 아니면 **LinkDemand를** 사용하지 마십시오.  
  
    > [!NOTE]
    > .NET Framework 4에서 링크 요청은 <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecurityRuleSet.Level2> 어셈블리의 특성으로 대체되었습니다. 이는 <xref:System.Security.SecurityCriticalAttribute> 완전 신뢰에 대한 링크 요구와 동일합니다. 그러나 상속 규칙에도 영향을 줍니다. 이 변경에 대한 자세한 내용은 [보안 투명 코드, 수준 2를](security-transparent-code-level-2.md)참조하십시오.  
  
 **LinkDemand를** 사용할 때 필요한 추가 예방 조치는 개별적으로 프로그래밍해야 합니다. 보안 시스템이 시행에 도움이 될 수 있습니다. 실수는 보안 약점이 됩니다. 사용자 코드를 사용하는 모든 권한 있는 코드는 다음을 수행하여 추가 보안을 구현해야 합니다.  
  
- 클래스 또는 어셈블리에 대한 호출 코드의 액세스 권한 제한.  
  
- 호출되는 코드에 표시되는 것과 동일한 보안 검사를 호출 코드에 배치하고 호출자도 이렇게 하도록 강제. 예를 들어 플래그가 지정된 **경우 LinkDemand로** <xref:System.Security.Permissions.SecurityPermission> <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 보호되는 메서드를 호출하는 코드를 작성하는 경우 메서드는 이 권한에 대해 **LinkDemand(또는** 더 강력한 **요청)를**만들어야 합니다. 코드에서 다른 보안 보호 메커니즘(예: 요구)이 주어지면 코드에서 안전하다고 판단하는 제한된 방식으로 **LinkDemand-protected**메서드를 사용하는 경우는 예외입니다. 이 예외적인 경우에서는 내부 코드의 보안 보호 약화에 대한 책임이 호출자에게 있습니다.  
  
- 코드의 호출자가 사용자 코드에서 보호된 코드를 대신 호출하도록 속일 수 없는지 확인. 즉, 호출자는 권한 있는 코드에서 특정 매개 변수를 보호된 코드로 전달하거나 보호된 코드에서 결과를 가져오도록 강제할 수 없습니다.  
  
### <a name="interfaces-and-link-demands"></a>인터페이스 및 링크 요구  
 **LinkDemand를** 사용하는 가상 메서드, 속성 또는 이벤트가 기본 클래스 메서드를 재사용하는 경우 기본 클래스 메서드는 재정의된 메서드에 대해 동일한 **LinkDemand를** 가져야 만 효과적입니다. 악성 코드가 기본 형식으로 다시 캐스팅되어 기본 클래스 메서드를 호출할 수 있습니다. 또한 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 어셈블리 수준 특성이 없는 어셈블리에 링크 요구를 암시적으로 추가할 수 있습니다.  
  
 인터페이스 메서드에도 링크 요구가 있는 경우 링크 요구로 메서드 구현을 보호하는 것이 좋습니다. 인터페이스와 함께 링크 요구를 사용하는 경우에 대한 다음 사항을 확인하세요.  
  
- 인터페이스 메서드를 구현하는 클래스의 공용 메서드에 **LinkDemand를** 배치하면 인터페이스에 캐스팅하고 메서드를 호출하면 **LinkDemand가** 적용되지 않습니다. 이 경우 인터페이스에 대해 연결했기 때문에 인터페이스의 **LinkDemand만** 적용됩니다.  
  
 보안 문제에 대한 다음 항목을 검토합니다.  
  
- 인터페이스 메서드의 명시적 링크 요구 이러한 링크 요구가 필요한 보호를 제공하는지 확인합니다. 앞에서 설명한 대로 악성 코드가 캐스트를 사용하여 링크 요구를 해결할 수 있는지 여부를 확인합니다.  
  
- 링크 요구가 적용된 가상 메서드  
  
- 가상 메서드가 구현하는 형식 및 인터페이스 링크 요구를 일관되게 사용해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [보안 코딩 지침](../../standard/security/secure-coding-guidelines.md)
