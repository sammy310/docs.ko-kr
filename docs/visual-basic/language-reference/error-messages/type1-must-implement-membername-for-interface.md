---
title: <type1>'<typename>'은 '<interfacename>' 인터페이스에 대한 '<membername>'을 구현해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 7b74ee3a05000f5d6cd94176b48dea116b647a2a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872172"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="f6db8-102">\<type1>'\<typename>'은 '\<interfacename>' 인터페이스에 대한 '\<membername>'을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="f6db8-103">' ' \<typename> 은 ' ' \<membername> 인터페이스에 대해 ' '을 (를) 구현 해야 합니다 \<interfacename> .</span><span class="sxs-lookup"><span data-stu-id="f6db8-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="f6db8-104">구현 속성에 일치 하는 ' ReadOnly '/' WriteOnly ' 지정 자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="f6db8-105">클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저, 속성 또는 이벤트를 구현 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="f6db8-106">인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="f6db8-107">**오류 ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="f6db8-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6db8-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f6db8-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f6db8-109">인터페이스에 정의 된 것과 동일한 이름 및 서명을 사용 하 여 멤버를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="f6db8-110">적어도, `End Function` `End Sub` 또는 문을 포함 해야 `End Property` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="f6db8-111">,, `Implements` 또는 문의 끝에 절을 `Function` 추가 `Sub` `Property` `Event` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="f6db8-112">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="f6db8-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="f6db8-113">속성을 구현할 때 `ReadOnly` 또는 `WriteOnly` 가 인터페이스 정의에서와 동일한 방식으로 사용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="f6db8-114">속성을 구현 하는 경우 `Get` 및 `Set` 프로시저를 적절 하 게 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6db8-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6db8-115">참조</span><span class="sxs-lookup"><span data-stu-id="f6db8-115">See also</span></span>

- [<span data-ttu-id="f6db8-116">Implements 문</span><span class="sxs-lookup"><span data-stu-id="f6db8-116">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="f6db8-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6db8-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
