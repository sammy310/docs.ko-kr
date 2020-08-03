---
title: 특성을 사용하여 C/C++ 공용 구조체 만드는 방법(C#)
description: 특성을 사용하여 C#의 메모리에서 구조체가 레이아웃되는 방식을 사용자 지정하는 방법에 대해 알아봅니다. 이 예제에서는 C/C++의 공용 구조체와 같은 요소를 구현합니다.
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: 766a070105441630dfd8fecf7b9f68fa6818fe50
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925074"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="c3b73-104">특성을 사용하여 C/C++ 공용 구조체 만드는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="c3b73-104">How to create a C/C++ union by using attributes (C#)</span></span>

<span data-ttu-id="c3b73-105">특성을 사용하여 메모리에서 구조체가 레이아웃되는 방식을 필요에 맞게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b73-105">By using attributes, you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="c3b73-106">예를 들어 `StructLayout(LayoutKind.Explicit)` 및 `FieldOffset` 특성을 사용하여 C/C++에서 공용 구조체로 알려진 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b73-106">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="c3b73-107">예제</span><span class="sxs-lookup"><span data-stu-id="c3b73-107">Example</span></span>

<span data-ttu-id="c3b73-108">이 코드 세그먼트에서 `TestUnion`의 모든 필드는 메모리의 같은 위치에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b73-108">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestUnion
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public byte b;
}
```

## <a name="example"></a><span data-ttu-id="c3b73-109">예제</span><span class="sxs-lookup"><span data-stu-id="c3b73-109">Example</span></span>

<span data-ttu-id="c3b73-110">다음은 명시적으로 설정된 다른 위치에서 필드가 시작하는 또 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b73-110">The following is another example where fields start at different explicitly set locations.</span></span>

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestExplicit
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public long lg;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i1;

    [System.Runtime.InteropServices.FieldOffset(4)]
    public int i2;

    [System.Runtime.InteropServices.FieldOffset(8)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(12)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(14)]
    public byte b;
}
```

<span data-ttu-id="c3b73-111">두 개의 정수 필드 `i1` 및 `i2`는 `lg`와 동일한 메모리 위치를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b73-111">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="c3b73-112">구조체 레이아웃에 대한 이러한 종류의 제어는 플랫폼 호출을 사용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b73-112">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3b73-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3b73-113">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="c3b73-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c3b73-114">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="c3b73-115">특성</span><span class="sxs-lookup"><span data-stu-id="c3b73-115">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="c3b73-116">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="c3b73-116">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="c3b73-117">특성(C#)</span><span class="sxs-lookup"><span data-stu-id="c3b73-117">Attributes (C#)</span></span>](index.md)
- [<span data-ttu-id="c3b73-118">사용자 지정 특성 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="c3b73-118">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="c3b73-119">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="c3b73-119">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
