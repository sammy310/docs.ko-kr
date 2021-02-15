---
description: '자세히 알아보기: COM 클래스에서 파생 된 관리 되는 클래스는 런타임에 바인딩된 호출을 할 수 없습니다.'
title: COM 클래스에서 파생된 관리되는 클래스는 런타임에 바인딩된 호출을 할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: bde124c3e5c52d4c0dbb0e6e1f7250574c83be8d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430042"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="0731e-103">COM 클래스에서 파생된 관리되는 클래스는 런타임에 바인딩된 호출을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0731e-103">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="0731e-104">COM 클래스에서 파생된 관리되는 클래스에 런타임에 바인딩된 호출을 하려고 했습니다. 이러한 호출은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0731e-104">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="0731e-105">문제를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0731e-105">To correct the problem</span></span>

<span data-ttu-id="0731e-106">초기 바인딩된 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0731e-106">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="0731e-107">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0731e-107">See also</span></span>

- [<span data-ttu-id="0731e-108">오류 유형</span><span class="sxs-lookup"><span data-stu-id="0731e-108">Error Types</span></span>](../programming-guide/language-features/error-types.md)
