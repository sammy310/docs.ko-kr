---
description: volatile - C# 참조
title: volatile - C# 참조
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: bb89e99e8e28ff1e263817f498619dbfae700a50
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141701"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="5f69c-103">volatile(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5f69c-103">volatile (C# Reference)</span></span>

<span data-ttu-id="5f69c-104">`volatile` 키워드는 동시에 실행되는 여러 스레드에 의해 필드가 수정될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-104">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="5f69c-105">컴파일러, 런타임 시스템 및 하드웨어는 성능상의 이유로 메모리 위치에 대한 읽기 및 쓰기를 다시 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-105">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="5f69c-106">`volatile`로 선언된 필드에는 이러한 최적화가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-106">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="5f69c-107">`volatile` 한정자를 추가하면 모든 스레드가 수행된 순서대로 다른 스레드가 휘발성 쓰기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-107">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="5f69c-108">모든 실행 스레드에서처럼 휘발성 쓰기의 단일 순서가 모두 보장되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-108">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="5f69c-109">`volatile` 키워드는 다음 형식의 필드에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-109">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="5f69c-110">참조 형식.</span><span class="sxs-lookup"><span data-stu-id="5f69c-110">Reference types.</span></span>
- <span data-ttu-id="5f69c-111">포인터 형식(안전하지 않은 컨텍스트에서).</span><span class="sxs-lookup"><span data-stu-id="5f69c-111">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="5f69c-112">포인터 자체는 volatile이 될 수 있지만, 포인터가 가리키는 개체는 volatile이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-112">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="5f69c-113">즉, "pointer to volatile"을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-113">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="5f69c-114">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` 및 `bool`와 같은 단순 형식.</span><span class="sxs-lookup"><span data-stu-id="5f69c-114">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="5f69c-115">기본 형식 `byte`, `sbyte`, `short`, `ushort`, `int` 또는 `uint` 중 하나가 있는 `enum` 형식.</span><span class="sxs-lookup"><span data-stu-id="5f69c-115">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="5f69c-116">참조 형식으로 알려진 제네릭 형식 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="5f69c-116">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="5f69c-117"><xref:System.IntPtr>와 <xref:System.UIntPtr>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f69c-117"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="5f69c-118">`double` 및 `long`을 포함한 기타 형식은 해당 형식의 필드에 대한 읽기 및 쓰기가 원자성임을 보장할 수 없기 때문에 `volatile`로 표시될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-118">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="5f69c-119">이러한 형식의 필드에 대한 다중 스레드 액세스를 보호하려면 <xref:System.Threading.Interlocked> 클래스 멤버를 사용하거나 [`lock`](lock-statement.md) 문을 통해 액세스를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-119">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="5f69c-120">`volatile` 키워드는 `class` 또는 `struct`의 필드에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-120">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="5f69c-121">지역 변수는 `volatile`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-121">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="5f69c-122">예제</span><span class="sxs-lookup"><span data-stu-id="5f69c-122">Example</span></span>

<span data-ttu-id="5f69c-123">다음 예제에서는 공용 필드 변수를 `volatile`로 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-123">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="5f69c-124">다음 예제에서는 보조 또는 작업자 스레드를 만들어 기본 스레드와 병렬로 처리하는 데 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-124">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="5f69c-125">다중 스레딩에 대한 자세한 내용은 [관리되는 스레딩](../../../standard/threading/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f69c-125">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="5f69c-126">`_shouldStop`의 선언에 `volatile` 한정자를 추가하면 항상 동일한 결과가 표시됩니다(앞의 코드에 표시된 것과 유사함).</span><span class="sxs-lookup"><span data-stu-id="5f69c-126">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="5f69c-127">그러나 `_shouldStop` 멤버의 해당 한정자가 없으면 동작을 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-127">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="5f69c-128">`DoWork` 메서드가 멤버 액세스를 최적화할 수 있으므로 부실 데이터를 읽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-128">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="5f69c-129">다중 스레드 프로그래밍의 특성으로 인해 부실 읽기 수는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-129">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="5f69c-130">프로그램의 실행에 따라 약간 다른 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f69c-130">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f69c-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5f69c-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5f69c-132">참조</span><span class="sxs-lookup"><span data-stu-id="5f69c-132">See also</span></span>

- [<span data-ttu-id="5f69c-133">C# 언어 사양: volatile 키워드</span><span class="sxs-lookup"><span data-stu-id="5f69c-133">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="5f69c-134">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5f69c-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5f69c-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5f69c-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5f69c-136">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="5f69c-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5f69c-137">한정자</span><span class="sxs-lookup"><span data-stu-id="5f69c-137">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5f69c-138">lock 문</span><span class="sxs-lookup"><span data-stu-id="5f69c-138">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
