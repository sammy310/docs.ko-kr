---
title: 링크 요청
description: JIT (just-in-time) 컴파일을 수행 하는 동안 보안 검사를 수행 하 고 코드의 즉시 호출 어셈블리만 검사 하는 링크 요청에 대해 알아보세요.
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
ms.openlocfilehash: eaf9ee1bb5cd10c724240bacac014503685a0c8c
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309107"
---
# <a name="link-demands"></a><span data-ttu-id="5ced8-103">링크 요청</span><span class="sxs-lookup"><span data-stu-id="5ced8-103">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="5ced8-104">링크 요청으로 인해 Just-In-Time 컴파일 동안 보안 검사를 수행하며 코드의 직접 호출 어셈블리만 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-104">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="5ced8-105">연결은 함수 포인터 참조 및 메서드 호출을 포함하여 코드가 형식 참조에 바인딩된 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-105">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="5ced8-106">호출 어셈블리에 코드에 연결할 권한이 없는 경우 링크가 허용되지 않으며 코드가 로드 및 실행될 때 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-106">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="5ced8-107">코드에서 상속하는 클래스에서 링크 요청을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-107">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="5ced8-108">전체 스택 워크는 이러한 유형의 요청으로 수행 되지 않으며 코드에서 여전히 잠복 공격에 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-108">A full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="5ced8-109">예를 들어 어셈블리 A의 메서드가 링크 요청에 의해 보호 되 면 어셈블리 b의 직접 호출자는 어셈블리 B의 권한에 따라 평가 됩니다.  그러나 어셈블리 B의 메서드를 사용 하 여 어셈블리 A에서 메서드를 간접적으로 호출 하는 경우 링크 요청은 어셈블리 C의 메서드를 평가 하지 않습니다. 링크 요청은 직접 호출 어셈블리의 직접 호출자가 코드에 연결 하는 데 필요한 권한만 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-109">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="5ced8-110">모든 호출자가 코드를 실행하는 데 필요한 권한은 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-110">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="5ced8-111"><xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> 및 <xref:System.Security.CodeAccessPermission.PermitOnly%2A> 스택 워크 한정자는 링크 요청의 평가에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-111">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="5ced8-112">링크 요청은 스택 워크를 수행하지 않으므로 스택 워크 한정자가 링크 요청에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-112">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="5ced8-113">[리플렉션을](../reflection-and-codedom/reflection.md)통해 링크 요청에 의해 보호 되는 메서드에 액세스 한 경우 링크 요청은 리플렉션을 통해 액세스 되는 코드의 직접 실행 호출자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-113">If a method protected by a link demand is accessed through [Reflection](../reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="5ced8-114">이는 리플렉션을 사용하여 수행된 메서드 호출 및 메서드 검색 둘 다에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-114">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="5ced8-115">예를 들어 코드에서 리플렉션을 사용 하 여 <xref:System.Reflection.MethodInfo> 링크 요청으로 보호 되는 메서드를 나타내는 개체를 반환한 다음 개체를 사용 하 여 원래 메서드를 호출 하는 다른 코드에 **MethodInfo** 개체를 전달 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-115">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="5ced8-116">이 경우 링크 요청 검사는 **MethodInfo** 개체를 반환 하는 코드에 대해 한 번, 그리고 호출 하는 코드의 경우 한 번 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-116">In this case, the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ced8-117">정적 생성자는 애플리케이션 코드 실행 경로 외부의 시스템에서 호출되므로 정적 클래스 생성자에서 수행되는 링크 요청은 생성자를 보호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-117">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="5ced8-118">따라서 링크 요청이 전체 클래스에 적용되는 경우 클래스의 나머지 부분은 보호하지만 정적 생성자에 대한 액세스를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-118">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="5ced8-119">다음 코드 조각에서는 `ReadData` 메서드에 연결하는 코드에 `CustomPermission` 권한이 있어야 함을 선언적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-119">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="5ced8-120">이 권한은 가상의 사용자 지정 권한이며 .NET Framework에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ced8-120">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="5ced8-121">요청은 **SecurityAction** 플래그를에 전달 하 여 수행 됩니다 `CustomPermissionAttribute` .</span><span class="sxs-lookup"><span data-stu-id="5ced8-121">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ced8-122">참조</span><span class="sxs-lookup"><span data-stu-id="5ced8-122">See also</span></span>

- [<span data-ttu-id="5ced8-123">특성</span><span class="sxs-lookup"><span data-stu-id="5ced8-123">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="5ced8-124">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="5ced8-124">Code Access Security</span></span>](code-access-security.md)
