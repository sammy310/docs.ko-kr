---
title: 파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 030c9c2ffa97572298b23f05c23e3af0df7387b0
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913169"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="80e15-102">파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80e15-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="80e15-103">이벤트 선언 되는 선언 공간 에서만에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80e15-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="80e15-104">따라서 클래스 다른 클래스와 파생 된 하나에서 이벤트를 발생 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80e15-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="80e15-105">**오류 ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="80e15-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80e15-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="80e15-106">To correct this error</span></span>  
  
- <span data-ttu-id="80e15-107">이동 합니다 `Event` 문 또는 `RaiseEvent` 문을 동일한 클래스에서.</span><span class="sxs-lookup"><span data-stu-id="80e15-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e15-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="80e15-108">See also</span></span>

- [<span data-ttu-id="80e15-109">Event 문</span><span class="sxs-lookup"><span data-stu-id="80e15-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="80e15-110">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="80e15-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
