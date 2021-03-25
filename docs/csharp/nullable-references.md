---
title: nullable 참조 형식
description: 이 문서에서는 C# 8.0에 추가된 nullable 참조 형식에 대해 간략하게 설명합니다. 이 기능이 신규 및 기존의 프로젝트의 null 참조 예외에 대해 어떻게 안전성을 제공하는지 알아봅니다.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: 36078031eebc1890edf04744475c330c2ba31f96
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480093"
---
# <a name="nullable-reference-types"></a><span data-ttu-id="2ef0d-104">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="2ef0d-104">Nullable reference types</span></span>

<span data-ttu-id="2ef0d-105">C# 8.0에는 참조 형식 변수의 속성에 대한 중요한 설명을 할 수 있는 **nullable 참조 형식** 과 **nullable이 아닌 참조 형식** 이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-105">C# 8.0 introduces **nullable reference types** and **non-nullable reference types** that enable you to make important statements about the properties for reference type variables:</span></span>

- <span data-ttu-id="2ef0d-106">**참조는 null이 아니어야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-106">**A reference isn't supposed to be null**.</span></span> <span data-ttu-id="2ef0d-107">변수에 null이 허용되지 않는 경우 컴파일러는 null이 아닌지 먼저 확인하지 않고 이러한 참조를 역참조하기에 안전한지 확인하는 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-107">When variables aren't supposed to be null, the compiler enforces rules that ensure it's safe to dereference these variables without first checking that it isn't null:</span></span>
  - <span data-ttu-id="2ef0d-108">이 변수는 null이 아닌 값으로 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-108">The variable must be initialized to a non-null value.</span></span>
  - <span data-ttu-id="2ef0d-109">이 변수에는 `null` 값을 절대로 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-109">The variable can never be assigned the value `null`.</span></span>
- <span data-ttu-id="2ef0d-110">**참조에 null이 허용됩니다**.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-110">**A reference may be null**.</span></span> <span data-ttu-id="2ef0d-111">변수에 null이 허용되는 경우 컴파일러는 null 참조 검사를 제대로 했는지 확인하는 다른 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-111">When variables may be null, the compiler enforces different rules to ensure that you've correctly checked for a null reference:</span></span>
  - <span data-ttu-id="2ef0d-112">컴파일러가 해당 값이 null이 아님을 보장할 수 있는 경우에만 변수를 역참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-112">The variable may only be dereferenced when the compiler can guarantee that the value isn't null.</span></span>
  - <span data-ttu-id="2ef0d-113">이러한 변수는 기본 `null` 값으로 초기화할 수 있으며 다른 코드에서 `null` 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-113">These variables may be initialized with the default `null` value and may be assigned the value `null` in other code.</span></span>

<span data-ttu-id="2ef0d-114">이 새로운 기능은 변수 선언에서 설계 의도를 파악할 수 없었던 이전 버전의 C#에 비해 참조 변수 처리에 관한 상당한 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-114">This new feature provides significant benefits over the handling of reference variables in earlier versions of C# where the design intent can't be determined from the variable declaration.</span></span> <span data-ttu-id="2ef0d-115">기존 컴파일러는 참조 형식의 null 참조 예외에 대해 안전성을 제공하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-115">The compiler didn't provide safety against null reference exceptions for reference types:</span></span>

- <span data-ttu-id="2ef0d-116">**참조가 null일 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-116">**A reference can be null**.</span></span> <span data-ttu-id="2ef0d-117">참조 형식 변수가 `null`로 초기화되거나 나중에 `null`이 할당되는 경우 컴파일러는 경고를 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-117">The compiler doesn't issue warnings when a reference-type variable is initialized to `null`, or later assigned `null`.</span></span> <span data-ttu-id="2ef0d-118">컴파일러는 이러한 변수가 null 검사 없이 역참조될 때 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-118">The compiler issues warnings when these variables are dereferenced without null checks.</span></span>
- <span data-ttu-id="2ef0d-119">**참조가 null이 아닌 것으로 간주됩니다**.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-119">**A reference is assumed to be not null**.</span></span> <span data-ttu-id="2ef0d-120">컴파일러는 참조 형식이 역참조될 때 어떠한 경고도 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-120">The compiler doesn't issue any warnings when reference types are dereferenced.</span></span> <span data-ttu-id="2ef0d-121">변수가 null일 수 있는 식으로 설정된 경우 컴파일러에서 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-121">The compiler issues warnings if a variable is set to an expression that may be null.</span></span>

