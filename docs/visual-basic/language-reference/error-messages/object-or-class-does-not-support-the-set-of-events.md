---
description: '자세한 정보: 개체 또는 클래스가 이벤트 집합을 지원 하지 않습니다.'
title: 개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: f13d47a6bb75a5e8394f5344b954afa523bedab3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795602"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="33d3b-103">개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33d3b-103">Object or class does not support the set of events</span></span>

<span data-ttu-id="33d3b-104">`WithEvents`지정 된 이벤트 집합에 대 한 이벤트 소스로 작동할 수 없는 구성 요소에서 변수를 사용 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="33d3b-104">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="33d3b-105">예를 들어 개체의 이벤트를 싱크 한 다음 `Implements` 첫 번째 개체에 해당 하는 다른 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d3b-105">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="33d3b-106">구현 된 개체에서 이벤트를 싱크할 수도 있지만이 경우에는 항상 그렇지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33d3b-106">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="33d3b-107">`Implements` 는 메서드 및 속성에 대 한 인터페이스만 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="33d3b-107">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="33d3b-108">`WithEvents` 는를 발생 시키는 데 `UserControls` 필요한 형식 정보를 런타임에 사용할 수 없으므로 private에 대해 지원 되지 않습니다 `ObjectEvent` .</span><span class="sxs-lookup"><span data-stu-id="33d3b-108">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="33d3b-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="33d3b-109">To correct this error</span></span>

- <span data-ttu-id="33d3b-110">이벤트를 소스 하지 않는 구성 요소에 대 한 이벤트를 싱크할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33d3b-110">You cannot sink events for a component that does not source events.</span></span>

## <a name="see-also"></a><span data-ttu-id="33d3b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33d3b-111">See also</span></span>

- [<span data-ttu-id="33d3b-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="33d3b-112">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="33d3b-113">Implements 문</span><span class="sxs-lookup"><span data-stu-id="33d3b-113">Implements Statement</span></span>](../statements/implements-statement.md)
