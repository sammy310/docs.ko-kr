---
description: '#region - C# 참조'
title: '#region - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ed40d895fedb9be271bb389a4f8de69d7ae3f266
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137944"
---
# <a name="region-c-reference"></a><span data-ttu-id="d2876-103">#region(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d2876-103">#region (C# Reference)</span></span>
<span data-ttu-id="d2876-104">`#region`을 사용하면 코드 편집기의 [개요 기능](/visualstudio/ide/outlining)을 사용할 때 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2876-104">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="d2876-105">더 긴 코드 파일에서 현재 작업 중인 파일 부분에 집중할 수 있도록 하나 이상의 영역을 축소하거나 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2876-105">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="d2876-106">다음 예제에서는 영역을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2876-106">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass
{  
    static void Main()
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="d2876-107">설명</span><span class="sxs-lookup"><span data-stu-id="d2876-107">Remarks</span></span>  
 <span data-ttu-id="d2876-108">`#region` 블록은 [#endregion](./preprocessor-endregion.md) 지시문으로 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2876-108">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="d2876-109">`#region` 블록은 [#if](./preprocessor-if.md) 블록과 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2876-109">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="d2876-110">그러나 `#region` 블록을 `#if` 블록에 중첩할 수 있고 `#if` 블록을 `#region` 블록에 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2876-110">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2876-111">참조</span><span class="sxs-lookup"><span data-stu-id="d2876-111">See also</span></span>

- [<span data-ttu-id="d2876-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d2876-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d2876-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d2876-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d2876-114">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="d2876-114">C# Preprocessor Directives</span></span>](./index.md)
