---
title: 고정 크기 버퍼 - C# 프로그래밍 가이드
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5920dd125ded34969d60feb299568b56402056ab
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140549"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="05879-102">고정 크기 버퍼(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="05879-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="05879-103">C#에서는 [fixed](../../language-reference/keywords/fixed-statement.md) 문을 사용하여 데이터 구조에 고정 크기 배열이 있는 버퍼를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="05879-104">고정 크기 버퍼는 다른 언어 또는 플랫폼에서 데이터 원본과 interop하는 메서드를 작성하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="05879-105">고정 배열은 일반 구조체 멤버에 허용되는 특성이나 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="05879-106">배열 형식이 `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` 또는 `double`이어야 한다는 것이 유일한 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="05879-107">설명</span><span class="sxs-lookup"><span data-stu-id="05879-107">Remarks</span></span>

<span data-ttu-id="05879-108">안전한 코드에서 배열을 포함하는 C# 구조체는 배열 요소를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="05879-109">대신 구조체에 요소에 대한 참조가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="05879-110">[unsafe](../../language-reference/keywords/unsafe.md) 코드 블록에서 사용될 경우 [struct](../../language-reference/builtin-types/struct.md)에 고정 크기 배열을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-110">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="05879-111">`pathName`이 참조이므로 다음 `struct`의 크기는 배열에 있는 요소의 수에 따라 달라지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-111">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="05879-112">`struct`은 안전하지 않은 코드에 포함된 배열을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-112">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="05879-113">다음 예제에서 `fixedBuffer` 배열은 고정 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-113">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="05879-114">`fixed` 명령문을 사용하여 첫 번째 요소에 대한 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-114">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="05879-115">이 포인터를 통해 배열의 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-115">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="05879-116">`fixed` 명령문은 `fixedBuffer`의 인스턴스 필드를 메모리의 특정 위치에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-116">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="05879-117">128개 요소 `char` 배열의 크기는 256바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="05879-118">고정 크기 [char](../../language-reference/builtin-types/char.md) 버퍼는 인코딩에 관계없이 항상 문자당 2바이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-118">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="05879-119">이는 char 버퍼가 `CharSet = CharSet.Auto` 또는 `CharSet = CharSet.Ansi`를 사용하는 API 메서드 또는 구조체로 마샬링되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="05879-120">자세한 내용은 <xref:System.Runtime.InteropServices.CharSet>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05879-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="05879-121">앞의 예제에서는 C# 7.3부터 사용할 수 있으며 고정하지 않은 `fixed` 필드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05879-121">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="05879-122">또 다른 일반적인 고정 크기 배열은 [bool](../../language-reference/builtin-types/bool.md) 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-122">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="05879-123">`bool` 배열의 요소 크기는 항상 1바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-123">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="05879-124">`bool` 배열은 비트 배열이나 버퍼를 만드는 데 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-124">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="05879-125">고정 크기 버퍼는 잠재적으로 오버플로될 수 있는 관리되지 않는 배열을 형식에 포함하는 CLR(공용 언어 런타임)에 지시하는 <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="05879-125">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="05879-126">이는 CLR에서 버퍼 오버런 검색 기능을 자동으로 사용하도록 설정하는 [stackalloc](../../language-reference/operators/stackalloc.md)를 사용하여 만든 메모리와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-126">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="05879-127">이전 예제에서는 `unsafe struct`에 고정 크기 버퍼가 존재할 수 있는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="05879-127">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="05879-128">`Buffer`에 대해 컴파일에서 생성된 C#은 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-128">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

<span data-ttu-id="05879-129">고정 크기 버퍼는 다음과 같은 측면에서 일반 배열과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="05879-129">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="05879-130">[안전하지 않은](../../language-reference/keywords/unsafe.md) 컨텍스트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-130">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="05879-131">단지 구조체의 인스턴스 필드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-131">May only be instance fields of structs.</span></span>
- <span data-ttu-id="05879-132">항상 벡터 또는 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="05879-132">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="05879-133">선언에는 `fixed char id[8]`와 같은 길이가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05879-133">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="05879-134">`fixed char id[]`을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05879-134">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="05879-135">참조</span><span class="sxs-lookup"><span data-stu-id="05879-135">See also</span></span>

- [<span data-ttu-id="05879-136">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="05879-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="05879-137">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="05879-137">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="05879-138">fixed 문</span><span class="sxs-lookup"><span data-stu-id="05879-138">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="05879-139">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="05879-139">Interoperability</span></span>](../interop/index.md)
