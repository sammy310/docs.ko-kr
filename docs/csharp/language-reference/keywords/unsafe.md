---
description: unsafe 키워드 - C# 참조
title: unsafe 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 5be895621966dd10b2b1b0f53ebf0f3c688f1ef0
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480660"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="3a87d-103">unsafe(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3a87d-103">unsafe (C# Reference)</span></span>

<span data-ttu-id="3a87d-104">`unsafe` 키워드는 포인터와 관련된 모든 작업에 필요한 안전하지 않은 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-104">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="3a87d-105">자세한 내용은 [안전하지 않은 코드 및 포인터](../../programming-guide/unsafe-code-pointers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a87d-105">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="3a87d-106">형식 또는 멤버 선언에서 `unsafe` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-106">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="3a87d-107">따라서 형식 또는 멤버의 전체 텍스트 범위가 안전하지 않은 컨텍스트로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-107">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="3a87d-108">예를 들어 다음은 `unsafe` 한정자를 사용하여 선언된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-108">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="3a87d-109">안전하지 않은 컨텍스트의 범위는 매개 변수 목록에서 메서드의 끝까지 확장되므로 매개 변수 목록에 포인터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-109">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="3a87d-110">안전하지 않은 블록을 통해 이 블록 내에서 안전하지 않은 코드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-110">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="3a87d-111">예:</span><span class="sxs-lookup"><span data-stu-id="3a87d-111">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="3a87d-112">안전하지 않은 코드를 컴파일하려면 [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks) 컴파일러 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-112">To compile unsafe code, you must specify the [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks) compiler option.</span></span> <span data-ttu-id="3a87d-113">안전하지 않은 코드는 공용 언어 런타임에서 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-113">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="3a87d-114">예제</span><span class="sxs-lookup"><span data-stu-id="3a87d-114">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="3a87d-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3a87d-115">C# language specification</span></span>

<span data-ttu-id="3a87d-116">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [안전하지 않은 코드](~/_csharplang/spec/unsafe-code.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a87d-116">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="3a87d-117">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a87d-117">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a87d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a87d-118">See also</span></span>

- [<span data-ttu-id="3a87d-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3a87d-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a87d-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3a87d-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a87d-121">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="3a87d-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3a87d-122">fixed 문</span><span class="sxs-lookup"><span data-stu-id="3a87d-122">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="3a87d-123">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="3a87d-123">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="3a87d-124">고정 크기 버퍼</span><span class="sxs-lookup"><span data-stu-id="3a87d-124">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