<span data-ttu-id="2ef0d-122">이러한 경고는 컴파일 시에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-122">These warnings are emitted at compile time.</span></span> <span data-ttu-id="2ef0d-123">컴파일러는 null 허용 컨텍스트에 null 검사 또는 다른 런타임 구성을 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-123">The compiler doesn't add any null checks or other runtime constructs in a nullable context.</span></span> <span data-ttu-id="2ef0d-124">런타임 시 null 허용 참조와 null을 허용하지 않는 참조는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-124">At runtime, a nullable reference and a non-nullable reference are equivalent.</span></span>

<span data-ttu-id="2ef0d-125">Nullable 참조 형식을 추가함으로써 의도를 보다 명확하게 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-125">With the addition of nullable reference types, you can declare your intent more clearly.</span></span> <span data-ttu-id="2ef0d-126">`null` 값은 변수가 값을 참조하지 않음을 나타내는 올바른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-126">The `null` value is the correct way to represent that a variable doesn't refer to a value.</span></span> <span data-ttu-id="2ef0d-127">코드에서 모든 `null` 값을 제거하는 데 이 기능을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-127">Don't use this feature to remove all `null` values from your code.</span></span> <span data-ttu-id="2ef0d-128">대신, 컴파일러 및 코드를 읽는 다른 개발자에게 의도를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-128">Rather, you should declare your intent to the compiler and other developers that read your code.</span></span> <span data-ttu-id="2ef0d-129">의도를 선언해 놓으면 컴파일러는 해당 의도와 일치하지 않는 코드 작성 시 이를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-129">By declaring your intent, the compiler informs you when you write code that is inconsistent with that intent.</span></span>

<span data-ttu-id="2ef0d-130">**nullable 참조 형식** 은 [nullable 값 형식](language-reference/builtin-types/nullable-value-types.md)과 동일한 구문을 사용하여 작성합니다. 변수 형식에 `?`가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-130">A **nullable reference type** is noted using the same syntax as [nullable value types](language-reference/builtin-types/nullable-value-types.md): a `?` is appended to the type of the variable.</span></span> <span data-ttu-id="2ef0d-131">예를 들어 다음 변수 선언은 nullable 문자열 변수 `name`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-131">For example, the following variable declaration represents a nullable string variable, `name`:</span></span>

```csharp
string? name;
```

<span data-ttu-id="2ef0d-132">형식 이름에 `?`가 추가되지 않은 모든 변수는 **null을 허용하지 않는 참조 형식** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-132">Any variable where the `?` isn't appended to the type name is a **non-nullable reference type**.</span></span> <span data-ttu-id="2ef0d-133">여기에는 이 기능을 설정한 기존 코드에 있는 모든 참조 형식 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-133">That includes all reference type variables in existing code when you've enabled this feature.</span></span>

<span data-ttu-id="2ef0d-134">컴파일러는 정적 분석을 사용하여 nullable 참조가 null이 아닌 것으로 알려져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-134">The compiler uses static analysis to determine if a nullable reference is known to be non-null.</span></span> <span data-ttu-id="2ef0d-135">컴파일러는 null일 수 있는 nullable 참조를 역참조하는 경우 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-135">The compiler warns you if you dereference a nullable reference when it may be null.</span></span> <span data-ttu-id="2ef0d-136">변수 이름 뒤에 [null 허용 연산자](language-reference/operators/null-forgiving.md) `!`를 사용하여 이 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-136">You can override this behavior by using the [null-forgiving operator](language-reference/operators/null-forgiving.md) `!` following a variable name.</span></span> <span data-ttu-id="2ef0d-137">예를 들어 `name` 변수가 null이 아닌 것으로 알고 있는데 컴파일러 경고가 발생하는 경우 다음 코드를 작성하여 컴파일러 분석을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-137">For example, if you know the `name` variable isn't null but the compiler issues a warning, you can write the following code to override the compiler's analysis:</span></span>

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a><span data-ttu-id="2ef0d-138">형식의 Null 허용 여부</span><span class="sxs-lookup"><span data-stu-id="2ef0d-138">Nullability of types</span></span>

