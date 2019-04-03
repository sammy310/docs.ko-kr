---
title: "'<propertyname>' 속성의 'Set' 접근자에 액세스할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3bc50d6762998ca5d8f445d84c8b698c9f46436f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834467"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="42b3b-102">'Set' 접근자 속성의 '\<propertyname >'에 액세스할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="42b3b-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="42b3b-103">문에서 속성에 대 한 액세스 되지 않은 경우 속성의 값을 저장 하려고 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="42b3b-104">경우는 [Set 문을](../../../visual-basic/language-reference/statements/set-statement.md) 수준 보다 더 제한적인 액세스를 사용 하 여 표시 됩니다 해당 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md), 다음과 같은 경우 속성 값을 설정 하려는 시도가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="42b3b-105">합니다 `Set` 문이 표시 됩니다 [개인](../../../visual-basic/language-reference/modifiers/private.md) 호출 코드에서 클래스 또는 속성이 정의 된 구조체를 벗어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="42b3b-106">합니다 `Set` 문이 표시 됩니다 [보호 된](../../../visual-basic/language-reference/modifiers/protected.md) 클래스 또는 속성이 정의 되어 있는 구조에 없는 또는 파생된 클래스에서 호출 하는 코드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="42b3b-107">합니다 `Set` 문이 표시 됩니다 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 고 호출 코드에서 속성이 정의 된 동일한 어셈블리에 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="42b3b-108">**오류 ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="42b3b-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42b3b-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="42b3b-109">To correct this error</span></span>  
  
-   <span data-ttu-id="42b3b-110">속성을 정의 하는 소스 코드 제어에 있는 경우 선언을 살펴보십시오는 `Set` 해당 속성과 동일한 액세스 레벨을 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="42b3b-111">속성을 정의 하는 소스 코드 제어 없는 또는 제한 해야 하는 경우는 `Set` 프로시저 액세스 수준 속성 자체에 쉽게 액세스할 수 있는 코드의 영역으로 속성 값을 설정 하는 문을 이동 하려고 보다는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="42b3b-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b3b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="42b3b-112">See also</span></span>

- [<span data-ttu-id="42b3b-113">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="42b3b-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="42b3b-114">방법: 액세스 수준이 혼합된 된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="42b3b-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
