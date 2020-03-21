---
title: 링크 요구 사항
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
ms.openlocfilehash: a0466eb5c24840c77a3b191f9b0e001f6b267fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181166"
---
# <a name="link-demands"></a>링크 요구 사항
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 링크 요청으로 인해 Just-In-Time 컴파일 동안 보안 검사를 수행하며 코드의 직접 호출 어셈블리만 검사합니다. 연결은 함수 포인터 참조 및 메서드 호출을 포함하여 코드가 형식 참조에 바인딩된 경우에 발생합니다. 호출 어셈블리에 코드에 연결할 권한이 없는 경우 링크가 허용되지 않으며 코드가 로드 및 실행될 때 런타임 예외가 발생합니다. 코드에서 상속하는 클래스에서 링크 요청을 재정의할 수 있습니다.  
  
 이 형식의 요청에서는 전체 스택 워크가 수행되지 않으며 코드가 여전히 보안 공격에 취약합니다. 예를 들어 어셈블리 A의 메서드가 링크 요구에 의해 보호되는 경우 어셈블리 B의 직접 호출자는 어셈블리 B의 사용 권한에 따라 평가됩니다.  그러나 링크 요구는 어셈블리 B에서 메서드를 사용하여 어셈블리 A에서 메서드를 간접적으로 호출하는 경우 어셈블리 C에서 메서드를 평가하지 않습니다. 링크 요청은 코드에 연결해야 하는 즉각적인 호출 어셈블리의 직접 호출자에게만 권한을 지정합니다. 모든 호출자가 코드를 실행하는 데 필요한 권한은 지정하지 않습니다.  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> 및 <xref:System.Security.CodeAccessPermission.PermitOnly%2A> 스택 워크 한정자는 링크 요청의 평가에 영향을 주지 않습니다.  링크 요청은 스택 워크를 수행하지 않으므로 스택 워크 한정자가 링크 요청에 영향을 주지 않습니다.  
  
 링크 요청으로 보호되는 메서드가 [리플렉션을](../reflection-and-codedom/reflection.md)통해 액세스되는 경우 링크 요청은 리플렉션을 통해 액세스된 코드의 즉각적인 호출을 확인합니다. 이는 리플렉션을 사용하여 수행된 메서드 호출 및 메서드 검색 둘 다에 적용됩니다. 예를 들어, 코드가 리플렉션을 사용하여 링크 요청으로 보호되는 메서드를 나타내는 개체를 반환한 <xref:System.Reflection.MethodInfo> 다음 **MethodInfo** 개체를 원래 메서드를 호출하는 다른 코드로 전달한다고 가정합니다. 이 경우 링크 요청 검사는 MethodInfo 개체를 반환하는 코드에 대해 한 번, **호출하는** 코드에 대해 한 번 두 번 발생합니다.  
  
> [!NOTE]
> 정적 생성자는 애플리케이션 코드 실행 경로 외부의 시스템에서 호출되므로 정적 클래스 생성자에서 수행되는 링크 요청은 생성자를 보호하지 않습니다. 따라서 링크 요청이 전체 클래스에 적용되는 경우 클래스의 나머지 부분은 보호하지만 정적 생성자에 대한 액세스를 보호할 수 없습니다.  
  
 다음 코드 조각에서는 `ReadData` 메서드에 연결하는 코드에 `CustomPermission` 권한이 있어야 함을 선언적으로 지정합니다. 이 권한은 가상의 사용자 지정 권한이며 .NET Framework에 존재하지 않습니다. 보안 **액션.LinkDemand** 플래그를 `CustomPermissionAttribute`에 전달하여 요구가 이루어집니다.  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a>참고 항목

- [특성](../../standard/attributes/index.md)
- [코드 액세스 보안](code-access-security.md)