<span data-ttu-id="2ef0d-139">모든 참조 형식은 경고가 생성되는 경우를 설명하는 4가지 *nullabilities(Null 허용 여부)* 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-139">Any reference type can have one of four *nullabilities*, which describes when warnings are generated:</span></span>

- <span data-ttu-id="2ef0d-140">*Nonnullable(Null 허용 안 함)* : 이 형식의 변수에는 null을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-140">*Nonnullable*: Null can't be assigned to variables of this type.</span></span> <span data-ttu-id="2ef0d-141">이 형식의 변수는 역참조되기 전에 null 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-141">Variables of this type don't need to be null-checked before dereferencing.</span></span>
- <span data-ttu-id="2ef0d-142">*Nullable(Null 허용)* : 이 형식의 변수에는 null을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-142">*Nullable*: Null can be assigned to variables of this type.</span></span> <span data-ttu-id="2ef0d-143">`null`에 대한 사전 검사 없이 이 형식의 변수를 역참조하면 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-143">Dereferencing variables of this type without first checking for `null` causes a warning.</span></span>
- <span data-ttu-id="2ef0d-144">*Oblivious(모호한)* : C# 8.0 이전 상태는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-144">*Oblivious*: Oblivious is the pre-C# 8.0 state.</span></span> <span data-ttu-id="2ef0d-145">이 형식의 변수는 경고 없이 역참조되거나 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-145">Variables of this type can be dereferenced or assigned without warnings.</span></span>
- <span data-ttu-id="2ef0d-146">*Unknown(알 수 없음)* : Unknown(알 수 없음)은 형식이 *nullable* 또는 *nonnullable* 이어야 하는지 제약 조건으로 컴파일러에 명시하지 않은 형식 매개 변수에 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-146">*Unknown*: Unknown is generally for type parameters where constraints don't tell the compiler that the type must be *nullable* or *nonnullable*.</span></span>

<span data-ttu-id="2ef0d-147">변수 선언에서 형식의 null 허용 여부는 변수가 선언된 *nullable 컨텍스트* 로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-147">The nullability of a type in a variable declaration is controlled by the *nullable context* in which the variable is declared.</span></span>

## <a name="nullable-contexts"></a><span data-ttu-id="2ef0d-148">Nullable 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="2ef0d-148">Nullable contexts</span></span>

<span data-ttu-id="2ef0d-149">Nullable 컨텍스트를 통해 컴파일러가 참조 형식 변수를 해석하는 방식을 미세하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-149">Nullable contexts enable fine-grained control for how the compiler interprets reference type variables.</span></span> <span data-ttu-id="2ef0d-150">지정된 소스 줄의 **nullable 주석 컨텍스트** 는 enabled 또는 disabled입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-150">The **nullable annotation context** of any given source line is either enabled or disabled.</span></span> <span data-ttu-id="2ef0d-151">C# 8.0 이전 컴파일러는 사용할 수 없는 nullable 컨텍스트에서 모든 코드를 컴파일하는 것으로 생각할 수 있습니다. 모든 참조 형식은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-151">You can think of the pre-C# 8.0 compiler as compiling all your code in a disabled nullable context: any reference type may be null.</span></span> <span data-ttu-id="2ef0d-152">**nullable 경고 컨텍스트** 도 enabled 또는 disabled일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-152">The **nullable warnings context** may also be enabled or disabled.</span></span> <span data-ttu-id="2ef0d-153">nullable 경고 컨텍스트는 컴파일러가 해당 흐름 분석을 사용하여 생성한 경고를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-153">The nullable warnings context specifies the warnings generated by the compiler using its flow analysis.</span></span>

<span data-ttu-id="2ef0d-154">*.csproj* 파일에 `Nullable` 요소를 사용하여 프로젝트에 대한 nullable 주석 컨텍스트 및 nullable 경고 컨텍스트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-154">The nullable annotation context and nullable warning context can be set for a project using the `Nullable` element in your *.csproj* file.</span></span> <span data-ttu-id="2ef0d-155">이 요소는 컴파일러가 형식의 null 허용 여부를 해석하는 방법 및 생성되는 경고를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-155">This element configures how the compiler interprets the nullability of types and what warnings are generated.</span></span> <span data-ttu-id="2ef0d-156">유효한 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-156">Valid settings are:</span></span>

