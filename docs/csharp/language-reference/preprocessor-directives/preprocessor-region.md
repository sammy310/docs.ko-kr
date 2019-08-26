---
title: '#region - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ba5b47d77c69761a77b05ac6079e1b003af336b3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608760"
---
# <a name="region-c-reference"></a><span data-ttu-id="cefdd-102">#region(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cefdd-102">#region (C# Reference)</span></span>
<span data-ttu-id="cefdd-103">`#region`을 사용하면 Visual Studio Code 편집기의 [개요 기능](/visualstudio/ide/outlining)을 사용할 때 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cefdd-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="cefdd-104">더 긴 코드 파일에서 현재 작업 중인 파일 부분에 집중할 수 있도록 하나 이상의 영역을 축소하거나 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cefdd-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="cefdd-105">다음 예제에서는 영역을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cefdd-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="cefdd-106">설명</span><span class="sxs-lookup"><span data-stu-id="cefdd-106">Remarks</span></span>  
 <span data-ttu-id="cefdd-107">`#region` 블록은 [#endregion](./preprocessor-endregion.md) 지시문으로 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cefdd-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="cefdd-108">`#region` 블록은 [#if](./preprocessor-if.md) 블록과 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cefdd-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="cefdd-109">그러나 `#region` 블록을 `#if` 블록에 중첩할 수 있고 `#if` 블록을 `#region` 블록에 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cefdd-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefdd-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cefdd-110">See also</span></span>

- [<span data-ttu-id="cefdd-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cefdd-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cefdd-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cefdd-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cefdd-113">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="cefdd-113">C# Preprocessor Directives</span></span>](./index.md)
