---
title: sizeof 연산자 - C# 참조
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 4852e1166a975b1a45c5bd905123a35fc846aa28
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513127"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="8c785-102">sizeof 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8c785-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="8c785-103">`sizeof` 연산자는 지정된 형식의 변수에서 사용하는 바이트 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="8c785-104">`sizeof` 연산자의 인수는 [비관리형 형식](../builtin-types/unmanaged-types.md) 또는 비관리형 형식이 되기 위해 [제한된](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) 형식 매개 변수의 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-104">An argument of the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="8c785-105">`sizeof` 연산자에 [안전하지 않은](../keywords/unsafe.md) 컨텍스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="8c785-106">그러나 아래 표의 식은 컴파일 시간에 해당 상수 값으로 계산되며 안전하지 않은 컨텍스트가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="8c785-107">식</span><span class="sxs-lookup"><span data-stu-id="8c785-107">Expression</span></span>|<span data-ttu-id="8c785-108">상수 값</span><span class="sxs-lookup"><span data-stu-id="8c785-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="8c785-109">1</span><span class="sxs-lookup"><span data-stu-id="8c785-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="8c785-110">1</span><span class="sxs-lookup"><span data-stu-id="8c785-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="8c785-111">2</span><span class="sxs-lookup"><span data-stu-id="8c785-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="8c785-112">2</span><span class="sxs-lookup"><span data-stu-id="8c785-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="8c785-113">4</span><span class="sxs-lookup"><span data-stu-id="8c785-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="8c785-114">4</span><span class="sxs-lookup"><span data-stu-id="8c785-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="8c785-115">8</span><span class="sxs-lookup"><span data-stu-id="8c785-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="8c785-116">8</span><span class="sxs-lookup"><span data-stu-id="8c785-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="8c785-117">2</span><span class="sxs-lookup"><span data-stu-id="8c785-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="8c785-118">4</span><span class="sxs-lookup"><span data-stu-id="8c785-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="8c785-119">8</span><span class="sxs-lookup"><span data-stu-id="8c785-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="8c785-120">16</span><span class="sxs-lookup"><span data-stu-id="8c785-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="8c785-121">1</span><span class="sxs-lookup"><span data-stu-id="8c785-121">1</span></span>|

<span data-ttu-id="8c785-122">`sizeof` 연산자의 피연산자가 [열거형](../keywords/enum.md) 형식의 이름인 경우에도 안전하지 않은 컨텍스트를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="8c785-123">다음 예제에서는 `sizeof` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="8c785-124">`sizeof` 연산자는 관리되는 메모리의 공용 언어 런타임에서 할당하는 바이트 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="8c785-125">[구조체](../keywords/struct.md) 형식의 경우 앞의 예제에서 보여 주는 것처럼 해당 값에 안쪽 여백이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-125">For [struct](../keywords/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="8c785-126">`sizeof` 연산자의 결과는 ‘관리되지 않는’ 메모리의 형식 크기를 반환하는 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 메서드의 결과와 다를 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="8c785-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8c785-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8c785-127">C# language specification</span></span>

<span data-ttu-id="8c785-128">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [sizeof 연산자](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c785-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c785-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c785-129">See also</span></span>

- [<span data-ttu-id="8c785-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8c785-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8c785-131">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8c785-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="8c785-132">포인터 관련 연산자</span><span class="sxs-lookup"><span data-stu-id="8c785-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="8c785-133">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="8c785-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8c785-134">메모리 및 범위 관련 형식</span><span class="sxs-lookup"><span data-stu-id="8c785-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
