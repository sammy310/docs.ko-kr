---
description: LINQ를 지 원하는 Visual Basic 기능에 대해 자세히 알아보세요.
title: LINQ를 지 원하는 기능
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: 58862ac4083bcd58ee08ef1afeebf95541c53e98
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428641"
---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="be182-103">LINQ를 지원하는 Visual Basic 기능</span><span class="sxs-lookup"><span data-stu-id="be182-103">Visual Basic Features That Support LINQ</span></span>

<span data-ttu-id="be182-104">LINQ (이름 Language-Integrated 쿼리)는 언어에서 직접 쿼리 구문 및 기타 언어 구문을 지 원하는 Visual Basic의 기술을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be182-104">The name Language-Integrated Query (LINQ) refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="be182-105">LINQ를 사용 하면 외부 데이터 원본에 대해 쿼리 하는 새 언어를 배울 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-105">With LINQ, you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="be182-106">Visual Basic를 사용 하 여 관계형 데이터베이스, XML 저장소 또는 개체의 데이터에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-106">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="be182-107">이러한 쿼리 기능을 언어에 통합 하면 구문 오류 및 형식 안전성에 대 한 컴파일 시간 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-107">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="be182-108">또한이 통합은 Visual Basic에서 다양 한 가변 쿼리를 작성 하기 위해 알고 있어야 하는 사항 대부분을 이미 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-108">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="be182-109">다음 섹션에서는 소개 문서, 코드 예제 및 예제 응용 프로그램을 읽을 수 있는 충분 한 정보를 제공 하는 언어 구문에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-109">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="be182-110">또한 링크를 클릭 하 여 언어 기능을 함께 사용 하 여 언어 통합 쿼리를 사용 하는 방법에 대 한 자세한 설명을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-110">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="be182-111">[연습: Visual Basic에서 쿼리 작성](walkthrough-writing-queries.md)을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-111">A good place to start is [Walkthrough: Writing Queries in Visual Basic](walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="be182-112">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="be182-112">Query Expressions</span></span>  

 <span data-ttu-id="be182-113">Visual Basic의 쿼리 식은 SQL 또는 XQuery와 유사한 선언적 구문으로 표현 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-113">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="be182-114">컴파일 시간에 쿼리 구문은 표준 쿼리 연산자 확장 메서드의 LINQ 공급자 구현에 대 한 메서드 호출로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be182-114">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="be182-115">응용 프로그램은 문을 사용 하 여 적절 한 네임 스페이스를 지정 하 여 범위 내에 있는 표준 쿼리 연산자를 제어 `Imports` 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-115">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="be182-116">Visual Basic 쿼리 식의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-116">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="be182-117">자세한 내용은 [Visual Basic의 LINQ 쿼리 소개](../../language-features/linq/introduction-to-linq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be182-117">For more information, see [Introduction to LINQ in Visual Basic](../../language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="be182-118">암시적으로 형식화 된 변수</span><span class="sxs-lookup"><span data-stu-id="be182-118">Implicitly Typed Variables</span></span>  

 <span data-ttu-id="be182-119">변수를 선언 하 고 초기화할 때 형식을 명시적으로 지정 하는 대신 컴파일러가 형식을 유추 하 고 할당 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-119">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="be182-120">이를 *로컬 형식 유추* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-120">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="be182-121">형식을 명시적으로 지정 하는 변수와 마찬가지로 형식이 유추 되는 변수가 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="be182-121">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="be182-122">지역 형식 유추는 메서드 본문 내에서 지역 변수를 정의 하는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-122">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="be182-123">자세한 내용은 [Option 유추 문](../../../language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be182-123">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="be182-124">다음 예제에서는 로컬 형식 유추를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be182-124">The following example illustrates local type inference.</span></span> <span data-ttu-id="be182-125">이 예를 사용 하려면를로 설정 해야 합니다 `Option Infer` `On` .</span><span class="sxs-lookup"><span data-stu-id="be182-125">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="be182-126">로컬 형식 유추를 사용 하 여 익명 형식을 만들 수도 있습니다 .이는이 단원의 뒷부분에 설명 되어 있으며 LINQ 쿼리에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-126">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="be182-127">다음 LINQ 예제에서는가 또는 일 경우 형식 유추가 발생 합니다 `Option Infer` `On` `Off` .</span><span class="sxs-lookup"><span data-stu-id="be182-127">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="be182-128">`Option Infer`가이 고가 이면 컴파일 시간 오류가 발생 합니다 `Off` `Option Strict` `On` .</span><span class="sxs-lookup"><span data-stu-id="be182-128">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a><span data-ttu-id="be182-129">개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="be182-129">Object Initializers</span></span>  

 <span data-ttu-id="be182-130">쿼리 결과를 저장 하는 무명 형식을 만들어야 하는 경우에는 쿼리 식에 개체 이니셜라이저가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be182-130">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="be182-131">또한 쿼리 외부의 명명 된 형식의 개체를 초기화 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-131">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="be182-132">개체 이니셜라이저를 사용 하면 명시적으로 생성자를 호출 하지 않고 단일 줄로 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-132">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="be182-133">`Customer`다른 속성과 함께 public 및 속성을 포함 하는 라는 클래스가 있다고 가정 하면 `Name` `Phone` 다음과 같은 방식으로 개체 이니셜라이저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-133">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 <span data-ttu-id="be182-134">자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be182-134">For more information, see [Object Initializers: Named and Anonymous Types](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="be182-135">익명 형식</span><span class="sxs-lookup"><span data-stu-id="be182-135">Anonymous Types</span></span>  

 <span data-ttu-id="be182-136">익명 형식은 속성 집합을 쿼리 결과에 포함 하려는 요소로 일시적으로 그룹화 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-136">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="be182-137">이렇게 하면 요소에 대 한 명명 된 데이터 형식을 정의 하지 않고 쿼리에서 사용 가능한 필드의 조합을 임의의 순서로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-137">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="be182-138">*익명 형식은* 컴파일러에 의해 동적으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be182-138">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="be182-139">형식 이름은 컴파일러에 의해 할당 되며, 각각의 새 컴파일에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-139">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="be182-140">따라서 이름을 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-140">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="be182-141">익명 형식은 다음과 같은 방식으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be182-141">Anonymous types are initialized in the following way:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 <span data-ttu-id="be182-142">자세한 내용은 [무명 형식](../../language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be182-142">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="be182-143">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="be182-143">Extension Methods</span></span>  

 <span data-ttu-id="be182-144">확장 메서드를 사용 하면 정의 외부에서 데이터 형식 또는 인터페이스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-144">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="be182-145">이 기능을 사용 하면 실제로 형식을 수정 하지 않고도 기존 형식에 새 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-145">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="be182-146">표준 쿼리 연산자는을 구현 하는 모든 형식에 대해 LINQ 쿼리 기능을 제공 하는 확장 메서드 집합입니다 <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="be182-146">The standard query operators are themselves a set of extension methods that provide LINQ query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="be182-147">, 및를 포함 하는 다른 확장 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.Enumerable.Count%2A> <xref:System.Linq.Enumerable.Union%2A> <xref:System.Linq.Enumerable.Intersect%2A> 입니다.</span><span class="sxs-lookup"><span data-stu-id="be182-147">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="be182-148">다음 확장 메서드는 인쇄 메서드를 클래스에 추가 합니다 <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="be182-148">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 <span data-ttu-id="be182-149">메서드는의 일반 인스턴스 메서드와 같이 호출 됩니다 <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="be182-149">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 <span data-ttu-id="be182-150">자세한 내용은 [확장 메서드](../../language-features/procedures/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be182-150">For more information, see [Extension Methods](../../language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="be182-151">람다 식</span><span class="sxs-lookup"><span data-stu-id="be182-151">Lambda Expressions</span></span>  

 <span data-ttu-id="be182-152">람다 식은 단일 값을 계산 하 고 반환 하는 이름이 없는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="be182-152">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="be182-153">명명 된 함수와 달리 람다 식을 동시에 정의 하 고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-153">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="be182-154">다음 예에서는 4를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-154">The following example displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="be182-155">람다 식 정의를 변수 이름에 할당 한 다음 이름을 사용 하 여 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be182-155">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="be182-156">또한 다음 예제에서는 4를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-156">The following example also displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 <span data-ttu-id="be182-157">LINQ에서 람다 식은 많은 표준 쿼리 연산자의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be182-157">In LINQ, lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="be182-158">컴파일러는,,, 등의 기본 쿼리 메서드에 정의 된 계산을 캡처하기 위해 람다 식을 `Where` 만듭니다 `Select` `Order By` `Take While` .</span><span class="sxs-lookup"><span data-stu-id="be182-158">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="be182-159">예를 들어 다음 코드는 학생 목록에서 모든 선임 학생을 반환 하는 쿼리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="be182-159">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 <span data-ttu-id="be182-160">쿼리 정의는 및에 대 한 인수를 지정 하는 두 개의 람다 식을 사용 하는 다음 예제와 유사한 코드로 컴파일됩니다 `Where` `Select` .</span><span class="sxs-lookup"><span data-stu-id="be182-160">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 <span data-ttu-id="be182-161">각 버전은 루프를 사용 하 여 실행할 수 있습니다 `For Each` .</span><span class="sxs-lookup"><span data-stu-id="be182-161">Either version can be run by using a `For Each` loop:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 <span data-ttu-id="be182-162">자세한 내용은 [람다 식](../../language-features/procedures/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be182-162">For more information, see [Lambda Expressions](../../language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be182-163">추가 정보</span><span class="sxs-lookup"><span data-stu-id="be182-163">See also</span></span>

- [<span data-ttu-id="be182-164">LINQ(Language-Integrated Query)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be182-164">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="be182-165">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="be182-165">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="be182-166">LINQ 및 문자열(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be182-166">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="be182-167">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="be182-167">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="be182-168">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="be182-168">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
