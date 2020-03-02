---
title: 고정 크기 버퍼 - C# 프로그래밍 가이드
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 9005c425badc5a4ed74e6af3447e563daf61229e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627801"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="54aac-102">고정 크기 버퍼(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="54aac-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="54aac-103">C#에서는 [fixed](../../language-reference/keywords/fixed-statement.md) 문을 사용하여 데이터 구조에 고정 크기 배열이 있는 버퍼를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="54aac-104">고정 크기 버퍼는 다른 언어 또는 플랫폼에서 데이터 원본과 interop하는 메서드를 작성하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="54aac-105">고정 배열은 일반 구조체 멤버에 허용되는 특성이나 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="54aac-106">배열 형식이 `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` 또는 `double`이어야 한다는 것이 유일한 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="54aac-107">설명</span><span class="sxs-lookup"><span data-stu-id="54aac-107">Remarks</span></span>

<span data-ttu-id="54aac-108">안전한 코드에서 배열을 포함하는 C# 구조체는 배열 요소를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="54aac-109">대신 구조체에 요소에 대한 참조가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="54aac-110">[unsafe](../../language-reference/keywords/unsafe.md) 코드 블록에서 사용될 경우 [struct](../../language-reference/builtin-types/struct.md)에 고정 크기 배열을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-110">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="54aac-111">다음 `struct`은 8바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-111">The following `struct` is 8 bytes in size.</span></span> <span data-ttu-id="54aac-112">`pathName` 배열은 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-112">The `pathName` array is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="54aac-113">`struct`은 안전하지 않은 코드에 포함된 배열을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-113">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="54aac-114">다음 예제에서 `fixedBuffer` 배열은 고정 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="54aac-115">`fixed` 명령문을 사용하여 첫 번째 요소에 대한 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-115">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="54aac-116">이 포인터를 통해 배열의 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-116">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="54aac-117">`fixed` 명령문은 `fixedBuffer`의 인스턴스 필드를 메모리의 특정 위치에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-117">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="54aac-118">128개 요소 `char` 배열의 크기는 256바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-118">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="54aac-119">고정 크기 [char](../../language-reference/builtin-types/char.md) 버퍼는 인코딩에 관계없이 항상 문자당 2바이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-119">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="54aac-120">이는 char 버퍼가 `CharSet = CharSet.Auto` 또는 `CharSet = CharSet.Ansi`를 사용하는 API 메서드 또는 구조체로 마샬링되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-120">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="54aac-121">자세한 내용은 <xref:System.Runtime.InteropServices.CharSet>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54aac-121">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="54aac-122">앞의 예제에서는 C# 7.3부터 사용할 수 있으며 고정하지 않은 `fixed` 필드에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-122">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="54aac-123">또 다른 일반적인 고정 크기 배열은 [bool](../../language-reference/builtin-types/bool.md) 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-123">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="54aac-124">`bool` 배열의 요소 크기는 항상 1바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-124">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="54aac-125">`bool` 배열은 비트 배열이나 버퍼를 만드는 데 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-125">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

> [!NOTE]
> <span data-ttu-id="54aac-126">[stackalloc](../../language-reference/operators/stackalloc.md)를 사용하여 만든 메모리를 제외하고 C# 컴파일러와 CLR(공용 언어 런타임)에서 보안 버퍼 오버런 검사를 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-126">Except for memory created by using [stackalloc](../../language-reference/operators/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="54aac-127">모든 안전하지 않은 코드와 마찬가지로 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-127">As with all unsafe code, use caution.</span></span>

<span data-ttu-id="54aac-128">안전하지 않은 버퍼는 다음과 같은 측면에서 일반 배열과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-128">Unsafe buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="54aac-129">안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-129">You can only use unsafe buffers in an unsafe context.</span></span>
- <span data-ttu-id="54aac-130">안전하지 않은 버퍼는 항상 벡터 또는 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-130">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="54aac-131">배열의 선언에는 `char id[8]`와 같이 개수가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-131">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="54aac-132">`char id[]`을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-132">You cannot use `char id[]`.</span></span>
- <span data-ttu-id="54aac-133">안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서 구조체의 인스턴스 필드만 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aac-133">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>

## <a name="see-also"></a><span data-ttu-id="54aac-134">참조</span><span class="sxs-lookup"><span data-stu-id="54aac-134">See also</span></span>

- [<span data-ttu-id="54aac-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="54aac-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="54aac-136">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="54aac-136">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="54aac-137">fixed 문</span><span class="sxs-lookup"><span data-stu-id="54aac-137">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="54aac-138">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="54aac-138">Interoperability</span></span>](../interop/index.md)
