---
title: void - C# 참조
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742766"
---
# <a name="void-c-reference"></a><span data-ttu-id="a25dc-102">void(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a25dc-102">void (C# Reference)</span></span>

<span data-ttu-id="a25dc-103">메서드에 대한 반환 형식으로 사용될 경우 `void`는 메서드가 값을 반환하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a25dc-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="a25dc-104">`void`는 메서드의 매개 변수 목록에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a25dc-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="a25dc-105">매개 변수를 사용하지 않고 값을 반환하지 않는 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25dc-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="a25dc-106">`void`는 또한 알 수 없는 형식에 대한 포인터를 선언하기 위해 안전하지 않은 컨텍스트에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25dc-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="a25dc-107">자세한 내용은 [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a25dc-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="a25dc-108">`void`는 .NET Framework <xref:System.Void?displayProperty=nameWithType> 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="a25dc-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a25dc-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a25dc-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a25dc-110">참조</span><span class="sxs-lookup"><span data-stu-id="a25dc-110">See also</span></span>

- [<span data-ttu-id="a25dc-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a25dc-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a25dc-112">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a25dc-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a25dc-113">참조 형식</span><span class="sxs-lookup"><span data-stu-id="a25dc-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="a25dc-114">값 형식</span><span class="sxs-lookup"><span data-stu-id="a25dc-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="a25dc-115">메서드</span><span class="sxs-lookup"><span data-stu-id="a25dc-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="a25dc-116">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="a25dc-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
