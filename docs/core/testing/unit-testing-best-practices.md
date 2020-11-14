---
title: 단위 테스트 작성에 대한 모범 사례
description: .NET Core 및 .NET 표준 프로젝트에 대한 코드 품질 및 탄력성을 구동하는 단위 테스트 작성에 대한 모범 사례를 알아봅니다.
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 6c1e9a665ad541bf6109634a6df857880ee47042
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281651"
---
# <a name="unit-testing-best-practices-with-net-core-and-net-standard"></a><span data-ttu-id="c5583-103">.NET Core 및.NET 표준을 사용하는 단위 테스트 모범 사례</span><span class="sxs-lookup"><span data-stu-id="c5583-103">Unit testing best practices with .NET Core and .NET Standard</span></span>

<span data-ttu-id="c5583-104">단위 테스트 작성에는 회귀를 돕고, 문서를 제공하고, 좋은 디자인을 용이하게 하는 등에 다양한 혜택이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-104">There are numerous benefits to writing unit tests; they help with regression, provide documentation, and facilitate good design.</span></span> <span data-ttu-id="c5583-105">그러나 읽기 어렵고 불안정한 단위 테스트는 코드 기반을 파괴할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-105">However, hard to read and brittle unit tests can wreak havoc on your code base.</span></span> <span data-ttu-id="c5583-106">이 문서에서는.NET Core 및 .NET 표준 프로젝트용 단위 테스트 디자인과 관련된 몇 가지 모범 사례를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-106">This article describes some best practices regarding unit test design for your .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="c5583-107">이 가이드에서는 단위 테스트를 작성할 때 테스트를 탄력적이고 이해하기 쉽게 유지하기 위한 몇 가지 모범 사례를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-107">In this guide, you'll learn some best practices when writing unit tests to keep your tests resilient and easy to understand.</span></span>

