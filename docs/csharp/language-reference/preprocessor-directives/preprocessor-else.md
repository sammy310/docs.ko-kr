---
description: '#else - C# 참조'
title: '#else - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168675"
---
# <a name="else-c-reference"></a><span data-ttu-id="12d9c-103">#else(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="12d9c-103">#else (C# Reference)</span></span>

<span data-ttu-id="12d9c-104">`#else`를 사용하면 복합 조건부 지시문을 만들 수 있습니다. 이 경우 앞의 [#if](./preprocessor-if.md) 또는 (선택 사항)[#elif](./preprocessor-elif.md) 지시문에 `true`로 평가하는 식이 없으면 컴파일러는 `#else`와 후속 `#endif` 사이에 있는 모든 코드를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="12d9c-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12d9c-105">설명</span><span class="sxs-lookup"><span data-stu-id="12d9c-105">Remarks</span></span>  

 <span data-ttu-id="12d9c-106">[#endif](./preprocessor-endif.md)는 `#else` 이후의 다음 전처리기 지시문이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d9c-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="12d9c-107">`#else`를 사용하는 방법에 대한 예제는 [#if](./preprocessor-if.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12d9c-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d9c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12d9c-108">See also</span></span>

- [<span data-ttu-id="12d9c-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="12d9c-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="12d9c-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="12d9c-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="12d9c-111">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="12d9c-111">C# Preprocessor Directives</span></span>](./index.md)
