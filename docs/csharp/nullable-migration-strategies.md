---
title: Nullable 참조 형식을 사용하기 위한 코드베이스 업데이트
description: Nullable 참조 형식을 사용하기 위해 코드베이스를 업그레이드하는 최고의 전략을 선택합니다.
ms.technology: csharp-null-safety
ms.date: 07/31/2019
ms.openlocfilehash: ab0970247c7e3f3c20d7fdb40ef035c4ba1d8b01
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "97866825"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a><span data-ttu-id="3a223-103">Nullable 참조 형식을 사용하기 위해 라이브러리를 업데이트하고 호출자에 nullable 규칙 전달</span><span class="sxs-lookup"><span data-stu-id="3a223-103">Update libraries to use nullable reference types and communicate nullable rules to callers</span></span>

<span data-ttu-id="3a223-104">[Nullable 참조 형식](nullable-references.md)를 추가하면 모든 변수에 `null` 값이 허용되거나 필요한지를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-104">The addition of [nullable reference types](nullable-references.md) means you can declare whether or not a `null` value is allowed or expected for every variable.</span></span> <span data-ttu-id="3a223-105">또한 `AllowNull`, `DisallowNull`, `MaybeNull`, `NotNull`, `NotNullWhen`, `MaybeNullWhen`, `NotNullIfNotNull` 등의 여러 특성을 적용하여 인수와 반환 값의 null 상태를 완전히 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-105">In addition, you can apply a number of attributes: `AllowNull`, `DisallowNull`, `MaybeNull`, `NotNull`, `NotNullWhen`, `MaybeNullWhen`, and `NotNullIfNotNull` to completely describe the null states of argument and return values.</span></span> <span data-ttu-id="3a223-106">따라서 코드를 작성할 때 뛰어난 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-106">That provides a great experience as you write code.</span></span> <span data-ttu-id="3a223-107">Null을 허용하지 않는 변수를 `null`로 설정할 수 있으면 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-107">You get warnings if a non-nullable variable might be set to `null`.</span></span> <span data-ttu-id="3a223-108">Nullable 변수를 역참조하기 전에 null 검사하지 않은 경우 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-108">You get warnings if a nullable variable isn't null-checked before you dereference it.</span></span> <span data-ttu-id="3a223-109">라이브러리 업데이트는 시간이 걸릴 수 있지만 얻는 결과를 보면 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-109">Updating your libraries can take time, but the payoffs are worth it.</span></span> <span data-ttu-id="3a223-110">컴파일러에 `null` 값이 허용되거나 금지되는 ‘경우’에 관해 더 많은 정보를 제공하면 API 사용자에게 더 유용한 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-110">The more information you provide to the compiler about *when* a `null` value is allowed or prohibited, the better warnings users of your API will get.</span></span> <span data-ttu-id="3a223-111">친숙한 예제부터 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-111">Let's start with a familiar example.</span></span> <span data-ttu-id="3a223-112">라이브러리에 리소스 문자열을 검색하는 다음 API가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-112">Imagine your library has the following API to retrieve a resource string:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="3a223-113">앞의 예제는 .NET의 친숙한 `Try*` 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-113">The preceding example follows the familiar `Try*` pattern in .NET.</span></span> <span data-ttu-id="3a223-114">이 API에 대한 두 개의 참조 인수인 `key` 및 `message` 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-114">There are two reference arguments for this API: the `key` and the `message` parameter.</span></span> <span data-ttu-id="3a223-115">이 API에는 해당 인수의 nullness에 관련된 다음 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-115">This API has the following rules relating to the nullness of these arguments:</span></span>

- <span data-ttu-id="3a223-116">호출자는 `null`을 `key`의 인수로 전달하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-116">Callers shouldn't pass `null` as the argument for `key`.</span></span>
- <span data-ttu-id="3a223-117">호출자는 값이 `null`인 변수를 `message`의 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-117">Callers can pass a variable whose value is `null` as the argument for `message`.</span></span>
- <span data-ttu-id="3a223-118">`TryGetMessage` 메서드가 `true`를 반환하면 `message` 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-118">If the `TryGetMessage` method returns `true`, the value of `message` isn't null.</span></span> <span data-ttu-id="3a223-119">반환 값이 `false,`이면 `message`의 값과 해당 null 상태는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-119">If the return value is `false,` the value of `message` (and its null state) is null.</span></span>

