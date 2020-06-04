---
title: COM 클래스에서 파생된 관리되는 클래스는 런타임에 바인딩된 호출을 할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: 401cb5d7194cbef616c87d59e5b1ed7f923fe6f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402124"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="da8b3-102">COM 클래스에서 파생된 관리되는 클래스는 런타임에 바인딩된 호출을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da8b3-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="da8b3-103">COM 클래스에서 파생된 관리되는 클래스에 런타임에 바인딩된 호출을 하려고 했습니다. 이러한 호출은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da8b3-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="da8b3-104">문제를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="da8b3-104">To correct the problem</span></span>

<span data-ttu-id="da8b3-105">초기 바인딩된 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8b3-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="da8b3-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da8b3-106">See also</span></span>

- [<span data-ttu-id="da8b3-107">오류 유형</span><span class="sxs-lookup"><span data-stu-id="da8b3-107">Error Types</span></span>](../programming-guide/language-features/error-types.md)
