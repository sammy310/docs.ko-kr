---
title: 인터페이스 속성 - C# 프로그래밍 가이드
description: C#의 인터페이스에 속성을 선언할 수 있습니다. 이 예제에서는 인터페이스 속성 접근자를 선언합니다.
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864971"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="a430f-104">인터페이스 속성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a430f-104">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="a430f-105">[interface](../../language-reference/keywords/interface.md)에 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-105">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="a430f-106">다음 예제에서는 인터페이스 속성 접근자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-106">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="a430f-107">일반적으로 인터페이스 속성에는 본문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-107">Interface properties typically don't have a body.</span></span> <span data-ttu-id="a430f-108">접근자는 속성이 읽기/쓰기인지, 읽기 전용인지, 쓰기 전용인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-108">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="a430f-109">클래스 및 구조체와 달리, 접근자를 본문 없이 선언해도 [자동 구현 속성](auto-implemented-properties.md)이 선언되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-109">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="a430f-110">C# 8.0부터 인터페이스는 멤버에 대한 기본 구현(속성 포함)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-110">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="a430f-111">인터페이스는 인스턴스 데이터 필드를 정의할 수 없으므로 인터페이스에서 속성에 대한 기본 구현을 정의하는 것은 드문 일입니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-111">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="a430f-112">예제</span><span class="sxs-lookup"><span data-stu-id="a430f-112">Example</span></span>

<span data-ttu-id="a430f-113">이 예제에서 `IEmployee` 인터페이스에는 읽기/쓰기 속성 `Name`과 읽기 전용 속성 `Counter`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-113">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="a430f-114">`Employee` 클래스는 `IEmployee` 인터페이스를 구현하고 이러한 두 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-114">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="a430f-115">프로그램은 새 직원의 이름과 현재 직원 수를 읽고 직원 이름과 계산된 직원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-115">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="a430f-116">멤버가 선언된 인터페이스를 참조하는 속성의 정규화된 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-116">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="a430f-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a430f-117">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="a430f-118">앞의 예제에서는 [명시적 인터페이스 구현](../interfaces/explicit-interface-implementation.md)을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-118">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="a430f-119">예를 들어 `Employee` 클래스가 두 인터페이스 `ICitizen` 및 `IEmployee`를 구현하고 두 인터페이스에 모두 `Name` 속성이 있으면 명시적 인터페이스 멤버 구현이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-119">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="a430f-120">즉, 다음과 같은 속성 선언이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-120">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="a430f-121">이 선언은 `IEmployee` 인터페이스의 `Name` 속성을 구현합니다. 또한 다음과 같은 선언이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-121">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="a430f-122">이 선언은 `ICitizen` 인터페이스의 `Name` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a430f-122">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="a430f-123">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="a430f-123">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="a430f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a430f-124">See also</span></span>

- [<span data-ttu-id="a430f-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a430f-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a430f-126">속성</span><span class="sxs-lookup"><span data-stu-id="a430f-126">Properties</span></span>](./properties.md)
- [<span data-ttu-id="a430f-127">속성 사용</span><span class="sxs-lookup"><span data-stu-id="a430f-127">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="a430f-128">속성 및 인덱서 비교</span><span class="sxs-lookup"><span data-stu-id="a430f-128">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="a430f-129">인덱서</span><span class="sxs-lookup"><span data-stu-id="a430f-129">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="a430f-130">인터페이스</span><span class="sxs-lookup"><span data-stu-id="a430f-130">Interfaces</span></span>](../interfaces/index.md)