<span data-ttu-id="3a223-120">`key`에 대한 규칙은 변수 형식으로 완전히 표현될 수 있습니다. `key`는 null을 허용하지 않는 참조 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-120">The rule for `key` can be completely expressed by the variable type: `key` should be a non-nullable reference type.</span></span> <span data-ttu-id="3a223-121">`message` 매개 변수는 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-121">The `message` parameter is more complex.</span></span> <span data-ttu-id="3a223-122">`null`을 인수로 허용하지만, 성공 시 해당 `out` 인수가 null이 아님을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-122">It allows `null` as the argument, but guarantees that, on success, that `out` argument isn't null.</span></span> <span data-ttu-id="3a223-123">이 시나리오의 경우 기대치를 설명하는 더 다양한 어휘가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-123">For these scenarios, you need a richer vocabulary to describe the expectations.</span></span>

<span data-ttu-id="3a223-124">Nullable 참조를 위해 라이브러리를 업데이트하려면 일부 변수 및 형식 이름에 `?`를 포함하는 것 이상의 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-124">Updating your library for nullable references requires more than sprinkling `?` on some of the variables and type names.</span></span> <span data-ttu-id="3a223-125">앞의 예제에서는 API를 검토하고 각 입력 인수의 기대 사항을 고려해야 함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-125">The preceding example shows that you need to examine your APIs and consider your expectations for each input argument.</span></span> <span data-ttu-id="3a223-126">반환 값의 보장과 메서드 반환의 `out` 또는 `ref` 인수를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-126">Consider the guarantees for the return value, and any `out` or `ref` arguments upon the method's return.</span></span> <span data-ttu-id="3a223-127">그런 다음 해당 규칙을 컴파일러에 전달하면 컴파일러에서 호출자가 해당 규칙을 준수하지 않는 경우 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-127">Then communicate those rules to the compiler, and the compiler will provide warnings when callers don't abide by those rules.</span></span>

<span data-ttu-id="3a223-128">이 작업에는 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-128">This work takes time.</span></span> <span data-ttu-id="3a223-129">우선 라이브러리나 애플리케이션에서 nullable을 인식하도록 하면서 다른 요구 사항도 적절하게 충족하는 전략을 따르겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-129">Let's start with strategies to make your library or application nullable-aware, while balancing other requirements.</span></span> <span data-ttu-id="3a223-130">진행 중인 개발을 균형 있게 조정하여 nullable 참조 형식을 사용하도록 설정하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-130">You'll see how to balance ongoing development enabling nullable reference types.</span></span> <span data-ttu-id="3a223-131">제네릭 형식 정의의 문제를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-131">You'll learn challenges for generic type definitions.</span></span> <span data-ttu-id="3a223-132">개별 API의 사전 및 사후 조건을 설명하는 특성을 적용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-132">You'll learn to apply attributes to describe pre- and post-conditions on individual APIs.</span></span>

## <a name="choose-a-strategy-for-nullable-reference-types"></a><span data-ttu-id="3a223-133">nullable 참조 형식을 위한 전략 선택</span><span class="sxs-lookup"><span data-stu-id="3a223-133">Choose a strategy for nullable reference types</span></span>

<span data-ttu-id="3a223-134">우선 nullable 참조 형식을 기본적으로 설정하거나 해제할지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-134">The first choice is whether nullable reference types should be on or off by default.</span></span> <span data-ttu-id="3a223-135">두 가지 전략이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-135">You have two strategies:</span></span>

- <span data-ttu-id="3a223-136">전체 프로젝트에서는 nullable 참조 형식을 사용하도록 설정하고 준비되지 않은 코드에서는 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-136">Enable nullable reference types for the entire project, and disable it in code that's not ready.</span></span>
- <span data-ttu-id="3a223-137">Nullable 참조 형식에 대한 주석이 추가된 코드에만 nullable 참조 형식을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-137">Only enable nullable reference types for code that's been annotated for nullable reference types.</span></span>