- <span data-ttu-id="2ef0d-157">`enable`: nullable 주석 컨텍스트가 **enabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-157">`enable`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="2ef0d-158">nullable 경고 컨텍스트가 **enabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-158">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="2ef0d-159">예를 들어 참조 형식 변수 `string`은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-159">Variables of a reference type, `string` for example, are non-nullable.</span></span>  <span data-ttu-id="2ef0d-160">모든 null 허용 여부 경고가 enabled입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-160">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="2ef0d-161">`warnings`: nullable 주석 컨텍스트가 **disabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-161">`warnings`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="2ef0d-162">nullable 경고 컨텍스트가 **enabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-162">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="2ef0d-163">참조 형식의 변수가 모호합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-163">Variables of a reference type are oblivious.</span></span> <span data-ttu-id="2ef0d-164">모든 null 허용 여부 경고가 enabled입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-164">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="2ef0d-165">`annotations`: nullable 주석 컨텍스트가 **enabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-165">`annotations`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="2ef0d-166">nullable 경고 컨텍스트가 **disabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-166">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="2ef0d-167">참조 형식의 변수(예: 문자열)는 null을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-167">Variables of a reference type, string for example, are non-nullable.</span></span> <span data-ttu-id="2ef0d-168">모든 null 허용 여부 경고가 disabled입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-168">All nullability warnings are disabled.</span></span>
- <span data-ttu-id="2ef0d-169">`disable`: nullable 주석 컨텍스트가 **disabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-169">`disable`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="2ef0d-170">nullable 경고 컨텍스트가 **disabled** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-170">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="2ef0d-171">참조 형식의 변수는 이전 버전의 C#과 마찬가지로 모호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-171">Variables of a reference type are oblivious, just like earlier versions of C#.</span></span> <span data-ttu-id="2ef0d-172">모든 null 허용 여부 경고가 disabled입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-172">All nullability warnings are disabled.</span></span>

<span data-ttu-id="2ef0d-173">**예제**:</span><span class="sxs-lookup"><span data-stu-id="2ef0d-173">**Example**:</span></span>

```xml
<Nullable>enable</Nullable>
```

<span data-ttu-id="2ef0d-174">또한 지시문을 사용하여 프로젝트의 아무 곳에나 이러한 동일한 컨텍스트를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-174">You can also use directives to set these same contexts anywhere in your project:</span></span>

