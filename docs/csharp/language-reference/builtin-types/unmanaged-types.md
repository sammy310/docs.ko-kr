---
title: 비관리형 형식 - C# 참조
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512071"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="19153-102">비관리형 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="19153-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="19153-103">**비관리형 형식**은 참조 형식이거나 생성된 형식(하나 이상의 형식 인수를 포함하는 형식)이 아닌 형식이며, 모든 중첩 수준에서 참조 형식이나 생성된 형식 필드를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19153-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="19153-104">즉 비관리형 형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="19153-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="19153-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` 또는 `bool`</span><span class="sxs-lookup"><span data-stu-id="19153-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="19153-106">임의의 [열거형](../keywords/enum.md) 형식</span><span class="sxs-lookup"><span data-stu-id="19153-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="19153-107">임의의 [포인터](../../programming-guide/unsafe-code-pointers/pointer-types.md) 형식</span><span class="sxs-lookup"><span data-stu-id="19153-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="19153-108">생성된 형식이 아니고 비관리형 형식의 필드만 포함하는 임의의 사용자 정의 [구조체](../keywords/struct.md) 형식</span><span class="sxs-lookup"><span data-stu-id="19153-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="19153-109">C# 7.3부터 [`unmanaged` 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)을 사용하여 형식 매개 변수가 비포인터 비관리형 형식임을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19153-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="19153-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="19153-110">C# language specification</span></span>

<span data-ttu-id="19153-111">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [포인터 형식](~/_csharplang/spec/unsafe-code.md#pointer-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19153-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19153-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19153-112">See also</span></span>

- [<span data-ttu-id="19153-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="19153-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="19153-114">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="19153-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="19153-115">메모리 및 범위 관련 형식</span><span class="sxs-lookup"><span data-stu-id="19153-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="19153-116">sizeof 연산자</span><span class="sxs-lookup"><span data-stu-id="19153-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="19153-117">stackalloc 연산자</span><span class="sxs-lookup"><span data-stu-id="19153-117">stackalloc operator</span></span>](../operators/stackalloc.md)