<span data-ttu-id="3a223-138">첫 번째 전략은 nullable 참조 형식을 위해 라이브러리를 업데이트할 때 라이브러리에 다른 기능을 추가하는 경우에 가장 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-138">The first strategy works best when you're adding other features to the library as you update it for nullable reference types.</span></span> <span data-ttu-id="3a223-139">새로 개발하는 코드는 모두 nullable을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-139">All new development is nullable aware.</span></span> <span data-ttu-id="3a223-140">기존 코드를 업데이트할 때는 해당 클래스에서 nullable 참조 형식을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-140">As you update existing code, you enable nullable reference types in those classes.</span></span>

<span data-ttu-id="3a223-141">이 첫 번째 전략을 따르면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-141">Following this first strategy, you do the following steps:</span></span>

1. <span data-ttu-id="3a223-142">*.csproj* 파일에 `<Nullable>enable</Nullable>` 요소를 추가하여 전체 프로젝트에서 nullable 참조 형식을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-142">Enable nullable reference types for the entire project by adding the `<Nullable>enable</Nullable>` element to your *csproj* files.</span></span>
1. <span data-ttu-id="3a223-143">프로젝트의 모든 소스 파일에 `#nullable disable` pragma를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-143">Add the `#nullable disable` pragma to every source file in your project.</span></span>
1. <span data-ttu-id="3a223-144">각 파일을 작업할 때 pragma를 제거하고 경고가 있으면 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-144">As you work on each file, remove the pragma and address any warnings.</span></span>

<span data-ttu-id="3a223-145">이 첫 번째 전략은 모든 파일에 pragma를 추가하는 사전 작업이 더 많이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-145">This first strategy has more up-front work to add the pragma to every file.</span></span> <span data-ttu-id="3a223-146">장점이라면 프로젝트에 추가되는 모든 새 코드 파일에서 nullable을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-146">The advantage is that every new code file added to the project will be nullable enabled.</span></span> <span data-ttu-id="3a223-147">모든 새 작업은 nullable 인식이므로 기존 코드만 업데이트만 업데이트하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-147">Any new work will be nullable aware; only existing code must be updated.</span></span>

<span data-ttu-id="3a223-148">두 번째 전략은 라이브러리가 안정적이며 개발에서 주로 nullable 참조 형식을 채택하는 데 중점을 두는 경우에 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-148">The second strategy works better if the library is stable, and the main focus of the development is to adopt nullable reference types.</span></span> <span data-ttu-id="3a223-149">API에 주석을 달 때 nullable 참조 형식을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-149">You turn on nullable reference types as you annotate APIs.</span></span> <span data-ttu-id="3a223-150">마쳤으면 전체 프로젝트에 대해 nullable 참조 형식을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-150">When you've finished, you enable nullable reference types for the entire project.</span></span>

<span data-ttu-id="3a223-151">이 두 번째 전략을 따르면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-151">Following this second strategy you do the following steps:</span></span>

1. <span data-ttu-id="3a223-152">Nullable을 인식하도록 할 파일에 `#nullable enable` pragma를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-152">Add the `#nullable enable` pragma to the file you want to make nullable aware.</span></span>
1. <span data-ttu-id="3a223-153">경고가 표시되면 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-153">Address any warnings.</span></span>
1. <span data-ttu-id="3a223-154">전체 라이브러리가 nullable을 인식하도록 지정될 때까지 처음 두 단계를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-154">Continue these first two steps until you've made the entire library nullable aware.</span></span>
1. <span data-ttu-id="3a223-155">*.csproj* 파일에 `<Nullable>enable</Nullable>` 요소를 추가하여 전체 프로젝트에서 nullable 형식을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-155">Enable nullable types for the entire project by adding the `<Nullable>enable</Nullable>` element to your *csproj* files.</span></span>
1. <span data-ttu-id="3a223-156">더 이상 필요하지 않으므로 `#nullable enable` pragma를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-156">Remove the `#nullable enable` pragmas, as they're no longer needed.</span></span>

<span data-ttu-id="3a223-157">이 두 번째 전략은 사전 작업이 덜 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-157">This second strategy has less work up-front.</span></span> <span data-ttu-id="3a223-158">단점이라면 새 파일을 만들 때 첫 번째 작업으로 pragma를 추가하고 여기에서 nullable을 인식하도록 설정해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-158">The tradeoff is that the first task when you create a new file is to add the pragma and make it nullable aware.</span></span> <span data-ttu-id="3a223-159">팀의 개발자가 위 작업을 잊는 경우 새 코드가 이제 작업의 백로그에 있게 되어 모든 코드에서 nullable을 인식하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-159">If any developers on your team forget, that new code is now in the backlog of work to make all code nullable aware.</span></span>