<span data-ttu-id="c5583-108">[John Reese](https://reese.dev), [Roy Osherove](https://osherove.com/)에 대한 특별한 감사</span><span class="sxs-lookup"><span data-stu-id="c5583-108">By [John Reese](https://reese.dev) with special thanks to [Roy Osherove](https://osherove.com/)</span></span>

## <a name="why-unit-test"></a><span data-ttu-id="c5583-109">단위 테스트하는 이유는?</span><span class="sxs-lookup"><span data-stu-id="c5583-109">Why unit test?</span></span>

### <a name="less-time-performing-functional-tests"></a><span data-ttu-id="c5583-110">기능 테스트 수행 시간 단축</span><span class="sxs-lookup"><span data-stu-id="c5583-110">Less time performing functional tests</span></span>

<span data-ttu-id="c5583-111">기능 테스트는 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-111">Functional tests are expensive.</span></span> <span data-ttu-id="c5583-112">일반적으로 애플리케이션을 열고 사용자(또는 다른 사용자)가 예상되는 동작의 유효성을 검사하기 위해 따라야 하는 일련의 단계 수행이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-112">They typically involve opening up the application and performing a series of steps that you (or someone else), must follow in order to validate the expected behavior.</span></span> <span data-ttu-id="c5583-113">이러한 단계는 항상 테스터에게 알려진 것은 아니며, 이는 테스트를 수행하기 위해 해당 영역에 더 많은 지식을 갖추어야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-113">These steps may not always be known to the tester, which means they will have to reach out to someone more knowledgeable in the area in order to carry out the test.</span></span> <span data-ttu-id="c5583-114">테스트 자체는 사소한 변경인 경우에는 몇 초가 걸리거나 큰 변경의 경우에는 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-114">Testing itself could take seconds for trivial changes, or minutes for larger changes.</span></span> <span data-ttu-id="c5583-115">마지막으로, 이 프로세스는 시스템에서 수행하는 모든 변경 사항에 대해 반복되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-115">Lastly, this process must be repeated for every change that you make in the system.</span></span>

<span data-ttu-id="c5583-116">반면에 단위 테스트는 밀리초가 소요되고 단추를 눌러 실행할 수 있으며 시스템 전체에 대한 정보가 반드시 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-116">Unit tests, on the other hand, take milliseconds, can be run at the press of a button, and don't necessarily require any knowledge of the system at large.</span></span> <span data-ttu-id="c5583-117">테스트 통과 또는 실패 여부는 개인이 아닌 test runner의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-117">Whether or not the test passes or fails is up to the test runner, not the individual.</span></span>

### <a name="protection-against-regression"></a><span data-ttu-id="c5583-118">회귀에 대한 보호</span><span class="sxs-lookup"><span data-stu-id="c5583-118">Protection against regression</span></span>

<span data-ttu-id="c5583-119">회귀 오류는 애플리케이션이 변경될 때 도입된 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-119">Regression defects are defects that are introduced when a change is made to the application.</span></span> <span data-ttu-id="c5583-120">테스터는 새 기능을 테스트할 뿐만 아니라 이전에 구현된 기능이 여전히 예상대로 작동하는지 확인하기 위해 이전에 존재했던 기능도 테스트하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-120">It is common for testers to not only test their new feature but also features that existed beforehand in order to verify that previously implemented features still function as expected.</span></span>

<span data-ttu-id="c5583-121">단위 테스트를 사용하면 모든 빌드 후에 또는 코드 줄을 변경한 후에도 전체 테스트 도구 모음을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-121">With unit testing, it's possible to rerun your entire suite of tests after every build or even after you change a line of code.</span></span> <span data-ttu-id="c5583-122">새 코드가 기존 기능을 중단시키지 않는다는 신뢰를 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-122">Giving you confidence that your new code does not break existing functionality.</span></span>

### <a name="executable-documentation"></a><span data-ttu-id="c5583-123">실행 가능한 설명서</span><span class="sxs-lookup"><span data-stu-id="c5583-123">Executable documentation</span></span>

<span data-ttu-id="c5583-124">특정 메서드가 무엇을 하는지 또는 특정 입력이 지정된 동작이 어떻게 수행되는지 항상 명확하지는 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-124">It may not always be obvious what a particular method does or how it behaves given a certain input.</span></span> <span data-ttu-id="c5583-125">빈 문자열을 전달하면 이 메서드는 어떻게 작동하는가를 자문해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-125">You may ask yourself: How does this method behave if I pass it a blank string?</span></span> <span data-ttu-id="c5583-126">Null?</span><span class="sxs-lookup"><span data-stu-id="c5583-126">Null?</span></span>

<span data-ttu-id="c5583-127">이름이 잘 지정된 단위 테스트의 도구 모음이 있는 경우 각 테스트는 지정된 입력에 대해 예상되는 출력을 명확하게 설명할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-127">When you have a suite of well-named unit tests, each test should be able to clearly explain the expected output for a given input.</span></span> <span data-ttu-id="c5583-128">또한 실제로 작동하는지 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-128">In addition, it should be able to verify that it actually works.</span></span>

### <a name="less-coupled-code"></a><span data-ttu-id="c5583-129">적은 결합 코드</span><span class="sxs-lookup"><span data-stu-id="c5583-129">Less coupled code</span></span>

<span data-ttu-id="c5583-130">코드가 밀접하게 결합되면 단위 테스트하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-130">When code is tightly coupled, it can be difficult to unit test.</span></span> <span data-ttu-id="c5583-131">작성 중인 코드에 대한 단위 테스트를 만들지 않으면 결합이 덜 분명해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-131">Without creating unit tests for the code that you're writing, coupling may be less apparent.</span></span>

<span data-ttu-id="c5583-132">코드 테스트를 작성하면 자연스럽게 분리됩니다. 그렇지 않으면 테스트하기가 더 어려워지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-132">Writing tests for your code will naturally decouple your code, because it would be more difficult to test otherwise.</span></span>

## <a name="characteristics-of-a-good-unit-test"></a><span data-ttu-id="c5583-133">좋은 단위 테스트의 특징</span><span class="sxs-lookup"><span data-stu-id="c5583-133">Characteristics of a good unit test</span></span>

- <span data-ttu-id="c5583-134">**Fast**.</span><span class="sxs-lookup"><span data-stu-id="c5583-134">**Fast**.</span></span> <span data-ttu-id="c5583-135">완성도 높은 프로젝트에서 수천 개의 단위 테스트를 수행하는 것은 드문 일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-135">It is not uncommon for mature projects to have thousands of unit tests.</span></span> <span data-ttu-id="c5583-136">단위 테스트는 실행하는 데 시간이 거의 걸리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-136">Unit tests should take very little time to run.</span></span> <span data-ttu-id="c5583-137">밀리초.</span><span class="sxs-lookup"><span data-stu-id="c5583-137">Milliseconds.</span></span>
- <span data-ttu-id="c5583-138">**Isolated**.</span><span class="sxs-lookup"><span data-stu-id="c5583-138">**Isolated**.</span></span> <span data-ttu-id="c5583-139">독립형 단위 테스트는 독립적으로 실행될 수 있으며, 파일 시스템 또는 데이터베이스와 같은 외부 요인에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-139">Unit tests are standalone, can be run in isolation, and have no dependencies on any outside factors such as a file system or database.</span></span>
- <span data-ttu-id="c5583-140">**반복 가능**.</span><span class="sxs-lookup"><span data-stu-id="c5583-140">**Repeatable**.</span></span> <span data-ttu-id="c5583-141">단위 테스트를 실행하는 것은 해당 결과와 일치해야 합니다. 즉, 실행 사이에 아무 것도 변경하지 않으면 항상 동일한 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-141">Running a unit test should be consistent with its results, that is, it always returns the same result if you do not change anything in between runs.</span></span>
- <span data-ttu-id="c5583-142">**자체 검사**.</span><span class="sxs-lookup"><span data-stu-id="c5583-142">**Self-Checking**.</span></span> <span data-ttu-id="c5583-143">테스트는 사람의 개입 없이 통과했는지 여부를 자동으로 검색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-143">The test should be able to automatically detect if it passed or failed without any human interaction.</span></span>
- <span data-ttu-id="c5583-144">**Timely**.</span><span class="sxs-lookup"><span data-stu-id="c5583-144">**Timely**.</span></span> <span data-ttu-id="c5583-145">단위 테스트는 테스트 중인 코드에 비해 작성하는 데 불균형적으로 긴 시간이 걸리지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-145">A unit test should not take a disproportionately long time to write compared to the code being tested.</span></span> <span data-ttu-id="c5583-146">코드를 작성하는 데 비해 많은 시간이 걸리는 코드를 테스트하는 경우 더 많은 테스트가 가능한 디자인을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c5583-146">If you find testing the code taking a large amount of time compared to writing the code, consider a design that is more testable.</span></span>

## <a name="code-coverage"></a><span data-ttu-id="c5583-147">코드 검사</span><span class="sxs-lookup"><span data-stu-id="c5583-147">Code coverage</span></span>

<span data-ttu-id="c5583-148">높은 코드 검사 비율이 높으면 코드 품질이 높아지는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-148">A high code coverage percentage is often associated with a higher quality of code.</span></span> <span data-ttu-id="c5583-149">하지만 측정 자체로 코드 품질이 결정되지는 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="c5583-149">However, the measurement itself *cannot* determine the quality of code.</span></span> <span data-ttu-id="c5583-150">코드 검사 비율 목표를 지나치게 욕심을 부려 높게 설정하면 역효과가 날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-150">Setting an overly ambitious code coverage percentage goal can be counterproductive.</span></span> <span data-ttu-id="c5583-151">수천 개의 조건부 분기가 포함된 복잡한 프로젝트에서 95% 코드 검사 목표를 설정한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c5583-151">Imagine a complex project with thousands of conditional branches, and imagine that you set a goal of 95% code coverage.</span></span> <span data-ttu-id="c5583-152">현재 프로젝트에서는 90% 코드 검사를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-152">Currently the project maintains 90% code coverage.</span></span> <span data-ttu-id="c5583-153">나머지 5%의 극단적인 경우를 모두 고려하는 데에는 엄청난 시간이 들 수 있으며 가치 제안의 중요성이 곧 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-153">The amount of time it takes to account for all of the edge cases in the remaining 5% could be a massive undertaking, and the value proposition quickly diminishes.</span></span>

<span data-ttu-id="c5583-154">높은 코드 검사 비율은 성공의 지표도 아니고 높은 코드 품질을 의미하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-154">A high code coverage percentage is not an indicator of success, nor does it imply high code quality.</span></span> <span data-ttu-id="c5583-155">단위 테스트에서 검사되는 코드의 양을 나타낼 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-155">It just represents the amount of code that is covered by unit tests.</span></span> <span data-ttu-id="c5583-156">자세한 내용은 [유닛 테스트 코드 검사](unit-testing-code-coverage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5583-156">For more information, see [unit testing code coverage](unit-testing-code-coverage.md).</span></span>

## <a name="lets-speak-the-same-language"></a><span data-ttu-id="c5583-157">동일한 언어 사용</span><span class="sxs-lookup"><span data-stu-id="c5583-157">Let's speak the same language</span></span>

<span data-ttu-id="c5583-158">*mock* 이라는 용어는 불행히도 테스트에 대해 이야기할 때 종종 잘못 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-158">The term *mock* is unfortunately often misused when talking about testing.</span></span> <span data-ttu-id="c5583-159">다음은 단위 테스트를 작성할 때 *fakes* 의 가장 일반적인 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-159">The following points define the most common types of *fakes* when writing unit tests:</span></span>

<span data-ttu-id="c5583-160">*Fake* - fake는 스텁 또는 모의 개체를 설명하는 데 사용할 수 있는 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-160">*Fake* - A fake is a generic term that can be used to describe either a stub or a mock object.</span></span> <span data-ttu-id="c5583-161">stub 또는 mock인지 여부는 사용되는 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-161">Whether it's a stub or a mock depends on the context in which it's used.</span></span> <span data-ttu-id="c5583-162">즉, fake는 stub 또는 mock이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-162">So in other words, a fake can be a stub or a mock.</span></span>

<span data-ttu-id="c5583-163">*Mock* - mock 개체는 단위 테스트가 통과되었는지 여부를 결정하는 시스템에서 fake 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-163">*Mock* - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed.</span></span> <span data-ttu-id="c5583-164">mock은 어설션될 때까지 fake로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-164">A mock starts out as a Fake until it's asserted against.</span></span>

<span data-ttu-id="c5583-165">*Stub* - stub은 시스템의 기존 종속성(또는 협력자)을 제어할 수 있는 대체품입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-165">*Stub* - A stub is a controllable replacement for an existing dependency (or collaborator) in the system.</span></span> <span data-ttu-id="c5583-166">stub을 사용하여 종속성을 직접 처리하지 않고 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-166">By using a stub, you can test your code without dealing with the dependency directly.</span></span> <span data-ttu-id="c5583-167">기본적으로 fake는 stub으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-167">By default, a fake starts out as a stub.</span></span>

<span data-ttu-id="c5583-168">다음 코드 조각을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-168">Consider the following code snippet:</span></span>

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="c5583-169">이는 stub이 mock이라고 불리는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-169">This would be an example of stub being referred to as a mock.</span></span> <span data-ttu-id="c5583-170">이 경우 stub입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-170">In this case, it is a stub.</span></span> <span data-ttu-id="c5583-171">`Purchase`(테스트 중인 시스템)를 인스턴스화할 수 있는 수단으로 Order를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-171">You're just passing in the Order as a means to be able to instantiate `Purchase` (the system under test).</span></span> <span data-ttu-id="c5583-172">`MockOrder` 이름도 잘못된 것입니다. 다시 말해서, 순서가 mock이 아니기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-172">The name `MockOrder` is also misleading because again, the order is not a mock.</span></span>

<span data-ttu-id="c5583-173">더 나은 방법은</span><span class="sxs-lookup"><span data-stu-id="c5583-173">A better approach would be</span></span>

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="c5583-174">클래스 이름을 `FakeOrder`로 바꾸면 클래스를 훨씬 더 일반화되게 만들므로 클래스를 mock 또는 stub으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-174">By renaming the class to `FakeOrder`, you've made the class a lot more generic, the class can be used as a mock or a stub.</span></span> <span data-ttu-id="c5583-175">어느 것이든 테스트 사례에 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-175">Whichever is better for the test case.</span></span> <span data-ttu-id="c5583-176">위의 예에서는 `FakeOrder`가 stub으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-176">In the above example, `FakeOrder` is used as a stub.</span></span> <span data-ttu-id="c5583-177">assert 중에 `FakeOrder`를 어떤 모양 또는 형태로 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-177">You're not using the `FakeOrder` in any shape or form during the assert.</span></span> <span data-ttu-id="c5583-178">`FakeOrder`는 방금 `Purchase` 클래스에 전달되어 생성자의 요구 사항을 충족했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-178">`FakeOrder` was passed into the `Purchase` class to satisfy the requirements of the constructor.</span></span>

<span data-ttu-id="c5583-179">Mock으로 사용하려면 다음과 같이 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-179">To use it as a Mock, you could do something like this</span></span>

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

<span data-ttu-id="c5583-180">이 경우 Fake(해당 항목에 대한 어설션)의 속성을 확인 중이므로 위의 코드 조각에서 `mockOrder`는 Mock입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-180">In this case, you are checking a property on the Fake (asserting against it), so in the above code snippet, the `mockOrder` is a Mock.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5583-181">이 용어를 올바르게 사용하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-181">It's important to get this terminology correct.</span></span> <span data-ttu-id="c5583-182">stubs를 "mocks"라고 부른다면 다른 개발자는 의도에 대해 잘못된 가정을 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-182">If you call your stubs "mocks", other developers are going to make false assumptions about your intent.</span></span>

<span data-ttu-id="c5583-183">mocks와 stubs에 대해 기억해야 할 주요 사항은 mocks는 stubs와 같지만, 모의 개체에 대해 어설션하는 반면 stub에 대해서는 어설션하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-183">The main thing to remember about mocks versus stubs is that mocks are just like stubs, but you assert against the mock object, whereas you do not assert against a stub.</span></span>

## <a name="best-practices"></a><span data-ttu-id="c5583-184">최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="c5583-184">Best practices</span></span>

<span data-ttu-id="c5583-185">단위 테스트를 작성하는 경우 인프라에 대한 종속성을 도입하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-185">Try not to introduce dependencies on infrastructure when writing unit tests.</span></span> <span data-ttu-id="c5583-186">종속성으로 인해 테스트가 느리고 불안정해지므로 통합 테스트에 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-186">These make the tests slow and brittle and should be reserved for integration tests.</span></span> <span data-ttu-id="c5583-187">[명시적 종속성 원칙](https://deviq.com/explicit-dependencies-principle)을 따르고 [종속성 주입](../extensions/dependency-injection.md)을 사용하여 애플리케이션에서 이러한 종속성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-187">You can avoid these dependencies in your application by following the [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle) and using [Dependency Injection](../extensions/dependency-injection.md).</span></span> <span data-ttu-id="c5583-188">통합 테스트의 개별 프로젝트에서 단위 테스트를 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-188">You can also keep your unit tests in a separate project from your integration tests.</span></span> <span data-ttu-id="c5583-189">이렇게 하면 단위 테스트 프로젝트가 인프라 패키지에 대한 참조 또는 종속성을 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-189">This ensures your unit test project doesn't have references to or dependencies on infrastructure packages.</span></span>

### <a name="naming-your-tests"></a><span data-ttu-id="c5583-190">테스트 이름 지정</span><span class="sxs-lookup"><span data-stu-id="c5583-190">Naming your tests</span></span>

<span data-ttu-id="c5583-191">테스트의 이름은 다음 세 부분으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-191">The name of your test should consist of three parts:</span></span>

- <span data-ttu-id="c5583-192">테스트할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-192">The name of the method being tested.</span></span>
- <span data-ttu-id="c5583-193">테스트 중인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-193">The scenario under which it's being tested.</span></span>
- <span data-ttu-id="c5583-194">시나리오에서 호출될 때 예상되는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-194">The expected behavior when the scenario is invoked.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-195">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-195">Why?</span></span>

- <span data-ttu-id="c5583-196">이름 지정 표준은 테스트의 의도를 명시적으로 표현하기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-196">Naming standards are important because they explicitly express the intent of the test.</span></span>

<span data-ttu-id="c5583-197">테스트는 단순히 코드가 작동하는지 확인하는 것 이상이며, 문서도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-197">Tests are more than just making sure your code works, they also provide documentation.</span></span> <span data-ttu-id="c5583-198">단위 테스트 도구 모음을 살펴봄으로써 코드 자체를 조회하지 않고도 코드의 동작을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-198">Just by looking at the suite of unit tests, you should be able to infer the behavior of your code without even looking at the code itself.</span></span> <span data-ttu-id="c5583-199">또한 테스트가 실패하는 경우 기대치를 충족하지 못하는 시나리오를 정확히 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-199">Additionally, when tests fail, you can see exactly which scenarios do not meet your expectations.</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-200">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-200">Bad:</span></span>

[!code-csharp[BeforeNaming](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a><span data-ttu-id="c5583-201">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-201">Better:</span></span>

[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a><span data-ttu-id="c5583-202">테스트 정렬</span><span class="sxs-lookup"><span data-stu-id="c5583-202">Arranging your tests</span></span>

<span data-ttu-id="c5583-203">**정렬, 동작, 어설션** 은 단위 테스트 시 일반적인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-203">**Arrange, Act, Assert** is a common pattern when unit testing.</span></span> <span data-ttu-id="c5583-204">이름에서 알 수 있듯이 세 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-204">As the name implies, it consists of three main actions:</span></span>

- <span data-ttu-id="c5583-205">개체를 *정렬* 하고 필요에 따라 만들고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-205">*Arrange* your objects, creating and setting them up as necessary.</span></span>
- <span data-ttu-id="c5583-206">개체의 *동작* 입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-206">*Act* on an object.</span></span>
- <span data-ttu-id="c5583-207">특정 항목이 예상대로라고 *assert* 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-207">*Assert* that something is as expected.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-208">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-208">Why?</span></span>

- <span data-ttu-id="c5583-209">테스트할 항목을 *정렬* 및 *assert* 단계에서 명확하게 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-209">Clearly separates what is being tested from the *arrange* and *assert* steps.</span></span>
- <span data-ttu-id="c5583-210">어설션과 "Act" 코드를 혼합할 기회가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-210">Less chance to intermix assertions with "Act" code.</span></span>

<span data-ttu-id="c5583-211">가독성은 테스트를 작성할 때 가장 중요한 측면 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-211">Readability is one of the most important aspects when writing a test.</span></span> <span data-ttu-id="c5583-212">테스트 내에서 이러한 작업을 각각 구분하면 코드를 호출하는 데 필요한 종속성, 코드 호출 방법 및 어설션하려는 대상이 명확하게 강조 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-212">Separating each of these actions within the test clearly highlight the dependencies required to call your code, how your code is being called, and what you are trying to assert.</span></span> <span data-ttu-id="c5583-213">몇 가지 단계를 결합하여 테스트의 크기를 줄일 수 있지만, 기본적인 목표는 가능한 한 테스트를 최대한으로 읽을 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-213">While it may be possible to combine some steps and reduce the size of your test, the primary goal is to make the test as readable as possible.</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-214">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-214">Bad:</span></span>

[!code-csharp[BeforeArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a><span data-ttu-id="c5583-215">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-215">Better:</span></span>

[!code-csharp[AfterArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a><span data-ttu-id="c5583-216">최소한의 테스트 통과 작성</span><span class="sxs-lookup"><span data-stu-id="c5583-216">Write minimally passing tests</span></span>

<span data-ttu-id="c5583-217">단위 테스트에 사용할 입력은 현재 테스트 중인 동작을 확인하기 위해 가능한 한 가장 간단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-217">The input to be used in a unit test should be the simplest possible in order to verify the behavior that you are currently testing.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-218">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-218">Why?</span></span>

- <span data-ttu-id="c5583-219">테스트는 코드베이스의 향후 변화에 대한 복원력이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-219">Tests become more resilient to future changes in the codebase.</span></span>
- <span data-ttu-id="c5583-220">구현에 대한 테스트 동작에 근접합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-220">Closer to testing behavior over implementation.</span></span>

<span data-ttu-id="c5583-221">테스트를 통과하는 데 필요한 것보다 많은 정보를 포함하는 테스트는 테스트에 오류가 발생할 가능성이 높으며 테스트의 의도를 덜 명확하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-221">Tests that include more information than required to pass the test have a higher chance of introducing errors into the test and can make the intent of the test less clear.</span></span> <span data-ttu-id="c5583-222">테스트를 작성할 때 동작에 집중하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-222">When writing tests, you want to focus on the behavior.</span></span> <span data-ttu-id="c5583-223">모델의 추가 속성을 설정하거나 필요하지 않을 때 0이 아닌 값을 사용하면 증명하려고 시도한 것만 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-223">Setting extra properties on models or using non-zero values when not required, only detracts from what you are trying to prove.</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-224">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-224">Bad:</span></span>

[!code-csharp[BeforeMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a><span data-ttu-id="c5583-225">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-225">Better:</span></span>

[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a><span data-ttu-id="c5583-226">매직 문자열 방지</span><span class="sxs-lookup"><span data-stu-id="c5583-226">Avoid magic strings</span></span>

<span data-ttu-id="c5583-227">단위 테스트의 이름 지정 변수는(프로덕션 코드의 이름 지정 변수보다 더 중요하지는 않지만) 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-227">Naming variables in unit tests is as important, if not more important, than naming variables in production code.</span></span> <span data-ttu-id="c5583-228">단위 테스트에는 매직 문자열이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-228">Unit tests should not contain magic strings.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-229">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-229">Why?</span></span>

- <span data-ttu-id="c5583-230">값을 특별하게 만드는 요인을 파악하기 위해 테스트의 판독기가 프로덕션 코드를 검사할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-230">Prevents the need for the reader of the test to inspect the production code in order to figure out what makes the value special.</span></span>
- <span data-ttu-id="c5583-231">*성취* 하려는 것보다는 *증명* 하려는 것을 명시적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-231">Explicitly shows what you're trying to *prove* rather than trying to *accomplish*.</span></span>

<span data-ttu-id="c5583-232">매직 문자열은 테스트 판독기에 혼동을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-232">Magic strings can cause confusion to the reader of your tests.</span></span> <span data-ttu-id="c5583-233">문자열이 일반적이지 않은 경우 매개 변수 또는 반환 값에 대해 특정 값이 선택된 이유가 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-233">If a string looks out of the ordinary, they may wonder why a certain value was chosen for a parameter or return value.</span></span> <span data-ttu-id="c5583-234">이를 통해 테스트에 집중하기보다는 구현 세부 사항을 더 자세히 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-234">This may lead them to take a closer look at the implementation details, rather than focus on the test.</span></span>

> [!TIP]
> <span data-ttu-id="c5583-235">테스트를 작성할 때는 가능한 한 많은 의도를 표현하는 것을 목표로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-235">When writing tests, you should aim to express as much intent as possible.</span></span> <span data-ttu-id="c5583-236">매직 문자열의 경우 좋은 방법은 이러한 값을 상수에 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-236">In the case of magic strings, a good approach is to assign these values to constants.</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-237">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-237">Bad:</span></span>

[!code-csharp[BeforeMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a><span data-ttu-id="c5583-238">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-238">Better:</span></span>

[!code-csharp[AfterMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a><span data-ttu-id="c5583-239">테스트에서 논리 방지</span><span class="sxs-lookup"><span data-stu-id="c5583-239">Avoid logic in tests</span></span>

<span data-ttu-id="c5583-240">단위 테스트를 작성할 때 수동 문자열 연결 및 `if`, `while`, `for`, `switch` 등의 논리 조건을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-240">When writing your unit tests avoid manual string concatenation and logical conditions such as `if`, `while`, `for`, `switch`, etc.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-241">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-241">Why?</span></span>

- <span data-ttu-id="c5583-242">테스트 중에 버그가 발생할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-242">Less chance to introduce a bug inside of your tests.</span></span>
- <span data-ttu-id="c5583-243">구현 세부 정보보다는 최종 결과에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-243">Focus on the end result, rather than implementation details.</span></span>

<span data-ttu-id="c5583-244">테스트 도구 모음에 논리를 도입하면 버그가 발생할 가능성이 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-244">When you introduce logic into your test suite, the chance of introducing a bug into it increases dramatically.</span></span> <span data-ttu-id="c5583-245">버그를 찾고자 하는 마지막 위치는 테스트 도구 모음 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-245">The last place that you want to find a bug is within your test suite.</span></span> <span data-ttu-id="c5583-246">테스트 작동에 높은 수준의 확신이 있어야 합니다. 그렇지 않으면 신뢰할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-246">You should have a high level of confidence that your tests work, otherwise, you will not trust them.</span></span> <span data-ttu-id="c5583-247">신뢰할 수 없는 테스트는 어떤 가치도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-247">Tests that you do not trust, do not provide any value.</span></span> <span data-ttu-id="c5583-248">테스트가 실패하면 코드에 실제로 잘못된 것이 있어서 무시할 수 없다는 것을 느낄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-248">When a test fails, you want to have a sense that something is actually wrong with your code and that it cannot be ignored.</span></span>

> [!TIP]
> <span data-ttu-id="c5583-249">테스트의 논리가 불가피한 경우 테스트를 두 개 이상의 다른 테스트로 분할하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-249">If logic in your test seems unavoidable, consider splitting the test up into two or more different tests.</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-250">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-250">Bad:</span></span>

[!code-csharp[LogicInTests](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a><span data-ttu-id="c5583-251">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-251">Better:</span></span>

[!code-csharp[AfterTestLogic](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a><span data-ttu-id="c5583-252">설정 및 해제할 도우미 방법 선호</span><span class="sxs-lookup"><span data-stu-id="c5583-252">Prefer helper methods to setup and teardown</span></span>

<span data-ttu-id="c5583-253">테스트에 비슷한 개체나 상태가 필요한 경우 `Setup` 및 `Teardown` 특성(있는 경우)을 활용하는 것보다 도우미 메서드가 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-253">If you require a similar object or state for your tests, prefer a helper method than leveraging `Setup` and `Teardown` attributes if they exist.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-254">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-254">Why?</span></span>

- <span data-ttu-id="c5583-255">모든 코트가 각 테스트 내에서 볼 수 있기 때문에 테스트를 읽을 때 혼동이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-255">Less confusion when reading the tests since all of the code is visible from within each test.</span></span>
- <span data-ttu-id="c5583-256">지정된 테스트에 대해 너무 많거나 너무 적게 설정될 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-256">Less chance of setting up too much or too little for the given test.</span></span>
- <span data-ttu-id="c5583-257">테스트 간 상태 공유로 테스트 간에 원치 않는 종속성이 생길 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-257">Less chance of sharing state between tests, which creates unwanted dependencies between them.</span></span>

<span data-ttu-id="c5583-258">단위 테스트 프레임워크에서 `Setup`은 단위 테스트 도구 모음 내의 각각의 모든 단위 테스트 전에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-258">In unit testing frameworks, `Setup` is called before each and every unit test within your test suite.</span></span> <span data-ttu-id="c5583-259">일부는 이를 유용한 도구로 볼 수 있지만, 일반적으로 테스트를 읽기에는 비대해지고 어렵워집니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-259">While some may see this as a useful tool, it generally ends up leading to bloated and hard to read tests.</span></span> <span data-ttu-id="c5583-260">각 테스트는 일반적으로 테스트를 시작하고 실행하기 위한 요구 사항이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-260">Each test will generally have different requirements in order to get the test up and running.</span></span> <span data-ttu-id="c5583-261">아쉽게도 `Setup`에서는 각 테스트에 대해 정확히 동일한 요구 사항을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-261">Unfortunately, `Setup` forces you to use the exact same requirements for each test.</span></span>

> [!NOTE]
> <span data-ttu-id="c5583-262">xUnit은 버전 2.x에서 SetUp 및 TearDown을 모두 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-262">xUnit has removed both SetUp and TearDown as of version 2.x</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-263">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-263">Bad:</span></span>

[!code-csharp[BeforeSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a><span data-ttu-id="c5583-264">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-264">Better:</span></span>

[!code-csharp[AfterHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a><span data-ttu-id="c5583-265">다중 어설션 방지</span><span class="sxs-lookup"><span data-stu-id="c5583-265">Avoid multiple asserts</span></span>

<span data-ttu-id="c5583-266">테스트를 작성할 때 테스트당 하나의 Assert만 포함하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-266">When writing your tests, try to only include one Assert per test.</span></span> <span data-ttu-id="c5583-267">하나의 어설션만 사용하는 일반적인 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-267">Common approaches to using only one assert include:</span></span>

- <span data-ttu-id="c5583-268">각 어설션에 대한 별도의 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-268">Create a separate test for each assert.</span></span>
- <span data-ttu-id="c5583-269">매개 변수화된 테스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-269">Use parameterized tests.</span></span>

#### <a name="why"></a><span data-ttu-id="c5583-270">이유</span><span class="sxs-lookup"><span data-stu-id="c5583-270">Why?</span></span>

- <span data-ttu-id="c5583-271">하나의 Assert가 실패하면 후속 Assert는 평가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-271">If one Assert fails, the subsequent Asserts will not be evaluated.</span></span>
- <span data-ttu-id="c5583-272">테스트에 여러 사례를 어설션하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-272">Ensures you are not asserting multiple cases in your tests.</span></span>
- <span data-ttu-id="c5583-273">테스트가 실패한 이유에 대한 전체 그림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-273">Gives you the entire picture as to why your tests are failing.</span></span>

<span data-ttu-id="c5583-274">테스트 사례에 다중 어설션을 도입할 때 모든 어설션이 실행된다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-274">When introducing multiple asserts into a test case, it is not guaranteed that all of the asserts will be executed.</span></span> <span data-ttu-id="c5583-275">대부분의 단위 테스트 프레임워크에서 단위 테스트에 어설션이 실패하면 절차 테스트는 자동으로 실패한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-275">In most unit testing frameworks, once an assertion fails in a unit test, the proceeding tests are automatically considered to be failing.</span></span> <span data-ttu-id="c5583-276">실제로 작동하는 기능이 실패한 것으로 표시되므로 혼란스러울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-276">This can be confusing as functionality that is actually working, will be shown as failing.</span></span>

> [!NOTE]
> <span data-ttu-id="c5583-277">이 규칙에 대한 일반적인 예외는 개체에 대해 어설션할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-277">A common exception to this rule is when asserting against an object.</span></span> <span data-ttu-id="c5583-278">이 경우 일반적으로 각 속성에 대해 다중 어설션을 허용하여 개체가 예상되는 상태에 있는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-278">In this case, it is generally acceptable to have multiple asserts against each property to ensure the object is in the state that you expect it to be in.</span></span>

#### <a name="bad"></a><span data-ttu-id="c5583-279">Bad:</span><span class="sxs-lookup"><span data-stu-id="c5583-279">Bad:</span></span>

[!code-csharp[BeforeMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a><span data-ttu-id="c5583-280">Better:</span><span class="sxs-lookup"><span data-stu-id="c5583-280">Better:</span></span>

[!code-csharp[AfterMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a><span data-ttu-id="c5583-281">공용 메서드를 테스트하여 전용 메서드 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c5583-281">Validate private methods by unit testing public methods</span></span>

<span data-ttu-id="c5583-282">대부분의 경우 전용 메서드를 테스트할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-282">In most cases, there should not be a need to test a private method.</span></span> <span data-ttu-id="c5583-283">전용 메서드는 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-283">Private methods are an implementation detail.</span></span> <span data-ttu-id="c5583-284">전용 메서드는 절대 분리되어 존재하지 않는다고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-284">You can think of it this way: private methods never exist in isolation.</span></span> <span data-ttu-id="c5583-285">특정 시점에서는 구현의 일부로 전용 메서드를 호출하는 공용 연결 메서드가 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-285">At some point, there is going to be a public facing method that calls the private method as part of its implementation.</span></span> <span data-ttu-id="c5583-286">주의해야 할 것은 사적인 것을 호출하는 공용 메서드의 최종 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-286">What you should care about is the end result of the public method that calls into the private one.</span></span>

<span data-ttu-id="c5583-287">다음 경우를 참조</span><span class="sxs-lookup"><span data-stu-id="c5583-287">Consider the following case</span></span>

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = TrimInput(input);
    return sanitizedInput;
}

private string TrimInput(string input)
{
    return input.Trim();
}
```

<span data-ttu-id="c5583-288">첫 번째 반응은 메서드가 예상대로 작동하는지 확인하려고 하기 때문에 `TrimInput`에 대한 테스트를 작성하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-288">Your first reaction may be to start writing a test for `TrimInput` because you want to make sure that the method is working as expected.</span></span> <span data-ttu-id="c5583-289">그러나 `ParseLogLine`에서 예상하지 못한 방식으로 `sanitizedInput`을 조작하여 쓸모없는 `TrimInput`에 대한 테스트를 렌더링하는 것은 전적으로 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-289">However, it is entirely possible that `ParseLogLine` manipulates `sanitizedInput` in such a way that you do not expect, rendering a test against `TrimInput` useless.</span></span>

<span data-ttu-id="c5583-290">실제 테스트는 공용 연결 메서드 `ParseLogLine`에 대해 수행되어야 합니다. 이는 최종적으로 주의를 기울여야 하는 것이기 때문이다.</span><span class="sxs-lookup"><span data-stu-id="c5583-290">The real test should be done against the public facing method `ParseLogLine` because that is what you should ultimately care about.</span></span>

```csharp
public void ParseLogLine_StartsAndEndsWithSpace_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

<span data-ttu-id="c5583-291">이 관점에서, 전용 메서드를 표시하는 경우 공용 메서드를 찾아 해당 메서드에 대해 테스트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-291">With this viewpoint, if you see a private method, find the public method and write your tests against that method.</span></span> <span data-ttu-id="c5583-292">단지 전용 메서드가 예상된 결과를 반환한다고 해서 최종적으로 전용 메서드를 호출하는 시스템이 결과를 올바르게 사용하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-292">Just because a private method returns the expected result, does not mean the system that eventually calls the private method uses the result correctly.</span></span>

### <a name="stub-static-references"></a><span data-ttu-id="c5583-293">Stub 정적 참조</span><span class="sxs-lookup"><span data-stu-id="c5583-293">Stub static references</span></span>

<span data-ttu-id="c5583-294">단위 테스트의 원칙 중 하나는 테스트 중인 시스템을 완전히 제어해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-294">One of the principles of a unit test is that it must have full control of the system under test.</span></span> <span data-ttu-id="c5583-295">프로덕션 코드에 정적 참조(예: `DateTime.Now`)에 대한 호출을 포함하는 경우 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-295">This can be problematic when production code includes calls to static references (for example, `DateTime.Now`).</span></span> <span data-ttu-id="c5583-296">다음 코드 참조</span><span class="sxs-lookup"><span data-stu-id="c5583-296">Consider the following code</span></span>

```csharp
public int GetDiscountedPrice(int price)
{
    if (DateTime.Now.DayOfWeek == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

<span data-ttu-id="c5583-297">이 코드를 어떻게 단위 테스트할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c5583-297">How can this code possibly be unit tested?</span></span> <span data-ttu-id="c5583-298">다음과 같은 방법을 시도하는 경우</span><span class="sxs-lookup"><span data-stu-id="c5583-298">You may try an approach such as</span></span>

```csharp
public void GetDiscountedPrice_NotTuesday_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="c5583-299">아쉽게도 테스트에 몇 가지 문제점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-299">Unfortunately, you will quickly realize that there are a couple problems with your tests.</span></span>

- <span data-ttu-id="c5583-300">테스트 도구 모음을 화요일에 실행하면 두 번째 테스트는 통과하지만 첫 번째 테스트는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-300">If the test suite is run on a Tuesday, the second test will pass, but the first test will fail.</span></span>
- <span data-ttu-id="c5583-301">테스트 도구 모음을 다른 날에 실행하면 첫 번째 테스트는 통과하지만 두 번째 테스트는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-301">If the test suite is run on any other day, the first test will pass, but the second test will fail.</span></span>

<span data-ttu-id="c5583-302">이러한 문제를 해결하려면 프로덕션 코드에 *이음새* 를 도입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-302">To solve these problems, you'll need to introduce a *seam* into your production code.</span></span> <span data-ttu-id="c5583-303">한 가지 방법은 인터페이스에서 제어해야 하는 코드를 래핑하여 프로덕션 코드가 해당 인터페이스에 종속되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-303">One approach is to wrap the code that you need to control in an interface and have the production code depend on that interface.</span></span>

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if (dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

<span data-ttu-id="c5583-304">이제 테스트 도구 모음이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-304">Your test suite now becomes</span></span>

```csharp
public void GetDiscountedPrice_NotTuesday_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="c5583-305">이제 테스트 도구 모음은 `DateTime.Now`에 대한 완전한 제어권을 가지며 메서드를 호출할 때 모든 값을 스텁할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5583-305">Now the test suite has full control over `DateTime.Now` and can stub any value when calling into the method.</span></span>
