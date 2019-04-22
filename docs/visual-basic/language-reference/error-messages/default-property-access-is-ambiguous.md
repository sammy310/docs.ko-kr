---
title: 기본 속성 액세스가 '<defaultpropertyname>' 인터페이스의 상속된 인터페이스 멤버 '<interfacename1>'과(와) '<defaultpropertyname>' 인터페이스의 상속된 인터페이스 멤버 '<interfacename2>' 사이에서 모호합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5f058c8e7d480b9145452ae85f186a6ac2ed0d56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836352"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="af92c-102">기본 속성 액세스가 상속 된 인터페이스 멤버 사이 모호\<defaultpropertyname >' 인터페이스의 '\<interfacename1 >' 및 '\<defaultpropertyname >' 인터페이스의 '\< interfacename2 >'</span><span class="sxs-lookup"><span data-stu-id="af92c-102">Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>
<span data-ttu-id="af92c-103">인터페이스는 각각 같은 이름의 기본 속성을 선언 하는 두 인터페이스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="af92c-104">컴파일러는 한정자 없이이 기본 속성에 대 한 액세스를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="af92c-105">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="af92c-106">지정 하는 경우 `testObj(1)`, 컴파일러에서 기본 속성을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="af92c-107">그러나 두 가지 가능한 기본 속성 상속 된 인터페이스 때문 하므로 컴파일러가이 오류를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="af92c-108">**오류 ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="af92c-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="af92c-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="af92c-109">To correct this error</span></span>  
  
-   <span data-ttu-id="af92c-110">동일한 이름 가진 모든 멤버를 상속 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="af92c-111">앞의 예제에서 경우 `testObj` 의 멤버는 필요 하지 않습니다 예를 들어, `Iface2`를 다음과 같이 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="af92c-112">또는</span><span class="sxs-lookup"><span data-stu-id="af92c-112">-or-</span></span>  
  
-   <span data-ttu-id="af92c-113">클래스에서 상속 하는 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="af92c-114">그런 다음 각 다른 이름의 상속 된 속성을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="af92c-115">그러나 그 중 하나만 구현 하는 클래스의 기본 속성을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="af92c-116">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="af92c-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="af92c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="af92c-117">See also</span></span>

- [<span data-ttu-id="af92c-118">인터페이스</span><span class="sxs-lookup"><span data-stu-id="af92c-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
