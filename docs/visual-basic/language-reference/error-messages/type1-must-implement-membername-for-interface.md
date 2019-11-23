---
title: <type1>'<typename>'은 '<membername>' 인터페이스에 대한 '<interfacename>'을 구현해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696888"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="68f11-102">\<type1 > '\<typename > '은 (는) '\<interfacename > ' 인터페이스에 대해 '\<membername > '를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="68f11-103">'\<typename > '은 (는) '\<interfacename > ' 인터페이스에 대해 '\<membername > '을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="68f11-104">구현 속성에 일치 하는 ' ReadOnly '/' WriteOnly ' 지정 자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="68f11-105">클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저, 속성 또는 이벤트를 구현 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="68f11-106">인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="68f11-107">**오류 ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="68f11-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="68f11-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="68f11-108">To correct this error</span></span>  
  
1. <span data-ttu-id="68f11-109">인터페이스에 정의 된 것과 동일한 이름 및 서명을 사용 하 여 멤버를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="68f11-110">적어도 `End Function`, `End Sub`또는 `End Property` 문을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="68f11-111">`Function`, `Sub`, `Property`또는 `Event` 문의 끝에 `Implements` 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="68f11-112">예:</span><span class="sxs-lookup"><span data-stu-id="68f11-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="68f11-113">속성을 구현 하는 경우 인터페이스 정의에서와 동일한 방식으로 `ReadOnly` 또는 `WriteOnly` 사용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="68f11-114">속성을 구현 하는 경우 `Get` 및 `Set` 프로시저를 적절 하 게 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f11-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f11-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68f11-115">See also</span></span>

- [<span data-ttu-id="68f11-116">Implements 문</span><span class="sxs-lookup"><span data-stu-id="68f11-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="68f11-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="68f11-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
