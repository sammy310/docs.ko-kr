---
description: '#endif - C# 참조'
title: '#endif - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168636"
---
# <a name="endif-c-reference"></a><span data-ttu-id="9f3d9-103">#endif(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9f3d9-103">#endif (C# Reference)</span></span>

<span data-ttu-id="9f3d9-104">`#endif`는 [#if](./preprocessor-if.md) 지시문으로 시작한 조건부 지시문의 끝을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3d9-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="9f3d9-105">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3d9-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="9f3d9-106">설명</span><span class="sxs-lookup"><span data-stu-id="9f3d9-106">Remarks</span></span>  

 <span data-ttu-id="9f3d9-107">`#if` 지시문으로 시작되는 조건부 지시문은 `#endif` 지시문을 사용하여 명시적으로 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3d9-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="9f3d9-108">`#endif`를 사용하는 방법에 대한 예제는 [#if](./preprocessor-if.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f3d9-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f3d9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f3d9-109">See also</span></span>

- [<span data-ttu-id="9f3d9-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9f3d9-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9f3d9-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9f3d9-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9f3d9-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="9f3d9-112">C# Preprocessor Directives</span></span>](./index.md)
