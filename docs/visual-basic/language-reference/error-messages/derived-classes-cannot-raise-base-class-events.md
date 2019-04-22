---
title: 파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0e9acf4b3e71295655c15ae9b1c80852c9aca8df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835143"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="c8e79-102">파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e79-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="c8e79-103">이벤트 선언 되는 선언 공간 에서만에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e79-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="c8e79-104">따라서 클래스 다른 클래스와 파생 된 하나에서 이벤트를 발생 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e79-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="c8e79-105">**오류 ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="c8e79-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8e79-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c8e79-106">To correct this error</span></span>  
  
-   <span data-ttu-id="c8e79-107">이동 합니다 `Event` 문 또는 `RaiseEvent` 문을 동일한 클래스에서.</span><span class="sxs-lookup"><span data-stu-id="c8e79-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e79-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8e79-108">See also</span></span>

- [<span data-ttu-id="c8e79-109">Event 문</span><span class="sxs-lookup"><span data-stu-id="c8e79-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c8e79-110">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="c8e79-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
