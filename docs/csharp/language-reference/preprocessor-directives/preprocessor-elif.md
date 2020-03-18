---
title: '#elif - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: c78818f40b76414d289af6c704ff019b63befe37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712574"
---
# <a name="elif-c-reference"></a><span data-ttu-id="e7894-102">#elif(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e7894-102">#elif (C# Reference)</span></span>
<span data-ttu-id="e7894-103">`#elif`를 사용하면 복합 조건부 지시문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="e7894-104">`#elif` 식이 계산되는 경우는 [#if](./preprocessor-if.md)와 앞의 선택적 `#elif` 지시문 식이 모두 `true`로 계산되지 않는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="e7894-105">`#elif` 식이 `true`이면 컴파일러는 `#elif`와 다음 조건부 지시문 사이에 있는 모든 코드를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="e7894-106">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="e7894-107">`==`(같음), `!=`(같지 않음), `&&`(AND), `||`(OR) 연산자를 사용하여 여러 기호를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="e7894-108">기호와 연산자를 괄호로 묶을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7894-109">설명</span><span class="sxs-lookup"><span data-stu-id="e7894-109">Remarks</span></span>  
 <span data-ttu-id="e7894-110">`#elif`는 다음 코드를 사용하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="e7894-111">`#elif`를 사용하는 것이 더 간단합니다. 각 `#if`에는 [#endif](./preprocessor-endif.md)가 필요한 반면, `#elif`는 짝이 되는 `#endif` 없이 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e7894-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="e7894-112">[를 사용하는 방법에 대한 예제는 ](./preprocessor-if.md)#if`#elif`를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7894-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7894-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7894-113">See also</span></span>

- [<span data-ttu-id="e7894-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e7894-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e7894-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e7894-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e7894-116">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="e7894-116">C# Preprocessor Directives</span></span>](./index.md)
