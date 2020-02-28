---
title: 선택적 단위 테스트 실행
description: 필터 식을 사용하여 .NET Core의 dotnet 테스트 명령을 통해 선택적 단위 테스트를 실행하는 방법입니다.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543510"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="cb4f9-103">선택적 단위 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="cb4f9-103">Running selective unit tests</span></span>

<span data-ttu-id="cb4f9-104">.NET Core에서 `dotnet test` 명령과 함께 필터 식을 사용하여 선택적 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="cb4f9-105">이 문서에서는 실행되는 테스트를 필터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="cb4f9-106">다음 예제에서는 `dotnet test`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="cb4f9-107">`vstest.console.exe`를 사용하는 경우 `--filter`를 `--testcasefilter:`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="cb4f9-108">`*nix`에서 느낌표(!)를 포함하는 필터를 사용하려면 이스케이프해야 합니다. `!`가 예약되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="cb4f9-109">예를 들어 이 필터는 네임스페이스에 IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`가 포함되어 있으면 모든 테스트를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="cb4f9-110">느낌표 앞에 백슬래시가 온다는 것을 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="cb4f9-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="cb4f9-111">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="cb4f9-112">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-112">Expression</span></span> | <span data-ttu-id="cb4f9-113">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="cb4f9-114">`FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="cb4f9-115">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cb4f9-116">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="cb4f9-117">클래스 `MSTestNamespace.UnitTest1`에 속하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="cb4f9-118">**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTest1`이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cb4f9-119">`MSTestNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cb4f9-120">`[TestCategory("CategoryA")]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cb4f9-121">`[Priority(2)]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="cb4f9-122">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="cb4f9-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cb4f9-123">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-123">Expression</span></span> | <span data-ttu-id="cb4f9-124">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="cb4f9-125">`FullyQualifiedName`에 `UnitTest1`이 **있거나**`TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="cb4f9-126">`FullyQualifiedName`에 `UnitTest1`**이 있고**`TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cb4f9-127">`UnitTest1`을 포함하는 `FullyQualifiedName` **이 있고** `TestCategory`가 `CategoryA` **이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="cb4f9-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="cb4f9-128">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="cb4f9-129">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-129">Expression</span></span> | <span data-ttu-id="cb4f9-130">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cb4f9-131">`XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cb4f9-132">`XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="cb4f9-133">표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="cb4f9-134">코드 예제에서 `Category` 및 `Priority` 키로 정의된 특성은 필터링에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="cb4f9-135">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-135">Expression</span></span> | <span data-ttu-id="cb4f9-136">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="cb4f9-137">`FullyQualifiedName`에 `XUnit`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="cb4f9-138">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="cb4f9-139">`[Trait("Category", "CategoryA")]`가 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="cb4f9-140">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="cb4f9-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cb4f9-141">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-141">Expression</span></span> | <span data-ttu-id="cb4f9-142">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="cb4f9-143">`FullyQualifiedName`에 `TestClass1`이 **있거나**`Category`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="cb4f9-144">`FullyQualifiedName`에 `TestClass1` **이 있고** `Category`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cb4f9-145">`TestClass1`을 포함하는 `FullyQualifiedName` **이 있고** `Category`가 `CategoryA` **이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="cb4f9-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="cb4f9-146">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="cb4f9-147">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-147">Expression</span></span> | <span data-ttu-id="cb4f9-148">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="cb4f9-149">`FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="cb4f9-150">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cb4f9-151">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="cb4f9-152">클래스 `NUnitNamespace.UnitTest1`에 속하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cb4f9-153">`NUnitNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cb4f9-154">`[Category("CategoryA")]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cb4f9-155">`[Priority(2)]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="cb4f9-156">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="cb4f9-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cb4f9-157">식</span><span class="sxs-lookup"><span data-stu-id="cb4f9-157">Expression</span></span> | <span data-ttu-id="cb4f9-158">결과</span><span class="sxs-lookup"><span data-stu-id="cb4f9-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="cb4f9-159">`FullyQualifiedName`에 `UnitTest1`이 **있거나**`TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="cb4f9-160">`FullyQualifiedName`에 `UnitTest1`**이 있고**`TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cb4f9-161">`UnitTest1`을 포함하는 `FullyQualifiedName` **이 있고** `TestCategory`가 `CategoryA` **이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
