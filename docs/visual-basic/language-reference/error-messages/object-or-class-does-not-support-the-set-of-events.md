---
title: 개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342884"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="e5dc6-102">개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dc6-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="e5dc6-103">사용 하려는 `WithEvents` 지정한 이벤트 집합에 대 한 이벤트 원본으로 작동할 수 없습니다. 구성 요소를 사용 하 여 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5dc6-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="e5dc6-104">예를 들어, 하려는 개체의 이벤트를 다른 개체를 만들 `Implements` 첫 번째 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e5dc6-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="e5dc6-105">구현 된 개체에서 이벤트를 싱크할 수 생각 하지만이 아닌 경우 항상 대/소문자</span><span class="sxs-lookup"><span data-stu-id="e5dc6-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="e5dc6-106">`Implements` 메서드 및 속성에 대 한 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dc6-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="e5dc6-107">`WithEvents` 개인에 대 한 지원 되지 않습니다 `UserControls`이므로 발생 시키는 데 필요한 형식 정보를 `ObjectEvent` 런타임에 사용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dc6-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5dc6-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e5dc6-108">To correct this error</span></span>  
  
1. <span data-ttu-id="e5dc6-109">이벤트 소스가 아닌 하는 구성 요소에 대 한 이벤트를 싱크할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dc6-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5dc6-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e5dc6-110">See also</span></span>

- [<span data-ttu-id="e5dc6-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="e5dc6-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="e5dc6-112">Implements 문</span><span class="sxs-lookup"><span data-stu-id="e5dc6-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