<span data-ttu-id="3a223-160">어떤 전략을 선택할지는 프로젝트에서 수행 중인 활성 개발이 얼마나 많은지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-160">Which of these strategies you pick depends on how much active development is taking place in your project.</span></span> <span data-ttu-id="3a223-161">프로젝트의 완성도와 안정도가 높아질수록 두 번째 전략이 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-161">The more mature and stable your project, the better the second strategy.</span></span> <span data-ttu-id="3a223-162">개발 중인 기능이 많을수록 첫 번째 전략이 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-162">The more features being developed, the better the first strategy.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a223-163">전역 null 허용 컨텍스트는 생성된 코드 파일에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-163">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="3a223-164">두 전략에서 null 허용 컨텍스트는 생성됨으로 표시된 모든 소스 파일에 대해 *disabled* 입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-164">Under either strategy, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="3a223-165">즉, 생성된 파일의 API가 주석 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-165">This means any APIs in generated files are not annotated.</span></span> <span data-ttu-id="3a223-166">다음 네 가지 방법으로 파일은 생성됨으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-166">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="3a223-167">.editorconfig에서 해당 파일에 적용되는 섹션에 `generated_code = true`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-167">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="3a223-168">파일의 맨 위에 있는 주석에 `<auto-generated>` 또는 `<auto-generated/>`를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-168">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="3a223-169">해당 주석의 모든 줄에 넣을 수 있지만 주석 블록은 파일의 첫 번째 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-169">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="3a223-170">파일 이름을 *TemporaryGeneratedFile_* 로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-170">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="3a223-171">파일 이름을 *.designer.cs*, *.generated.cs*, *.g.cs* 또는 *.g.i.cs* 로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-171">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="3a223-172">생성기는 [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) 전처리기 지시문을 사용하여 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-172">Generators can opt-in using the [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

## <a name="should-nullable-warnings-introduce-breaking-changes"></a><span data-ttu-id="3a223-173">Nullable 경고에서 호환성이 손상되는 변경을 도입해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="3a223-173">Should nullable warnings introduce breaking changes?</span></span>

<span data-ttu-id="3a223-174">Nullable 참조 형식을 사용하도록 설정하기 전에 변수는 ‘nullable 인식 불가능’으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-174">Before you enable nullable reference types, variables are considered *nullable oblivious*.</span></span> <span data-ttu-id="3a223-175">Nullable 참조 형식을 사용하도록 설정하면 해당 변수는 모두 ‘null을 허용하지 않습니다’.</span><span class="sxs-lookup"><span data-stu-id="3a223-175">Once you enable nullable reference types, all those variables are *non-nullable*.</span></span> <span data-ttu-id="3a223-176">컴파일러에서는 해당 변수가 null이 아닌 값으로 초기화되지 않은 경우 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-176">The compiler will issue warnings if those variables aren't initialized to non-null values.</span></span>

<span data-ttu-id="3a223-177">또한 값이 초기화되지 않은 경우의 반환 값 때문에도 경고가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-177">Another likely source of warnings is return values when the value hasn't been initialized.</span></span>

<span data-ttu-id="3a223-178">컴파일러 경고를 해결하는 첫 번째 단계는 매개 변수와 반환 형식에 `?` 주석을 사용하여 인수나 반환 값이 null일 수 있는 경우를 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-178">The first step in addressing the compiler warnings is to use `?` annotations on parameter and return types to indicate when arguments or return values may be null.</span></span> <span data-ttu-id="3a223-179">참조 변수가 null이 될 수 없는 경우 원래 선언이 올바릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-179">When reference variables must not be null, the original declaration is correct.</span></span> <span data-ttu-id="3a223-180">이 작업을 수행할 때 목표는 경고를 해결하는 것만이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-180">As you do this task, your goal isn't just to fix warnings.</span></span> <span data-ttu-id="3a223-181">무엇보다 컴파일러에서 잠재적 null 값을 사용하는 사용자의 의도로 이해하게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-181">The more important goal is to make the compiler understand your intent for potential null values.</span></span> <span data-ttu-id="3a223-182">경고를 검토할 때 라이브러리와 관련하여 다음으로 중요한 결정을 내리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-182">As you examine the warnings, you reach your next major decision for your library.</span></span> <span data-ttu-id="3a223-183">디자인 의도를 더 명확하게 전달하기 위해 API 시그니처를 수정하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="3a223-183">Do you want to consider modifying API signatures to more clearly communicate your design intent?</span></span> <span data-ttu-id="3a223-184">이전에 살펴본 `TryGetMessage` 메서드를 위한 더 나은 API 시그니처는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-184">A better API signature for the `TryGetMessage` method examined earlier could be:</span></span>

```csharp
string? TryGetMessage(string key);
```

<span data-ttu-id="3a223-185">반환 값은 성공이나 실패를 나타내며 값을 찾은 경우 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-185">The return value indicates success or failure, and carries the value if the value was found.</span></span> <span data-ttu-id="3a223-186">대부분의 경우 API 시그니처를 변경하면 null 값이 전달되는 방식이 개선될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-186">In many cases, changing API signatures can improve how they communicate null values.</span></span>

<span data-ttu-id="3a223-187">그러나 퍼블릭 라이브러리나 사용자 기반이 대규모인 라이브러리의 경우 API 시그니처 변경을 도입하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-187">However, for public libraries, or libraries with large user bases, you may prefer not introducing any API signature changes.</span></span> <span data-ttu-id="3a223-188">해당 사례와 기타 일반적인 패턴의 경우 특성을 적용하여 인수나 반환 값이 `null`일 수 있는 경우를 더 명확히 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-188">For those cases, and other common patterns, you can apply attributes to more clearly define when an argument or return value may be `null`.</span></span> <span data-ttu-id="3a223-189">API의 표면 변경을 고려할지 여부와 관계없이 형식 주석만으로는 인수나 반환 값의 `null` 값을 설명하는 데 충분하지 않을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-189">Whether or not you consider changing the surface of your API, you'll likely find that type annotations alone aren't sufficient for describing `null` values for arguments or return values.</span></span> <span data-ttu-id="3a223-190">해당 경우 특성을 적용하여 API를 더 명확하게 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-190">In those instances, you can apply attributes to more clearly describe an API.</span></span>

## <a name="attributes-extend-type-annotations"></a><span data-ttu-id="3a223-191">특성을 통한 형식 주석 확장</span><span class="sxs-lookup"><span data-stu-id="3a223-191">Attributes extend type annotations</span></span>

<span data-ttu-id="3a223-192">변수의 null 상태에 대한 추가 정보를 표현하기 위해 여러 가지 특성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-192">Several attributes have been added to express additional information about the null state of variables.</span></span> <span data-ttu-id="3a223-193">C# 8에 null 허용 참조 형식을 도입하기 전에 작성한 모든 코드는 ‘null 인식 불가능’이었습니다. </span><span class="sxs-lookup"><span data-stu-id="3a223-193">All code you wrote before C# 8 introduced nullable reference types was *null oblivious*.</span></span> <span data-ttu-id="3a223-194">즉, 모든 참조 형식 변수가 null일 수 있지만 null 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-194">That means any reference type variable may be null, but null checks aren't required.</span></span> <span data-ttu-id="3a223-195">코드가 ‘null 허용 인식’이 되면 해당 규칙이 변경됩니다. </span><span class="sxs-lookup"><span data-stu-id="3a223-195">Once your code is *nullable aware*, those rules change.</span></span> <span data-ttu-id="3a223-196">참조 형식은 `null` 값이 아니어야 하며 null 허용 참조 형식은 참조되기 전에 `null`에 대해 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-196">Reference types should never be the `null` value, and nullable reference types must be checked against `null` before being dereferenced.</span></span>

<span data-ttu-id="3a223-197">API에 대한 규칙은 `TryGetValue` API 시나리오에서 살펴본 것처럼 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-197">The rules for your APIs are likely more complicated, as you saw with the `TryGetValue` API scenario.</span></span> <span data-ttu-id="3a223-198">대부분의 API에는 변수가 `null`일 수 있거나 없는 경우에 대한 더 복잡한 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-198">Many of your APIs have more complex rules for when variables can or can't be `null`.</span></span> <span data-ttu-id="3a223-199">이러한 경우에는 특성을 사용하여 해당 규칙을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-199">In these cases, you'll use attributes to express those rules.</span></span> <span data-ttu-id="3a223-200">API의 의미 체계를 설명하는 특성은 [nullable 분석에 영향을 주는 특성](./language-reference/attributes/nullable-analysis.md)에 관한 문서에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-200">The attributes that describe the semantics of your API are found in the article on [Attributes that impact nullable analysis](./language-reference/attributes/nullable-analysis.md).</span></span>

## <a name="generic-definitions-and-nullability"></a><span data-ttu-id="3a223-201">제네릭 정의 및 null 허용 여부</span><span class="sxs-lookup"><span data-stu-id="3a223-201">Generic definitions and nullability</span></span>

<span data-ttu-id="3a223-202">제네릭 형식과 제네릭 메서드의 null 상태를 올바로 전달하려면 특별한 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-202">Correctly communicating the null state of generic types and generic methods requires special care.</span></span> <span data-ttu-id="3a223-203">각별한 주의가 필요한 이유는 nullable 값 형식과 nullable 참조 형식이 근본적으로 다르다는 점 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-203">The extra care stems from the fact that a nullable value type and a nullable reference type are fundamentally different.</span></span> <span data-ttu-id="3a223-204">`int?`는 `Nullable<int>`의 동의어이지만 `string?`는 컴파일러에서 추가한 특성을 갖는 `string`입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-204">An `int?` is a synonym for `Nullable<int>`, whereas `string?` is `string` with an attribute added by the compiler.</span></span> <span data-ttu-id="3a223-205">결과적으로 컴파일러에서는 `T`가 `class`인지 `struct`인지를 모르면 `T?`의 올바른 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-205">The result is that the compiler can't generate correct code for `T?` without knowing if `T` is a `class` or a `struct`.</span></span>

<span data-ttu-id="3a223-206">그렇다고 nullable 형식(값 형식 또는 참조 형식 중 하나)을 폐쇄형 제네릭 형식의 형식 인수로 사용할 수 없다는 의미는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-206">This fact doesn't mean you can't use a nullable type (either value type or reference type) as the type argument for a closed generic type.</span></span> <span data-ttu-id="3a223-207">`List<string?>`와 `List<int?>`는 모두 `List<T>`의 유효한 인스턴스화입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-207">Both `List<string?>` and `List<int?>` are valid instantiations of `List<T>`.</span></span>

<span data-ttu-id="3a223-208">따라서 `T?`를 제네릭 클래스 또는 메서드 선언에서 제약 조건이 없이 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-208">What it does mean is that you can't use `T?` in a generic class or method declaration without constraints.</span></span> <span data-ttu-id="3a223-209">예를 들어 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType>는 `T?`를 반환하도록 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-209">For example, <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> won't be changed to return `T?`.</span></span> <span data-ttu-id="3a223-210">`struct` 또는 `class` 제약 조건을 추가하여 이 제한을 극복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-210">You can overcome this limitation by adding either the `struct` or `class` constraint.</span></span> <span data-ttu-id="3a223-211">해당 제약 조건 중 하나가 있으면 컴파일러는 `T`와 `T?` 모두의 코드를 생성하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-211">With either of those constraints, the compiler knows how to generate code for both `T` and `T?`.</span></span>

<span data-ttu-id="3a223-212">제네릭 형식 인수에 사용되는 형식을 null을 허용하지 않는 형식으로 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-212">You may want to restrict the types used for a generic type argument to be non-nullable types.</span></span> <span data-ttu-id="3a223-213">이렇게 하려면 해당 형식 인수에 `notnull` 제약 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-213">You can do that by adding the `notnull` constraint on that type argument.</span></span> <span data-ttu-id="3a223-214">해당 제약 조건을 적용하면 형식 인수는 nullable 형식이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-214">When that constraint is applied, the type argument must not be a nullable type.</span></span>

## <a name="late-initialized-properties-data-transfer-objects-and-nullability"></a><span data-ttu-id="3a223-215">런타임에 초기화되는 속성, 데이터 전송 개체, null 허용 여부</span><span class="sxs-lookup"><span data-stu-id="3a223-215">Late-initialized properties, Data Transfer Objects, and nullability</span></span>

<span data-ttu-id="3a223-216">생성 후 설정됨을 의미하는 런타임에 초기화되는 속성의 null 허용 여부를 나타내려면 클래스에서 계속 원래 디자인 의도를 올바르게 표현하도록 특별히 고려해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-216">Indicating the nullability of properties that are late-initialized, meaning set after construction, may require special consideration to ensure that your class continues to correctly express the original design intent.</span></span>

<span data-ttu-id="3a223-217">DTO(데이터 전송 개체)와 같이 런타임에 초기화되는 속성을 포함하는 형식은 데이터베이스 ORM(개체 관계형 매퍼), 역직렬 변환기, 다른 소스의 속성을 자동으로 채우는 일부 다른 구성 요소 등과 같은 외부 라이브러리에 의해 인스턴스화되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-217">Types that contain late-initialized properties, such as Data Transfer Objects (DTOs), are often instantiated by an external library, like a database ORM (Object Relational Mapper), a deserializer, or some other component that automatically populates properties from another source.</span></span>

<span data-ttu-id="3a223-218">Nullable 참조 형식을 사용하도록 설정하기 전에 학생을 나타내는 다음 DTO 클래스를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-218">Consider the following DTO class, prior to enabling nullable reference types, that represents a student:</span></span>

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string VehicleRegistration { get; set; }
}
```

<span data-ttu-id="3a223-219">이 경우 `Required` 특성으로 표시되는 디자인 의도에서는 이 시스템에서 `FirstName` 및 `LastName` 속성이 **필수** 이고 따라서 null이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-219">The design intent (indicated in this case by the `Required` attribute) suggests that in this system, the `FirstName` and `LastName` properties are **mandatory**, and therefore not null.</span></span>

<span data-ttu-id="3a223-220">`VehicleRegistration` 속성은 **필수가 아니므로** null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-220">The `VehicleRegistration` property is **not mandatory**, so may be null.</span></span>

<span data-ttu-id="3a223-221">Nullable 참조 형식을 사용하도록 설정할 때 원래 의도와 일치하도록 DTO의 속성 중 nullable일 수 있는 속성을 나타내려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-221">When you enable nullable reference types, you want to indicate which properties on your DTO may be nullable, consistent with your original intent:</span></span>

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

<span data-ttu-id="3a223-222">이 DTO 경우 null일 수 있는 속성은 ``VehicleRegistration``뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-222">For this DTO, the only property that may be null is ``VehicleRegistration``.</span></span>

<span data-ttu-id="3a223-223">그러나 컴파일러는 `FirstName` 및 `LastName` 모두에 대해 null을 허용하지 않는 속성이 초기화되지 않았음을 나타내는 `CS8618` 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-223">However, the compiler raises `CS8618` warnings for both `FirstName` and `LastName`, indicating the non-nullable properties are uninitialized.</span></span>

<span data-ttu-id="3a223-224">원래 의도를 유지하면서 컴파일러 경고를 해결하는 세 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-224">There are three options available to you that resolve the compiler warnings in a way that maintains the original intent.</span></span> <span data-ttu-id="3a223-225">해당 옵션은 모두 유효하지만, 코딩 스타일과 디자인 요구 사항에 가장 적합한 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-225">Any of these options are valid; you should choose the one that best suits your coding style and design requirements.</span></span>

### <a name="initialize-in-the-constructor"></a><span data-ttu-id="3a223-226">생성자에서 초기화</span><span class="sxs-lookup"><span data-stu-id="3a223-226">Initialize in the constructor</span></span>

<span data-ttu-id="3a223-227">초기화되지 않음 경고를 해결하는 데 적합한 방법은 생성자에서 속성을 초기화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-227">The ideal way to resolve the uninitialized warnings is to initialize the properties in the constructor:</span></span>

```csharp
class Student
{
    public Student(string firstName, string lastName)
    {
        FirstName = firstName;
        LastName = lastName;
    }

    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

<span data-ttu-id="3a223-228">이 접근 방식은 클래스를 인스턴스화하기 위해 사용하는 라이브러리가 생성자에서 매개 변수 전달을 지원하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-228">This approach only works if the library that you use to instantiate the class supports passing parameters in the constructor.</span></span>

<span data-ttu-id="3a223-229">라이브러리는 생성자에서 전부는 아니지만 ‘일부’ 속성의 전달을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-229">A library may support passing *some* properties in the constructor, but not all.</span></span> <span data-ttu-id="3a223-230">예를 들어 EF Core에서는 일반 열 속성은 [생성자 바인딩](/ef/core/modeling/constructors)을 지원하지만 탐색 속성의 경우 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-230">For example, EF Core supports [constructor binding](/ef/core/modeling/constructors) for normal column properties, but not navigation properties.</span></span>

<span data-ttu-id="3a223-231">클래스를 인스턴스화하는 라이브러리 관련 설명서를 확인하여 생성자 바인딩을 지원하는 범위를 파악하세요.</span><span class="sxs-lookup"><span data-stu-id="3a223-231">Check the documentation on the library that instantiates your class, to understand the extent to which it supports constructor binding.</span></span>

### <a name="property-with-nullable-backing-field"></a><span data-ttu-id="3a223-232">Nullable 지원 필드가 있는 속성</span><span class="sxs-lookup"><span data-stu-id="3a223-232">Property with nullable backing field</span></span>

<span data-ttu-id="3a223-233">생성자 바인딩이 적합하지 않은 경우 이 문제를 해결하는 한 가지 방법으로 nullable 지원 필드가 있는 null을 허용하지 않는 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-233">If constructor binding won't work for you, one way to deal with this problem is to have a non-nullable property with a nullable backing field:</span></span>

```csharp
private string? _firstName;

[Required]
public string FirstName
{
    set => _firstName = value;
    get => _firstName
           ?? throw new InvalidOperationException("Uninitialized " + nameof(FirstName))
}
```

<span data-ttu-id="3a223-234">해당 시나리오에서는 `FirstName` 속성을 초기화되기 전에 액세스하는 경우 API 계약이 잘못 사용되었으므로 코드에서 `InvalidOperationException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-234">In this scenario, if the `FirstName` property is accessed before it has been initialized, then the code throws an `InvalidOperationException`, because the API contract has been used incorrectly.</span></span>

<span data-ttu-id="3a223-235">지원 필드를 사용할 경우 일부 라이브러리에 특별히 고려할 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-235">Consider that some libraries may have special considerations when using backing fields.</span></span> <span data-ttu-id="3a223-236">예를 들어 EF Core에서는 [지원 필드](/ef/core/modeling/backing-field) 올바로 사용하도록 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-236">For example, EF Core may need to be configured to use [backing fields](/ef/core/modeling/backing-field) correctly.</span></span>

### <a name="initialize-the-property-to-null"></a><span data-ttu-id="3a223-237">속성을 null로 초기화</span><span class="sxs-lookup"><span data-stu-id="3a223-237">Initialize the property to null</span></span>

<span data-ttu-id="3a223-238">Nullable 지원 필드 사용의 간단한 대안으로 또는 클래스를 인스턴스화하는 라이브러리가 해당 접근 방식과 호환되지 않는 경우 null 허용 연산자(`!`)를 통해 속성을 직접 `null`로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-238">As a terser alternative to using a nullable backing field, or if the library that instantiates your class isn't compatible with that approach, you can initialize the property to `null` directly, with the help of the null-forgiving operator (`!`):</span></span>

```csharp
[Required]
public string FirstName { get; set; } = null!;

[Required]
public string LastName { get; set; } = null!;

public string? VehicleRegistration { get; set; }
```

<span data-ttu-id="3a223-239">프로그래밍 버그의 결과인 경우를 제외하고는 속성이 올바로 초기화되기 전에 속성에 액세스하여 런타임에 실제 null 값을 확인하지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3a223-239">You'll never observe an actual null value at runtime except as a result of a programming bug, by accessing the property before it has been properly initialized.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a223-240">참조</span><span class="sxs-lookup"><span data-stu-id="3a223-240">See also</span></span>

- [<span data-ttu-id="3a223-241">기존 코드베이스를 nullable 참조로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3a223-241">Migrate an existing codebase to nullable references</span></span>](tutorials/upgrade-to-nullable-references.md)
- [<span data-ttu-id="3a223-242">EF Core에서 nullable 참조 형식 사용</span><span class="sxs-lookup"><span data-stu-id="3a223-242">Working with Nullable Reference Types in EF Core</span></span>](/ef/core/miscellaneous/nullable-reference-types)
