---
title: 예외 만들기 및 Throw - C# 프로그래밍 가이드
description: 예외 만들기 및 throw에 대해 알아봅니다. 예외는 프로그램을 실행하는 동안 오류가 발생했음을 나타내는 데 사용됩니다.
ms.date: 07/20/2015
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: 77a1e8eb4d442e66f8b9ed17a5881661a5990a35
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195495"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="b2acf-104">예외 만들기 및 Throw(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b2acf-104">Creating and Throwing Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="b2acf-105">예외는 프로그램을 실행하는 동안 오류가 발생했음을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-105">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="b2acf-106">오류를 설명하는 예외 개체가 만들어지고 [throw](../../language-reference/keywords/throw.md) 키워드를 통해 *throw*됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-106">Exception objects that describe an error are created and then *thrown* with the [throw](../../language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="b2acf-107">그런 다음 런타임에 가장 호환성이 높은 예외 처리기를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-107">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="b2acf-108">프로그래머는 다음 조건 중 하나 이상에 해당할 경우 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-108">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="b2acf-109">메서드가 정의된 기능을 완료할 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="b2acf-109">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="b2acf-110">예를 들어 메서드에 대한 매개 변수에 잘못된 값이 포함된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-110">For example, if a parameter to a method has an invalid value:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#12)]  
  
- <span data-ttu-id="b2acf-111">개체 상태에 따라 개체에 대한 부적절한 호출이 이루어진 경우.</span><span class="sxs-lookup"><span data-stu-id="b2acf-111">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="b2acf-112">한 가지 예는 읽기 전용 파일에 쓰려고 시도하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-112">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="b2acf-113">개체 상태가 작업을 허용하지 않을 경우 이 클래스의 파생에 따라 <xref:System.InvalidOperationException>의 인스턴스 또는 개체를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-113">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="b2acf-114">다음은 <xref:System.InvalidOperationException> 개체를 throw하는 메서드의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-114">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#13)]  
  
- <span data-ttu-id="b2acf-115">메서드에 대한 인수가 예외를 일으키는 경우.</span><span class="sxs-lookup"><span data-stu-id="b2acf-115">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="b2acf-116">이 경우 원래 예외가 catch되고 <xref:System.ArgumentException> 인스턴스가 만들어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-116">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="b2acf-117">원래 예외를 <xref:System.ArgumentException>의 생성자에 <xref:System.Exception.InnerException%2A> 매개 변수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-117">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#14)]  
  
 <span data-ttu-id="b2acf-118">예외에 이름이 <xref:System.Exception.StackTrace%2A>인 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-118">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="b2acf-119">이 문자열에는 현재 콜 스택에 대한 메서드의 이름과 각 메서드에 대해 예외가 throw된 파일 이름 및 줄 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-119">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="b2acf-120"><xref:System.Exception.StackTrace%2A> 개체는 `throw` 문의 지점에서 CLR(공용 언어 런타임)에 의해 자동으로 만들어지므로 해당 예외는 스택 추적이 시작되는 지점에서 throw되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-120">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="b2acf-121">모든 예외에 이름이 <xref:System.Exception.Message%2A>인 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-121">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="b2acf-122">예외의 이유를 설명하려면 이 문자열을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-122">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="b2acf-123">보안이 중요한 정보는 메시지 텍스트에 넣으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-123">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="b2acf-124"><xref:System.Exception.Message%2A> 외에 <xref:System.ArgumentException>에는 예외를 throw한 인수의 이름으로 설정해야 하는 <xref:System.ArgumentException.ParamName%2A> 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-124">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="b2acf-125">속성 setter의 경우 <xref:System.ArgumentException.ParamName%2A>을 `value`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-125">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="b2acf-126">public 및 protected 메서드는 의도한 함수를 완료할 수 없을 때마다 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-126">Public and protected methods should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="b2acf-127">throw된 예외 클래스는 오류 조건에 맞을 수 있는 가장 구체적인 예외여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-127">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="b2acf-128">이러한 예외는 클래스 기능의 일부로 문서화해야 하고 파생 클래스 또는 원래 클래스의 업데이트는 이전 버전과의 호환성을 위해 같은 동작을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-128">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="b2acf-129">예외를 throw할 때 피해야 하는 작업</span><span class="sxs-lookup"><span data-stu-id="b2acf-129">Things to Avoid When Throwing Exceptions</span></span>  

 <span data-ttu-id="b2acf-130">다음 목록은 예외를 throw할 때 피해야 할 사례를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-130">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
- <span data-ttu-id="b2acf-131">프로그램 흐름을 일반 예외의 일부로 변경하는 데는 예외를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-131">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="b2acf-132">오류 조건을 보고하고 처리하는 데만 예외를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-132">Exceptions should only be used to report and handle error conditions.</span></span>  
  
- <span data-ttu-id="b2acf-133">예외는 throw하는 대신 반환 값 또는 매개 변수로 반환하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-133">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
- <span data-ttu-id="b2acf-134">고유한 소스 코드에서 의도적으로 <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType> 또는 <xref:System.IndexOutOfRangeException?displayProperty=nameWithType>을 throw하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b2acf-134">Do not throw <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType>, or <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> intentionally from your own source code.</span></span>  
  
- <span data-ttu-id="b2acf-135">릴리스 모드가 아닌 디버그 모드에서 throw될 수 있는 예외를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b2acf-135">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="b2acf-136">개발 단계에서 런타임 오류를 식별하려면 대신 디버그 어설션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b2acf-136">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="b2acf-137">예외 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="b2acf-137">Defining Exception Classes</span></span>  

 <span data-ttu-id="b2acf-138">프로그램에서는 <xref:System> 네임스페이스의 미리 정의된 예외 클래스를 throw하거나(이전에 언급한 위치 제외) <xref:System.Exception>에서 파생시켜 자체 예외 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-138">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="b2acf-139">파생 클래스는 매개 변수 없는 생성자, 메시지 속성을 설정하는 생성자, <xref:System.Exception.Message%2A> 및 <xref:System.Exception.InnerException%2A> 속성을 설정하는 생성자 두 개를 포함하여 네 개 이상의 생성자를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-139">The derived classes should define at least four constructors: one parameterless constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="b2acf-140">네 번째 생성자는 예외를 serialize하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-140">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="b2acf-141">새 예외 클래스는 serialize할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-141">New exception classes should be serializable.</span></span> <span data-ttu-id="b2acf-142">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b2acf-142">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#15)]  
  
 <span data-ttu-id="b2acf-143">새로운 속성이 제공하는 데이터가 예외 확인에 유용할 경우에만 해당 속성을 예외 클래스에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-143">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="b2acf-144">새 속성이 파생 예외 클래스에 추가되면 추가된 정보를 반환하기 위해 `ToString()`을 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-144">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b2acf-145">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b2acf-145">C# Language Specification</span></span>  

<span data-ttu-id="b2acf-146">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [예외](~/_csharplang/spec/exceptions.md) 및 [throw 문](~/_csharplang/spec/statements.md#the-throw-statement)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2acf-146">For more information, see [Exceptions](~/_csharplang/spec/exceptions.md) and [The throw statement](~/_csharplang/spec/statements.md#the-throw-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b2acf-147">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2acf-147">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b2acf-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2acf-148">See also</span></span>

- [<span data-ttu-id="b2acf-149">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b2acf-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b2acf-150">예외 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="b2acf-150">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="b2acf-151">예외 계층</span><span class="sxs-lookup"><span data-stu-id="b2acf-151">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
- [<span data-ttu-id="b2acf-152">예외 처리</span><span class="sxs-lookup"><span data-stu-id="b2acf-152">Exception Handling</span></span>](./exception-handling.md)
