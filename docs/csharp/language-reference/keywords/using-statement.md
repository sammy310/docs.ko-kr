---
title: using 문 - C# 참조
ms.date: 10/15/2019
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 52cde99fd029ce50f159b2a87fbfbf47fc79dccc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712964"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="c7bc8-102">using 문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c7bc8-102">using statement (C# Reference)</span></span>

<span data-ttu-id="c7bc8-103"><xref:System.IDisposable> 개체의 올바른 사용을 보장하는 편리한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="c7bc8-104">예제</span><span class="sxs-lookup"><span data-stu-id="c7bc8-104">Example</span></span>

<span data-ttu-id="c7bc8-105">다음 예제에서는 `using` 문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

<span data-ttu-id="c7bc8-106">C# 8.0부터는 중괄호가 필요하지 않은 `using` 문에 다음 대체 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-106">Beginning with C# 8.0, you can use the following alternative syntax for the `using` statement that doesn't require braces:</span></span>

[!code-csharp[csrefKeywordsNamespace#New](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#ModernUsing)]

## <a name="remarks"></a><span data-ttu-id="c7bc8-107">설명</span><span class="sxs-lookup"><span data-stu-id="c7bc8-107">Remarks</span></span>

<span data-ttu-id="c7bc8-108"><xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스에 액세스하는 관리되는 형식의 예입니다(이 경우 파일 핸들 및 디바이스 컨텍스트).</span><span class="sxs-lookup"><span data-stu-id="c7bc8-108"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="c7bc8-109">다른 많은 종류의 관리되지 않는 리소스 및 이를 캡슐화하는 클래스 라이브러리 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-109">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="c7bc8-110">이러한 형식은 모두 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-110">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="c7bc8-111">`IDisposable` 개체의 수명이 단일 메서드로 제한된 경우 `using` 문에서 선언하고 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-111">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="c7bc8-112">`using` 문은 올바른 방법으로 개체에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하며, (앞서 설명한 대로 사용하는 경우) <xref:System.IDisposable.Dispose%2A>가 호출되자마자 개체 자체가 범위를 벗어나도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-112">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="c7bc8-113">`using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-113">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="c7bc8-114">`using` 문은 `using` 블록 내에서 예외가 발생하더라도 <xref:System.IDisposable.Dispose%2A>가 호출되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-114">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="c7bc8-115">`try` 블록 내부에 개체를 배치한 다음, `finally` 블록에서 <xref:System.IDisposable.Dispose%2A>를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 컴파일러는 이 방법으로 `using` 문을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-115">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="c7bc8-116">이전의 코드 예제는 컴파일 시 다음 코드로 확장됩니다(개체의 제한된 범위를 만드는 여분의 중괄호 참고).</span><span class="sxs-lookup"><span data-stu-id="c7bc8-116">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="c7bc8-117">최신 `using` 문 구문은 매우 유사한 코드로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-117">The newer `using` statement syntax translates to very similar code.</span></span> <span data-ttu-id="c7bc8-118">변수가 선언된 위치에서 `try` 블록이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-118">The `try` block opens where the variable is declared.</span></span> <span data-ttu-id="c7bc8-119">`finally` 블록은 일반적으로 메서드의 끝에 있는 바깥쪽 블록의 가까이에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-119">The `finally` block is added at the close of the enclosing block, typically at the end of a method.</span></span>

<span data-ttu-id="c7bc8-120">`try`-`finally` 문에 대한 자세한 내용은 [try-finally](try-finally.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-120">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="c7bc8-121">다음 예제와 같이 `using` 문에서 한 형식의 여러 인스턴스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-121">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="c7bc8-122">C# 8에 도입된 새로운 구문을 사용하여 동일한 형식의 여러 선언을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-122">You can combine multiple declarations of the same type using the new syntax introduced with C# 8 as well.</span></span> <span data-ttu-id="c7bc8-123">이는 다음 예제에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-123">This is shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#MultipleUsing)]

<span data-ttu-id="c7bc8-124">리소스 개체를 인스턴스화한 후 `using` 문에 변수를 전달할 수 있지만, 이 방법이 최선은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-124">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="c7bc8-125">이 경우 컨트롤이 `using` 블록을 벗어난 후에도 개체가 범위 내에 있지만, 관리되지 않는 리소스에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-125">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="c7bc8-126">즉, 더 이상 완전히 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-126">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="c7bc8-127">`using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-127">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="c7bc8-128">따라서 일반적으로 `using` 문에서 개체를 인스턴스화하고 `using` 블록에서 범위를 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-128">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="c7bc8-129">`IDisposable` 개체를 삭제하는 방법에 대한 자세한 내용은 [IDisposable을 구현하는 개체 사용](../../../standard/garbage-collection/using-objects.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-129">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c7bc8-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c7bc8-130">C# language specification</span></span>

<span data-ttu-id="c7bc8-131">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [using 문](~/_csharplang/spec/statements.md#the-using-statement)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-131">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c7bc8-132">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7bc8-132">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7bc8-133">참조</span><span class="sxs-lookup"><span data-stu-id="c7bc8-133">See also</span></span>

- [<span data-ttu-id="c7bc8-134">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c7bc8-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7bc8-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c7bc8-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7bc8-136">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="c7bc8-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c7bc8-137">using 지시문</span><span class="sxs-lookup"><span data-stu-id="c7bc8-137">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="c7bc8-138">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="c7bc8-138">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="c7bc8-139">IDisposable을 구현하는 개체 사용</span><span class="sxs-lookup"><span data-stu-id="c7bc8-139">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="c7bc8-140">IDisposable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7bc8-140">IDisposable interface</span></span>](xref:System.IDisposable)
- [<span data-ttu-id="c7bc8-141">C# 8.0의 using 문</span><span class="sxs-lookup"><span data-stu-id="c7bc8-141">using statement in C# 8.0</span></span>](~/_csharplang/proposals/csharp-8.0/using.md)
