---
title: '#if 전처리기 지시문 - C# 참조'
ms.custom: seodec18
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: 561a628c60888a8d4f3c50c8413784e1ed210599
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036000"
---
# <a name="if-c-reference"></a><span data-ttu-id="993de-102">#if(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="993de-102">#if (C# Reference)</span></span>

<span data-ttu-id="993de-103">C# 컴파일러는 `#if` 지시문과 [#endif](preprocessor-endif.md) 지시문이 차례로 확인되면 지정된 기호가 정의되어 있어야 지시문 사이의 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="993de-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="993de-104">C 및 C++와 달리, 기호에 숫자 값을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="993de-105">C#의 #if 문은 부울이고 기호가 정의되었는지 여부만 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="993de-105">The #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="993de-106">예:</span><span class="sxs-lookup"><span data-stu-id="993de-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="993de-107">[==](../operators/equality-operators.md#equality-operator-)(같음) 및 [!=](../operators/equality-operators.md#inequality-operator-)(같지 않음) 연산자는 [true](../keywords/true-literal.md) 또는 [false](../keywords/false-literal.md)를 테스트할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-107">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for [true](../keywords/true-literal.md) or [false](../keywords/false-literal.md).</span></span> <span data-ttu-id="993de-108">true가 반환되면 기호가 정의된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="993de-108">True means the symbol is defined.</span></span> <span data-ttu-id="993de-109">`#if DEBUG` 문의 의미는 `#if (DEBUG == true)`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="993de-110">[&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-)(및), [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-)(또는), [!](../operators/boolean-logical-operators.md#logical-negation-operator-)(아님)</span><span class="sxs-lookup"><span data-stu-id="993de-110">You can use the operators [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (and), [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (or), and [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span></span> <span data-ttu-id="993de-111">연산자를 사용하면 여러 기호가 정의되었는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-111">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="993de-112">기호와 연산자를 괄호로 묶을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="993de-113">설명</span><span class="sxs-lookup"><span data-stu-id="993de-113">Remarks</span></span>

<span data-ttu-id="993de-114">`#if`를 [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) 및 [#undef](preprocessor-undef.md) 지시문과 함께 사용하면 하나 이상의 기호 유무에 따라 코드를 포함하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="993de-115">따라서 코드를 디버그 빌드용으로 컴파일하거나 특정 구성용으로 컴파일할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="993de-116">`#if` 지시문으로 시작되는 조건부 지시문은 `#endif` 지시문을 사용하여 명시적으로 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="993de-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="993de-117">`#define`을 사용하여 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="993de-118">그러면 `#if` 지시문으로 전달되는 식으로 해당 기호를 사용하는 경우 식이 `true`로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="993de-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="993de-119">[-define](../compiler-options/define-compiler-option.md) 컴파일러 옵션으로 기호를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="993de-120">[#undef](preprocessor-undef.md)로 기호 정의를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="993de-121">`-define` 또는 `#define`으로 정의하는 기호는 동일한 이름의 변수와 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="993de-122">즉, 변수 이름이 전처리기 지시문에 전달되지 않아야 하며 전처리기 지시문을 통해서만 기호를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="993de-123">`#define`을 사용하여 만든 기호의 범위는 해당 기호가 정의된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="993de-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="993de-124">빌드 시스템은 SDK 스타일 프로젝트의 여러 [대상 프레임워크](../../../standard/frameworks.md)를 나타내는 미리 정의된 전처리기 기호도 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="993de-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md) in SDK-style projects.</span></span> <span data-ttu-id="993de-125">둘 이상의 .NET 구현 또는 버전을 대상으로 지정할 수 있는 애플리케이션을 만들 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="993de-125">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> <span data-ttu-id="993de-126">기존 .NET Framework 프로젝트의 경우 프로젝트의 속성 페이지를 통해 Visual Studio의 여러 대상 프레임워크에 대한 조건부 컴파일 기호를 수동으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="993de-126">For traditional .NET Framework projects, you have to manually configure the conditional compilation symbols for the different target frameworks in Visual Studio via the project's properties pages.</span></span>

<span data-ttu-id="993de-127">기타 미리 정의된 기호에는 DEBUG와 TRACE 상수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-127">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="993de-128">`#define`을 사용하여 프로젝트에 설정된 값을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="993de-128">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="993de-129">예를 들어 DEBUG 기호는 빌드 구성 특성(“디버그” 또는 “릴리스” 모드)에 따라 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="993de-129">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="993de-130">예</span><span class="sxs-lookup"><span data-stu-id="993de-130">Examples</span></span>

<span data-ttu-id="993de-131">다음 예제에서는 파일에 MYTEST 기호를 정의한 다음 MYTEST 및 DEBUG 기호의 값을 테스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="993de-131">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="993de-132">이 예제의 출력은 디버그 구성 모드에서 프로젝트를 빌드했는지, 릴리스 구성 모드에서 프로젝트를 빌드했는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="993de-132">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

<span data-ttu-id="993de-133">다음 예제에서는 가능한 경우 새 API를 사용할 수 있도록 여러 대상 프레임워크에 대해 테스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="993de-133">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a><span data-ttu-id="993de-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="993de-134">See also</span></span>

- [<span data-ttu-id="993de-135">C# 참조</span><span class="sxs-lookup"><span data-stu-id="993de-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="993de-136">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="993de-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="993de-137">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="993de-137">C# Preprocessor Directives</span></span>](index.md)
- [<span data-ttu-id="993de-138">방법: 추적 및 디버그를 사용한 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="993de-138">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
