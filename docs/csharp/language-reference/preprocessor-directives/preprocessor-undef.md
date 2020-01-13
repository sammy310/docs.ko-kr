---
title: '#undef - C# 참조'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 21923412aa178c3b86e94a54bd911130e48e4deb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712444"
---
# <a name="undef-c-reference"></a><span data-ttu-id="fc896-102">#undef(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fc896-102">#undef (C# Reference)</span></span>
<span data-ttu-id="fc896-103">`#undef`를 사용하면 기호의 정의를 해제할 수 있습니다. 그러면 [#if](./preprocessor-if.md) 지시문에서 해당 기호를 식으로 사용하여 식이 `false`로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc896-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="fc896-104">[#define](./preprocessor-define.md) 지시문 또는 [-define](../compiler-options/define-compiler-option.md) 컴파일러 옵션을 사용하여 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc896-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="fc896-105">`#undef` 지시문은 지시문이 아닌 문을 사용하기 전에 파일에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc896-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc896-106">예제</span><span class="sxs-lookup"><span data-stu-id="fc896-106">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="fc896-107">**디버그가 정의되어 있지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="fc896-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="fc896-108">참조</span><span class="sxs-lookup"><span data-stu-id="fc896-108">See also</span></span>

- [<span data-ttu-id="fc896-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fc896-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fc896-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fc896-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fc896-111">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="fc896-111">C# Preprocessor Directives</span></span>](./index.md)