- <span data-ttu-id="2ef0d-175">`#nullable enable`: nullable 주석 컨텍스트와 nullable 경고 컨텍스트를 **enabled** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-175">`#nullable enable`: Sets the nullable annotation context and nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="2ef0d-176">`#nullable disable`: nullable 주석 컨텍스트와 nullable 경고 컨텍스트를 **disabled** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-176">`#nullable disable`: Sets the nullable annotation context and nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="2ef0d-177">`#nullable restore`: nullable 주석 컨텍스트와 nullable 경고 컨텍스트를 프로젝트 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-177">`#nullable restore`: Restores the nullable annotation context and nullable warning context to the project settings.</span></span>
- <span data-ttu-id="2ef0d-178">`#nullable disable warnings`: nullable 경고 컨텍스트를 **disabled** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-178">`#nullable disable warnings`: Set the nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="2ef0d-179">`#nullable enable warnings`: nullable 경고 컨텍스트를 **enabled** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-179">`#nullable enable warnings`: Set the nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="2ef0d-180">`#nullable restore warnings`: nullable 경고 컨텍스트를 프로젝트 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-180">`#nullable restore warnings`: Restores the nullable warning context to the project settings.</span></span>
- <span data-ttu-id="2ef0d-181">`#nullable disable annotations`: nullable 주석 컨텍스트를 **disabled** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-181">`#nullable disable annotations`: Set the nullable annotation context to **disabled**.</span></span>
- <span data-ttu-id="2ef0d-182">`#nullable enable annotations`: nullable 주석 컨텍스트를 **enabled** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-182">`#nullable enable annotations`: Set the nullable annotation context to **enabled**.</span></span>
- <span data-ttu-id="2ef0d-183">`#nullable restore annotations`: 주석 경고 컨텍스트를 프로젝트 설정으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-183">`#nullable restore annotations`: Restores the annotation warning context to the project settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ef0d-184">전역 null 허용 컨텍스트는 생성된 코드 파일에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-184">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="2ef0d-185">두 전략에서 null 허용 컨텍스트는 생성됨으로 표시된 모든 소스 파일에 대해 *disabled* 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-185">Under either strategy, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="2ef0d-186">즉, 생성된 파일의 API가 주석 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-186">This means any APIs in generated files are not annotated.</span></span> <span data-ttu-id="2ef0d-187">다음 네 가지 방법으로 파일은 생성됨으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-187">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="2ef0d-188">.editorconfig에서 해당 파일에 적용되는 섹션에 `generated_code = true`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-188">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="2ef0d-189">파일의 맨 위에 있는 주석에 `<auto-generated>` 또는 `<auto-generated/>`를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-189">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="2ef0d-190">해당 주석의 모든 줄에 넣을 수 있지만 주석 블록은 파일의 첫 번째 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-190">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="2ef0d-191">파일 이름을 *TemporaryGeneratedFile_* 로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-191">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="2ef0d-192">파일 이름을 *.designer.cs*, *.generated.cs*, *.g.cs* 또는 *.g.i.cs* 로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-192">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="2ef0d-193">생성기는 [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) 전처리기 지시문을 사용하여 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-193">Generators can opt-in using the [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

<span data-ttu-id="2ef0d-194">기본적으로 null 허용 주석 및 경고 컨텍스트는 새 프로젝트를 포함하여 **사용 안 함** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-194">By default, nullable annotation and warning contexts are **disabled**, including new projects.</span></span> <span data-ttu-id="2ef0d-195">이는 기존 코드가 변경 없이 새로운 경고를 생성하지 않고 컴파일됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-195">That means that your existing code compiles without changes and without generating any new warnings.</span></span>

<span data-ttu-id="2ef0d-196">이러한 옵션은 null 허용 참조 형식을 사용하도록 [기존 코드베이스를 업데이트](nullable-migration-strategies.md)하는 두 가지 고유한 전략을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-196">These options provide two distinct strategies to [update an existing codebase](nullable-migration-strategies.md) to use nullable reference types.</span></span>

## <a name="nullable-annotation-context"></a><span data-ttu-id="2ef0d-197">nullable 주석 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="2ef0d-197">Nullable annotation context</span></span>

<span data-ttu-id="2ef0d-198">컴파일러는 disabled nullable 주석 컨텍스트에 다음 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-198">The compiler uses the following rules in a disabled nullable annotation context:</span></span>

- <span data-ttu-id="2ef0d-199">disabled 컨텍스트에서 nullable 참조를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-199">You can't declare nullable references in a disabled context.</span></span>
- <span data-ttu-id="2ef0d-200">모든 참조 변수에는 null 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-200">All reference variables may be assigned a value of null.</span></span>
- <span data-ttu-id="2ef0d-201">참조 형식의 변수가 역참조되면 경고가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-201">No warnings are generated when a variable of a reference type is dereferenced.</span></span>
- <span data-ttu-id="2ef0d-202">disabled 컨텍스트에는 null 허용 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-202">The null-forgiving operator may not be used in a disabled context.</span></span>

<span data-ttu-id="2ef0d-203">동작은 이전 버전의 C#과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-203">The behavior is the same as previous versions of C#.</span></span>

<span data-ttu-id="2ef0d-204">컴파일러는 enabled nullable 주석 컨텍스트에 다음 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-204">The compiler uses the following rules in an enabled nullable annotation context:</span></span>

- <span data-ttu-id="2ef0d-205">모든 참조 형식의 변수는 **nullable이 아닌 참조** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-205">Any variable of a reference type is a **non-nullable reference**.</span></span>
- <span data-ttu-id="2ef0d-206">nullable이 아닌 모든 참조는 안전하게 역참조될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-206">Any non-nullable reference may be dereferenced safely.</span></span>
- <span data-ttu-id="2ef0d-207">모든 nullable 참조 형식(변수 선언에서 형식 뒤에 `?` 표시)은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-207">Any nullable reference type (noted by `?` after the type in the variable declaration) may be null.</span></span> <span data-ttu-id="2ef0d-208">정적 분석은 값이 역참조될 때 null이 아닌 것으로 알려져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-208">Static analysis determines if the value is known to be non-null when it's dereferenced.</span></span> <span data-ttu-id="2ef0d-209">아닌 경우 컴파일러가 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-209">If not, the compiler warns you.</span></span>
- <span data-ttu-id="2ef0d-210">null 허용 연산자를 사용하여 nullable 참조가 null이 아님을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-210">You can use the null-forgiving operator to declare that a nullable reference isn't null.</span></span>

<span data-ttu-id="2ef0d-211">enabled nullable 주석 컨텍스트에서 참조 형식에 추가된 `?` 문자는 **nullable 참조 형식** 을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-211">In an enabled nullable annotation context, the `?` character appended to a reference type declares a **nullable reference type**.</span></span> <span data-ttu-id="2ef0d-212">**null 비허용 연산자** `!`를 식 뒤에 추가하여 식이 null이 아님을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-212">The **null-forgiving operator** `!` may be appended to an expression to declare that the expression isn't null.</span></span>

## <a name="nullable-warning-context"></a><span data-ttu-id="2ef0d-213">Nullable 경고 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="2ef0d-213">Nullable warning context</span></span>

<span data-ttu-id="2ef0d-214">nullable 경고 컨텍스트는 nullable 주석 컨텍스트와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-214">The nullable warning context is distinct from the nullable annotation context.</span></span> <span data-ttu-id="2ef0d-215">새 주석이 해제(disabled)되어도 경고는 설정(enabled)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-215">Warnings can be enabled even when the new annotations are disabled.</span></span> <span data-ttu-id="2ef0d-216">컴파일러는 정적 흐름 분석을 사용하여 모든 참조에 대한 **null 상태** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-216">The compiler uses static flow analysis to determine the **null state** of any reference.</span></span> <span data-ttu-id="2ef0d-217">null 상태는 *nullable 경고 컨텍스트* 가 **disabled** 가 아닌 경우 **null이 아님** 또는 **null일 수 있음** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-217">The null state is either **not null** or **maybe null** when the *nullable warning context* isn't **disabled**.</span></span> <span data-ttu-id="2ef0d-218">컴파일러가 **null일 수 있음** 으로 확인한 경우 역참조하면 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-218">If you dereference a reference when the compiler has determined it's **maybe null**, the compiler warns you.</span></span> <span data-ttu-id="2ef0d-219">참조 상태는 컴파일러가 다음 두 조건 중 하나를 확인할 수 없으면 **null일 수 있음** 입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-219">The state of a reference is **maybe null** unless the compiler can determine one of two conditions:</span></span>

1. <span data-ttu-id="2ef0d-220">변수에 null이 아닌 값이 명확하게 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-220">The variable has been definitely assigned a non-null value.</span></span>
1. <span data-ttu-id="2ef0d-221">변수 또는 식이 역참조되기 전에 null 검사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-221">The variable or expression has been checked against null before de-referencing it.</span></span>

<span data-ttu-id="2ef0d-222">컴파일러는 nullable 경고 컨텍스트에서 **null일 수 있는** 변수 또는 식을 역참조할 때 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-222">The compiler generates warnings when you dereference a variable or expression that is **maybe null** in a nullable warning context.</span></span> <span data-ttu-id="2ef0d-223">또한 컴파일러는 활성화된 null 허용 주석 컨텍스트에서 null을 허용하지 않는 참조 형식에 **null일 수 있음** 변수 또는 식이 할당되면 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-223">Furthermore, the compiler generates warnings when a nonnullable reference-type variable is assigned a **maybe null** variable or expression in an enabled nullable annotation context.</span></span>

## <a name="attributes-describe-apis"></a><span data-ttu-id="2ef0d-224">API를 설명하는 특성</span><span class="sxs-lookup"><span data-stu-id="2ef0d-224">Attributes describe APIs</span></span>

<span data-ttu-id="2ef0d-225">인수 또는 반환 값이 null일 수 있거나 null이 될 수 없는 경우에 대한 자세한 정보를 컴파일러에 제공하는 API에 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-225">You add attributes to APIs that provide the compiler more information about when arguments or return values can or can't be null.</span></span> <span data-ttu-id="2ef0d-226">[null 허용 특성](language-reference/attributes/nullable-analysis.md)을 다루는 언어 참조의 문서에서 이러한 특성에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-226">You can learn more about these attributes in our article in the language reference covering the [nullable attributes](language-reference/attributes/nullable-analysis.md).</span></span> <span data-ttu-id="2ef0d-227">이러한 특성은 현재 및 이후 릴리스에서 .NET 라이브러리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-227">These attributes are being added to .NET libraries over current and upcoming releases.</span></span> <span data-ttu-id="2ef0d-228">가장 일반적으로 사용되는 API가 먼저 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-228">The most commonly used APIs are being updated first.</span></span>

## <a name="known-pitfalls"></a><span data-ttu-id="2ef0d-229">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="2ef0d-229">Known pitfalls</span></span>

<span data-ttu-id="2ef0d-230">참조 유형을 포함하는 배열 및 구조체는 nullable 참조 형식 기능의 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-230">Arrays and structs that contain reference types are known pitfalls in nullable reference types feature.</span></span>

### <a name="structs"></a><span data-ttu-id="2ef0d-231">구조체</span><span class="sxs-lookup"><span data-stu-id="2ef0d-231">Structs</span></span>

<span data-ttu-id="2ef0d-232">null을 허용하지 않는 참조 형식을 포함하는 구조에서는 경고 없이 `default`를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-232">A struct that contains non-nullable reference types allows assigning `default` for it without any warnings.</span></span> <span data-ttu-id="2ef0d-233">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-233">Consider the following example:</span></span>

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

<span data-ttu-id="2ef0d-234">앞의 예제에서 null을 허용하지 않는 참조 형식 `FirstName` 및 `LastName`이 null인 동안 `PrintStudent(default)`에는 경고가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-234">In the preceding example, there is no warning in `PrintStudent(default)` while the non-nullable reference types `FirstName` and `LastName` are null.</span></span>

<span data-ttu-id="2ef0d-235">또 다른 일반적인 사례는 일반 구조체를 처리하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-235">Another more common case is when you deal with generic structs.</span></span> <span data-ttu-id="2ef0d-236">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-236">Consider the following example:</span></span>

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

<span data-ttu-id="2ef0d-237">앞의 예제에서 `Bar` 속성은 런타임 시 `null`이 되고 경고 없이 null을 허용하지 않는 문자열에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-237">In the preceding example, the property `Bar` is going to be `null` at runtime, and it's assigned to non-nullable string without any warnings.</span></span>

### <a name="arrays"></a><span data-ttu-id="2ef0d-238">배열</span><span class="sxs-lookup"><span data-stu-id="2ef0d-238">Arrays</span></span>

<span data-ttu-id="2ef0d-239">배열은 nullable 참조 형식의 알려진 문제가 되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-239">Arrays are also a known pitfall in nullable reference types.</span></span> <span data-ttu-id="2ef0d-240">경고를 생성하지 않는 다음 예제를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-240">Consider the following example which doesn't produce any warnings:</span></span>

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

<span data-ttu-id="2ef0d-241">앞의 예제에서 배열 선언은 해당 요소가 모두 null로 초기화되는 동안 null을 허용하지 않는 문자열을 보유함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-241">In the preceding example, the declaration of the array shows it holds non-nullable strings, while its elements are all initialized to null.</span></span> <span data-ttu-id="2ef0d-242">그런 다음, `s` 변수에는 null 값(배열의 첫 번째 요소)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-242">Then, the variable `s` is assigned a null value (the first element of the array).</span></span> <span data-ttu-id="2ef0d-243">마지막으로 `s` 변수가 역참조되어 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef0d-243">Finally, the variable `s` is dereferenced causing a runtime exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef0d-244">참조</span><span class="sxs-lookup"><span data-stu-id="2ef0d-244">See also</span></span>

- [<span data-ttu-id="2ef0d-245">Nullable 참조 형식 사양 초안</span><span class="sxs-lookup"><span data-stu-id="2ef0d-245">Draft nullable reference types specification</span></span>](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)
- [<span data-ttu-id="2ef0d-246">Nullable 참조 소개 자습서</span><span class="sxs-lookup"><span data-stu-id="2ef0d-246">Intro to nullable references tutorial</span></span>](tutorials/nullable-reference-types.md)
- [<span data-ttu-id="2ef0d-247">기존 코드베이스를 nullable 참조로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2ef0d-247">Migrate an existing codebase to nullable references</span></span>](tutorials/upgrade-to-nullable-references.md)
- [<span data-ttu-id="2ef0d-248">**Null 허용**(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="2ef0d-248">**Nullable** (C# Compiler option)</span></span>](language-reference/compiler-options/language.md#nullable)
