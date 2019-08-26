---
title: '#warning - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 3d09cd95ef4d53e3f11d9feb9675ebba22d6f857
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608517"
---
# <a name="warning-c-reference"></a><span data-ttu-id="84dc8-102">#warning(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="84dc8-102">#warning (C# Reference)</span></span>
<span data-ttu-id="84dc8-103">`#warning`을 사용하면 코드의 특정 위치에서 [CS1030](../../misc/cs1030.md) 수준 1 컴파일러 경고를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dc8-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="84dc8-104">예:</span><span class="sxs-lookup"><span data-stu-id="84dc8-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="84dc8-105">설명</span><span class="sxs-lookup"><span data-stu-id="84dc8-105">Remarks</span></span>
 <span data-ttu-id="84dc8-106">`#warning`은 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dc8-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="84dc8-107">[#error](./preprocessor-error.md)를 사용하여 사용자 정의 오류를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dc8-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84dc8-108">예</span><span class="sxs-lookup"><span data-stu-id="84dc8-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="84dc8-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84dc8-109">See also</span></span>

- [<span data-ttu-id="84dc8-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="84dc8-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="84dc8-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="84dc8-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="84dc8-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="84dc8-112">C# Preprocessor Directives</span></span>](./index.md)
