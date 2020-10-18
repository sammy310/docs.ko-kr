---
title: 속성 또는 메서드 호출에 인수 또는 반환 값으로서 private 개체에 대한 참조를 포함할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 00237d795fb62fbae426e0015d8e64d5fabb4c32
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162676"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="af74c-102">속성 또는 메서드 호출에 인수 또는 반환 값으로서 private 개체에 대한 참조를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af74c-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>

<span data-ttu-id="af74c-103">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="af74c-103">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="af74c-104">클라이언트가 Out of Process 구성 요소의 속성 또는 메서드를 호출했으며 private 개체에 대한 참조를 인수 중 하나로 전달하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af74c-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>

- <span data-ttu-id="af74c-105">Out of Process 구성 요소가 해당 클라이언트에 대해 콜백 메서드를 호출했으며 private 개체에 대한 참조를 전달하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af74c-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>

- <span data-ttu-id="af74c-106">Out of Process 구성 요소가 private 개체에 대한 참조를 발생 이벤트의 인수로 전달하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af74c-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>

- <span data-ttu-id="af74c-107">클라이언트가 처리 중인 이벤트의 `ByRef` 인수에 private 개체 참조를 할당하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af74c-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="af74c-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="af74c-108">To correct this error</span></span>

- <span data-ttu-id="af74c-109">참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="af74c-109">Remove the reference.</span></span>

## <a name="see-also"></a><span data-ttu-id="af74c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af74c-110">See also</span></span>

- [<span data-ttu-id="af74c-111">개인</span><span class="sxs-lookup"><span data-stu-id="af74c-111">Private</span></span>](../modifiers/private.md)
