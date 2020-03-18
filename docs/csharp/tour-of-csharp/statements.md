---
title: C# 문 - C# 언어 둘러보기
description: 문을 사용하여 C# 프로그램 동작 만들기
ms.date: 02/27/2020
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.openlocfilehash: ced13b1bfd17977acb98bf33c0a477161cf08a93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159106"
---
# <a name="statements"></a><span data-ttu-id="fbee2-103">문</span><span class="sxs-lookup"><span data-stu-id="fbee2-103">Statements</span></span>

<span data-ttu-id="fbee2-104">프로그램의 동작은 *문*을 사용하여 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-104">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="fbee2-105">C#은 여러 다른 종류의 문을 지원하며 이중 많은 문이 포함 문에 대해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-105">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="fbee2-106">*블록*은 단일 문이 허용되는 컨텍스트에서 여러 문을 쓸 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-106">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="fbee2-107">블록은 구분 기호 `{`와 `}` 사이에 쓴 문 목록으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-107">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="fbee2-108">*선언 문*은 지역 변수 및 상수를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-108">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="fbee2-109">*식 문*은 식을 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-109">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="fbee2-110">문으로 사용할 수 있는 식에는 메서드 호출, `new` 연산자를 사용하는 개체 할당, `=` 및 복합 할당 연산자를 사용하는 대입, `++` 및 `--` 연산자를 사용하는 증가 및 감소 연산, `await` 식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-110">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="fbee2-111">*선택 문*은 일부 식 값에 따라 실행할 수 있는 다양한 문 중에서 하나를 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-111">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="fbee2-112">이 그룹에는 `if` 문과 `switch` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-112">This group contains the `if` and `switch` statements.</span></span>

<span data-ttu-id="fbee2-113">*반복 문*은 포함 문을 반복해서 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-113">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="fbee2-114">이 그룹에는 `while` 문, `do` 문, `for` 문과 `foreach` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-114">This group contains the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="fbee2-115">*점프 문*은 제어를 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-115">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="fbee2-116">이 그룹에는 `break` 문, `continue` 문, `goto` 문, `throw` 문, `return` 문과 `yield` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-116">This group contains the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="fbee2-117">`try`... `catch` 문은 블록 실행 중에 발생하는 예외를 catch하는 데 사용되고 `try`... `finally` 문은 예외 발생 여부에 관계 없이 항상 실행되는 종료 코드를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-117">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="fbee2-118">`checked` 및 `unchecked` 문은 정수 계열 형식 산술 연산 및 변환에 대한 오버플로 검사 컨텍스트를 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-118">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="fbee2-119">`lock` 문은 지정된 개체에 대한 상호 배타적 잠금을 획득하고, 문을 실행한 후 잠금을 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-119">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="fbee2-120">`using` 문은 리소스를 획득하고, 문을 실행한 후 해당 리소스를 삭제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-120">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="fbee2-121">다음은 사용할 수 있는 문 종류와 각각에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fbee2-121">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="fbee2-122">지역 변수 선언:</span><span class="sxs-lookup"><span data-stu-id="fbee2-122">Local variable declaration:</span></span>

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* <span data-ttu-id="fbee2-123">지역 상수 선언:</span><span class="sxs-lookup"><span data-stu-id="fbee2-123">Local constant declaration:</span></span>

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* <span data-ttu-id="fbee2-124">식 문</span><span class="sxs-lookup"><span data-stu-id="fbee2-124">Expression statement:</span></span>

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* <span data-ttu-id="fbee2-125">`if` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-125">`if` statement:</span></span>

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* <span data-ttu-id="fbee2-126">`switch` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-126">`switch` statement:</span></span>

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* <span data-ttu-id="fbee2-127">`while` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-127">`while` statement:</span></span>

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* <span data-ttu-id="fbee2-128">`do` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-128">`do` statement:</span></span>

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* <span data-ttu-id="fbee2-129">`for` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-129">`for` statement:</span></span>

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* <span data-ttu-id="fbee2-130">`foreach` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-130">`foreach` statement:</span></span>

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* <span data-ttu-id="fbee2-131">`break` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-131">`break` statement:</span></span>

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* <span data-ttu-id="fbee2-132">`continue` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-132">`continue` statement:</span></span>

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* <span data-ttu-id="fbee2-133">`goto` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-133">`goto` statement:</span></span>

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* <span data-ttu-id="fbee2-134">`return` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-134">`return` statement:</span></span>

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* <span data-ttu-id="fbee2-135">`yield` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-135">`yield` statement:</span></span>

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* <span data-ttu-id="fbee2-136">`throw`문 및 `try` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-136">`throw` statements and `try` statements:</span></span>

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* <span data-ttu-id="fbee2-137">`checked` 및 `unchecked` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-137">`checked` and `unchecked` statements:</span></span>

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* <span data-ttu-id="fbee2-138">`lock` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-138">`lock` statement:</span></span>

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* <span data-ttu-id="fbee2-139">`using` 문:</span><span class="sxs-lookup"><span data-stu-id="fbee2-139">`using` statement:</span></span>

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
><span data-ttu-id="fbee2-140">[이전](expressions.md)
>[다음](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="fbee2-140">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>
