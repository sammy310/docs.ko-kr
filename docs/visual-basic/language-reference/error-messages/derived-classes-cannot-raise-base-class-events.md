---
title: 파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874491"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="a6b33-102">파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b33-102">Derived classes cannot raise base class events</span></span>

<span data-ttu-id="a6b33-103">이벤트는 선언 된 선언 공간 에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b33-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="a6b33-104">따라서 클래스는 파생 된 클래스를 비롯 하 여 다른 클래스에서 이벤트를 발생 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b33-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="a6b33-105">**오류 ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="a6b33-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6b33-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a6b33-106">To correct this error</span></span>  
  
- <span data-ttu-id="a6b33-107">`Event`문이나 `RaiseEvent` 문이 동일한 클래스에 있도록 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b33-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b33-108">참조</span><span class="sxs-lookup"><span data-stu-id="a6b33-108">See also</span></span>

- [<span data-ttu-id="a6b33-109">Event 문</span><span class="sxs-lookup"><span data-stu-id="a6b33-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="a6b33-110">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="a6b33-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
