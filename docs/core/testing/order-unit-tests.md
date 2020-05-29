---
title: 단위 테스트 순서 지정
description: .NET Core를 사용하여 단위 테스트의 순서를 지정하는 방법을 알아봅니다.
author: IEvangelist
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: ce0d01c924075ffcc9ad49ef8aca49222c10c921
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83704534"
---
# <a name="order-unit-tests"></a><span data-ttu-id="24157-103">단위 테스트 순서 지정</span><span class="sxs-lookup"><span data-stu-id="24157-103">Order unit tests</span></span>

<span data-ttu-id="24157-104">경우에 따라 단위 테스트를 특정 순서로 실행해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24157-104">Occasionally, you may want to have unit tests run in a specific order.</span></span> <span data-ttu-id="24157-105">이상적으로는 단위 테스트가 실행되는 순서가 중요하지 _않아야_ 하며 단위 테스트 순서를 사용하지 않는 것이 [모범 사례](unit-testing-best-practices.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="24157-105">Ideally, the order in which unit tests run should _not_ matter, and it is [best practice](unit-testing-best-practices.md) to avoid ordering unit tests.</span></span> <span data-ttu-id="24157-106">그럼에도 단위 테스트를 수행해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24157-106">Regardless, there may be a need to do so.</span></span> <span data-ttu-id="24157-107">이 문서에서는 그러한 경우 테스트를 실행하는 순서를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="24157-107">In that case, this article demonstrates how to order test runs.</span></span>

<span data-ttu-id="24157-108">소스 코드를 찾아보려면 [.NET Core 단위 테스트 순서 지정](/samples/dotnet/samples/order-unit-tests-cs) 샘플 리포지토리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24157-108">If you prefer to browse the source code, see the [order .NET Core unit tests](/samples/dotnet/samples/order-unit-tests-cs) sample repository.</span></span>

> [!TIP]
> <span data-ttu-id="24157-109">이 문서에서 설명하는 순서 지정 기능 외에 [Visual Studio를 사용하여 사용자 지정 재생 목록 만들기](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists)를 대안으로 고려할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24157-109">In addition to the ordering capabilities outlined in this article, consider [creating custom playlists with Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) as an alternative.</span></span>

:::zone pivot="mstest"

## <a name="order-alphabetically"></a><span data-ttu-id="24157-110">사전순으로 순서 지정</span><span class="sxs-lookup"><span data-stu-id="24157-110">Order alphabetically</span></span>

<span data-ttu-id="24157-111">MSTest를 사용하면 테스트 순서가 테스트 이름을 기준으로 자동으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="24157-111">With MSTest, tests are automatically ordered by their test name.</span></span>

> [!NOTE]
> <span data-ttu-id="24157-112">`2`가 `14`보다 작지만 `Test14`라는 테스트는 `Test2`보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="24157-112">A test named `Test14` will run before `Test2` even though the number  `2` is less than `14`.</span></span> <span data-ttu-id="24157-113">이는 테스트 이름 순서 지정이 테스트의 텍스트 이름을 사용하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="24157-113">This is because, test name ordering uses the text name of the test.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

<span data-ttu-id="24157-114">xUnit 테스트 프레임워크를 사용하면 테스트 실행 순서를 보다 세밀하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24157-114">The xUnit test framework allows for more granularity and control of test run order.</span></span> <span data-ttu-id="24157-115">클래스 또는 테스트 컬렉션에 대한 테스트 사례의 순서를 제어하려면 `ITestCaseOrderer` 및 `ITestCollectionOrderer` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-115">You implement the `ITestCaseOrderer` and `ITestCollectionOrderer` interfaces to control the order of test cases for a class, or test collections.</span></span>

## <a name="order-by-test-case-alphabetically"></a><span data-ttu-id="24157-116">사전순으로 테스트 사례 순서 지정</span><span class="sxs-lookup"><span data-stu-id="24157-116">Order by test case alphabetically</span></span>

<span data-ttu-id="24157-117">테스트 사례를 해당 메서드 이름에 따라 순서를 지정하려면 `ITestCaseOrderer`를 구현하고 순서 지정 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-117">To order test cases by their method name, you implement the `ITestCaseOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

<span data-ttu-id="24157-118">그런 다음 테스트 클래스에서 `TestCaseOrdererAttribute`를 사용하여 테스트 사례 순서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-118">Then in a test class you set the test case order with the `TestCaseOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a><span data-ttu-id="24157-119">사전순으로 컬렉션 순서 지정</span><span class="sxs-lookup"><span data-stu-id="24157-119">Order by collection alphabetically</span></span>

<span data-ttu-id="24157-120">테스트 컬렉션을 해당 표시 이름에 따라 순서를 지정하려면 `ITestCollectionOrderer`을 구현하고 순서 지정 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-120">To order test collections by their display name, you implement the `ITestCollectionOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

<span data-ttu-id="24157-121">테스트 컬렉션은 잠재적으로 병렬로 실행되므로 `CollectionBehaviorAttribute`를 사용하여 컬렉션의 테스트 병렬 처리를 명시적으로 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-121">Since test collections potentially run in parallel, you must explicitly disable test parallelization of the collections with the `CollectionBehaviorAttribute`.</span></span> <span data-ttu-id="24157-122">그런 다음 `TestCollectionOrdererAttribute`에 대한 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-122">Then specify the implementation to the `TestCollectionOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a><span data-ttu-id="24157-123">사용자 지정 특성별로 순서 지정</span><span class="sxs-lookup"><span data-stu-id="24157-123">Order by custom attribute</span></span>

<span data-ttu-id="24157-124">사용자 지정 특성을 사용하는 xUnit 테스트의 순서를 지정하려면 먼저 사용할 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-124">To order xUnit tests with custom attributes, you first need an attribute to rely on.</span></span> <span data-ttu-id="24157-125">다음과 같이 `TestPriorityAttribute`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-125">Define a `TestPriorityAttribute` as follows:</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

<span data-ttu-id="24157-126">다음으로 `ITestCaseOrderer` 인터페이스의 다음 `PriorityOrderer` 구현을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-126">Next, consider the following `PriorityOrderer` implementation of the `ITestCaseOrderer` interface.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

<span data-ttu-id="24157-127">그런 다음 테스트 클래스에서 `TestCaseOrdererAttribute`를 `PriorityOrderer`로 지정하여 테스트 사례 순서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-127">Then in a test class you set the test case order with the `TestCaseOrdererAttribute` to the `PriorityOrderer`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a><span data-ttu-id="24157-128">우선 순위로 순서 지정</span><span class="sxs-lookup"><span data-stu-id="24157-128">Order by priority</span></span>

<span data-ttu-id="24157-129">명시적으로 테스트의 순서를 지정하기 위해 NUnit은 [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-129">To order tests explicitly, NUnit provides an [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute).</span></span> <span data-ttu-id="24157-130">이 특성이 지정된 테스트는 그렇지 않은 테스트보다 먼저 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="24157-130">Tests with this attribute are started before tests without.</span></span> <span data-ttu-id="24157-131">순서 값은 단위 테스트를 실행하는 순서를 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24157-131">The order value is used to determined the order to run the unit tests.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a><span data-ttu-id="24157-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="24157-132">Next Steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="24157-133">단위 테스트 모범 사례</span><span class="sxs-lookup"><span data-stu-id="24157-133">Unit testing best practices</span></span>](unit-testing-best-practices.md)
