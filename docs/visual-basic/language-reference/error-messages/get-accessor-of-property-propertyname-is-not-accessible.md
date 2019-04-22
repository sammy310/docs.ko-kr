---
title: "'<propertyname>' 속성의 'Get' 접근자에 액세스할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 8fb78f3c14708c79f1910e202287c25a3b2213b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814408"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="ce49f-102">'Get' 접근자 속성의 '\<propertyname >'에 액세스할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="ce49f-102">'Get' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="ce49f-103">문에서 속성에 대 한 액세스 되지 않은 경우 속성의 값을 검색 하려고 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="ce49f-104">경우는 [Get 문은](../../../visual-basic/language-reference/statements/get-statement.md) 수준 보다 더 제한적인 액세스를 사용 하 여 표시 됩니다 해당 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)를 속성 값을 읽으려는 시도가 다음 경우에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="ce49f-105">합니다 `Get` 문이 표시 됩니다 [개인](../../../visual-basic/language-reference/modifiers/private.md) 호출 코드에서 클래스 또는 속성이 정의 된 구조체를 벗어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="ce49f-106">합니다 `Get` 문이 표시 됩니다 [보호 된](../../../visual-basic/language-reference/modifiers/protected.md) 클래스 또는 속성이 정의 되어 있는 구조에 없는 또는 파생된 클래스에서 호출 하는 코드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="ce49f-107">합니다 `Get` 문이 표시 됩니다 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 고 호출 코드에서 속성이 정의 된 동일한 어셈블리에 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="ce49f-108">**오류 ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="ce49f-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce49f-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ce49f-109">To correct this error</span></span>  
  
-   <span data-ttu-id="ce49f-110">속성을 정의 하는 소스 코드 제어에 있는 경우 선언을 살펴보십시오는 `Get` 해당 속성과 동일한 액세스 레벨을 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="ce49f-111">속성을 정의 하는 소스 코드 제어 없는 또는 제한 해야 하는 경우는 `Get` 프로시저 액세스 수준 속성 자체가 속성 값에 쉽게 액세스할 수 있는 코드 영역을 읽는 문을 이동 하려고 보다는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ce49f-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce49f-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce49f-112">See also</span></span>

- [<span data-ttu-id="ce49f-113">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="ce49f-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="ce49f-114">방법: 액세스 수준이 혼합된 된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="ce49f-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
