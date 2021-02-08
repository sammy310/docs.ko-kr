---
description: '자세한 정보: BC30594: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.'
title: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f9e8bf6e0d365c4ee747deb6be0e809904d87117
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796420"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="d8964-103">BC30594: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8964-103">BC30594: Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>

<span data-ttu-id="d8964-104">한정자를 사용 하 여 선언 된 변수는 `Shared` 공유 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8964-104">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="d8964-105">공유 변수는 정확히 하나의 저장소 위치를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8964-105">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="d8964-106">한정자를 사용 하 여 선언 된 변수는 변수가 `WithEvents` 속한 형식이 변수가 발생 시키는 이벤트 집합을 처리 함을 어설션 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8964-106">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="d8964-107">변수에 값이 할당 되 면 선언으로 생성 된 속성이 `WithEvents` 기존 이벤트 처리기를 언 후크 하 고 메서드를 통해 새 이벤트 처리기를 후크합니다 `Add` .</span><span class="sxs-lookup"><span data-stu-id="d8964-107">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>

 <span data-ttu-id="d8964-108">**오류 ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="d8964-108">**Error ID:** BC30594</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d8964-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d8964-109">To correct this error</span></span>

- <span data-ttu-id="d8964-110">이벤트 처리기를 선언 `Shared` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8964-110">Declare your event handler `Shared`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8964-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8964-111">See also</span></span>

- [<span data-ttu-id="d8964-112">공유</span><span class="sxs-lookup"><span data-stu-id="d8964-112">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="d8964-113">WithEvents</span><span class="sxs-lookup"><span data-stu-id="d8964-113">WithEvents</span></span>](../modifiers/withevents.md)
