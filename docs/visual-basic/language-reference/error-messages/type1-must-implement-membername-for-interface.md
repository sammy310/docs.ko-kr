---
title: <type1>'<typename>'구현 해야 합니다'<membername>'interface'에 대 한<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 485680a2984a29037b2836fcba13cf1aa1e2e699
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822754"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="42821-102">\<type1 >'\<typename >'를 구현 해야 합니다 '\<membername >' 인터페이스에 대 한 '\<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="42821-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="42821-103">'\<typename >'를 구현 해야 합니다 '\<membername >' 인터페이스에 대 한 '\<interfacename >'입니다.</span><span class="sxs-lookup"><span data-stu-id="42821-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="42821-104">속성을 구현 일치 해야 합니다 'ReadOnly '/' WriteOnly' 지정 자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42821-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="42821-105">클래스 또는 구조체는 인터페이스를 구현 하지만 프로시저, 속성 또는 인터페이스에 의해 정의 된 이벤트를 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42821-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="42821-106">인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42821-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="42821-107">**오류 ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="42821-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42821-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="42821-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="42821-109">동일한 이름 및 서명을 인터페이스에 정의 된 멤버를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="42821-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="42821-110">포함 해야 적어도 `End Function`, `End Sub`, 또는 `End Property` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="42821-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="42821-111">추가 `Implements` 의 끝에 절을 `Function`, `Sub`, `Property`, 또는 `Event` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="42821-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="42821-112">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="42821-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="42821-113">속성을 구현할 때 했는지 `ReadOnly` 또는 `WriteOnly` 인터페이스 정의 처럼 동일한 방식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42821-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="42821-114">속성을 구현할 때 선언 `Get` 고 `Set` 프로시저를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="42821-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42821-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="42821-115">See also</span></span>

- [<span data-ttu-id="42821-116">Implements 문</span><span class="sxs-lookup"><span data-stu-id="42821-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="42821-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="42821-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
