---
title: struct - C# 참조
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8d9a23a0813423571c894758257b284ad67a72e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744652"
---
# <a name="struct-c-reference"></a><span data-ttu-id="cc93d-102">struct(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cc93d-102">struct (C# Reference)</span></span>

<span data-ttu-id="cc93d-103">`struct` 형식은 인벤토리의 항목 특성이나 사각형의 좌표와 같은 관련 변수의 소규모 그룹을 캡슐화하는 데 일반적으로 사용되는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cc93d-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="cc93d-104">다음 예제에서는 간단한 구조체 선언을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc93d-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="cc93d-105">설명</span><span class="sxs-lookup"><span data-stu-id="cc93d-105">Remarks</span></span>

<span data-ttu-id="cc93d-106">구조체는 [생성자](../../programming-guide/classes-and-structs/constructors.md), [상수](../../programming-guide/classes-and-structs/constants.md), [필드](../../programming-guide/classes-and-structs/fields.md), [메서드](../../programming-guide/classes-and-structs/methods.md), [속성](../../programming-guide/classes-and-structs/properties.md), [인덱서](../../programming-guide/indexers/index.md), [연산자](../operators/index.md), [이벤트](../../programming-guide/events/index.md) 및 [중첩 형식](../../programming-guide/classes-and-structs/nested-types.md)도 포함할 수 있습니다. 그러나 이러한 멤버가 여러 개 필요한 경우에는 구조체 대신 클래스 형식을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc93d-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="cc93d-107">예제를 보려면 [구조체 사용](../../programming-guide/classes-and-structs/using-structs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc93d-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="cc93d-108">구조체는 인터페이스를 구현할 수는 있지만 다른 구조체를 상속할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc93d-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="cc93d-109">그러므로 구조체 멤버를 `protected`로 선언할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc93d-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="cc93d-110">자세한 내용은 [구조체](../../programming-guide/classes-and-structs/structs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc93d-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="cc93d-111">예</span><span class="sxs-lookup"><span data-stu-id="cc93d-111">Examples</span></span>

<span data-ttu-id="cc93d-112">예제 및 자세한 내용은 [구조체 사용](../../programming-guide/classes-and-structs/using-structs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc93d-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cc93d-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="cc93d-113">C# language specification</span></span>

<span data-ttu-id="cc93d-114">예제를 보려면 [구조체 사용](../../programming-guide/classes-and-structs/using-structs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc93d-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc93d-115">참조</span><span class="sxs-lookup"><span data-stu-id="cc93d-115">See also</span></span>

- [<span data-ttu-id="cc93d-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cc93d-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="cc93d-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="cc93d-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="cc93d-118">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="cc93d-118">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="cc93d-119">값 형식</span><span class="sxs-lookup"><span data-stu-id="cc93d-119">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="cc93d-120">class</span><span class="sxs-lookup"><span data-stu-id="cc93d-120">class</span></span>](class.md)
- [<span data-ttu-id="cc93d-121">interface</span><span class="sxs-lookup"><span data-stu-id="cc93d-121">interface</span></span>](interface.md)
- [<span data-ttu-id="cc93d-122">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="cc93d-122">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
