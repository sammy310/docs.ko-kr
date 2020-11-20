---
title: with 식 - C# 참조
description: C# 레코드의 비파괴적 변경을 수행하는 with 식에 대해 알아봅니다.
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: 8412dfe8663703d3b201fe98b5f4752da1b344cf
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556714"
---
# <a name="with-expression-c-reference"></a><span data-ttu-id="3041d-103">with 식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3041d-103">with expression (C# reference)</span></span>

<span data-ttu-id="3041d-104">C# 9.0 이상에서 사용 가능한 `with` 식은 지정된 속성 및 필드를 수정하여 해당 [레코드](../../whats-new/csharp-9.md#record-types) 피연산자의 복사본을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-104">Available in C# 9.0 and later, a `with` expression produces a copy of its [record](../../whats-new/csharp-9.md#record-types) operand with the specified properties and fields modified:</span></span>

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

<span data-ttu-id="3041d-105">위 예제와 같이 [개체 이니셜라이저](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) 구문을 사용하여 수정할 멤버와 새 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-105">As the preceding example shows, you use [object initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) syntax to specify what members to modify and their new values.</span></span> <span data-ttu-id="3041d-106">`with` 식에서 왼쪽 피연산자는 레코드 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-106">In a `with` expression, a left-hand operand must be of a record type.</span></span>

<span data-ttu-id="3041d-107">다음 예제와 같이 `with` 식의 결과는 식의 피연산자와 동일한 런타임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-107">The result of a `with` expression has the same runtime type as the expression's operand, as the following example shows:</span></span>

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

<span data-ttu-id="3041d-108">참조 형식 멤버인 경우 레코드가 복사될 때 인스턴스에 대한 참조만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-108">In case of a reference-type member, only the reference to an instance is copied when a record is copied.</span></span> <span data-ttu-id="3041d-109">복사본과 원본 레코드 모두 동일한 참조 형식 인스턴스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-109">Both the copy and original record have access to the same reference-type instance.</span></span> <span data-ttu-id="3041d-110">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-110">The following example demonstrates that behavior:</span></span>

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

<span data-ttu-id="3041d-111">모든 레코드 형식에 ‘복사 생성자’가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-111">Any record type has the *copy constructor*.</span></span> <span data-ttu-id="3041d-112">이 생성자는 레코드 형식의 단일 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-112">That is a constructor with a single parameter of the containing record type.</span></span> <span data-ttu-id="3041d-113">또한 인수의 상태를 새 레코드 인스턴스로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-113">It copies the state of its argument to a new record instance.</span></span> <span data-ttu-id="3041d-114">`with` 식을 평가할 때 복사 생성자가 호출되어 원본 레코드를 기반으로 새 레코드 인스턴스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-114">At evaluation of a `with` expression, the copy constructor gets called to instantiate a new record instance based on an original record.</span></span> <span data-ttu-id="3041d-115">그런 다음, 지정된 수정 사항에 따라 새 인스턴스가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-115">After that, the new instance gets updated according to the specified modifications.</span></span> <span data-ttu-id="3041d-116">기본적으로 복사 생성자는 암시적으로, 컴파일러에서 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-116">By default, the copy constructor is implicit, that is, compiler-generated.</span></span> <span data-ttu-id="3041d-117">레코드 복사 의미 체계를 사용자 지정해야 하는 경우 원하는 동작으로 복사 생성자를 명시적으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-117">If you need to customize the record copy semantics, explicitly declare a copy constructor with the desired behavior.</span></span> <span data-ttu-id="3041d-118">다음 예제에서는 명시적 복사 생성자를 사용하여 위의 예제를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-118">The following example updates the preceding example with an explicit copy constructor.</span></span> <span data-ttu-id="3041d-119">새 복사 동작은 레코드가 복사될 때 목록 참조 대신 목록 항목을 복사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3041d-119">The new copy behavior is to copy list items instead of a list reference when a record is copied:</span></span>

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a><span data-ttu-id="3041d-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3041d-120">C# language specification</span></span>

<span data-ttu-id="3041d-121">자세한 내용은 [레코드 기능 제안 노트](~/_csharplang/proposals/csharp-9.0/records.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3041d-121">For more information, see the following sections of the [records feature proposal note](~/_csharplang/proposals/csharp-9.0/records.md):</span></span>

- [<span data-ttu-id="3041d-122">`with` 식</span><span class="sxs-lookup"><span data-stu-id="3041d-122">`with` expression</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [<span data-ttu-id="3041d-123">멤버 복사 및 복제</span><span class="sxs-lookup"><span data-stu-id="3041d-123">Copy and Clone members</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a><span data-ttu-id="3041d-124">참조</span><span class="sxs-lookup"><span data-stu-id="3041d-124">See also</span></span>

- [<span data-ttu-id="3041d-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3041d-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3041d-126">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="3041d-126">C# operators and expressions</span></span>](index.md)
