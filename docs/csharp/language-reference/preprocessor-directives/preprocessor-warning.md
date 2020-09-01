---
description: '#warning - C# 참조'
title: '#warning - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: ab2cc5120492fc2a4b94296eb85e563c0a1d5ad3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137840"
---
# <a name="warning-c-reference"></a><span data-ttu-id="da463-103">#warning(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="da463-103">#warning (C# Reference)</span></span>
<span data-ttu-id="da463-104">`#warning`을 사용하면 코드의 특정 위치에서 [CS1030](../../misc/cs1030.md) 수준 1 컴파일러 경고를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da463-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="da463-105">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="da463-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="da463-106">설명</span><span class="sxs-lookup"><span data-stu-id="da463-106">Remarks</span></span>
 <span data-ttu-id="da463-107">`#warning`는 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da463-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="da463-108">[#error](./preprocessor-error.md)를 사용하여 사용자 정의 오류를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da463-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da463-109">예제</span><span class="sxs-lookup"><span data-stu-id="da463-109">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="da463-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da463-110">See also</span></span>

- [<span data-ttu-id="da463-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="da463-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="da463-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="da463-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="da463-113">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="da463-113">C# Preprocessor Directives</span></span>](./index.md)
