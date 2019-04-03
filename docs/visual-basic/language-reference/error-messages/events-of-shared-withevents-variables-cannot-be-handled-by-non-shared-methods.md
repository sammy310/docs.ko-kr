---
title: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 2b32043898986b3e3e68fab18c5f907843d7691c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838653"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="b1e6a-102">비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="b1e6a-103">사용 하 여 선언 된 변수는 `Shared` 한정자는 공유 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="b1e6a-104">공유 변수는 정확히 하나의 저장 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="b1e6a-105">사용 하 여 선언 된 변수는 `WithEvents` 한정자 변수의 속한 형식에서 변수의 발생 하는 이벤트 집합을 처리 하는 어설션 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="b1e6a-106">속성에서 만든 값이 변수에 할당 되는 경우는 `WithEvents` 선언 기존 이벤트 처리기를 언 후크합니다를 통해 새 이벤트 처리기는 `Add` 메서드.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="b1e6a-107">**오류 ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="b1e6a-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1e6a-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b1e6a-108">To correct this error</span></span>  
  
-   <span data-ttu-id="b1e6a-109">이벤트 처리기를 선언 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e6a-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e6a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1e6a-110">See also</span></span>

- [<span data-ttu-id="b1e6a-111">공유</span><span class="sxs-lookup"><span data-stu-id="b1e6a-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="b1e6a-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="b1e6a-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
