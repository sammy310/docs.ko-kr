---
title: 선택적 단위 테스트 실행
description: 필터 식을 사용하여 .NET Core의 dotnet 테스트 명령을 통해 선택적 단위 테스트를 실행하는 방법입니다.
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728189"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="2e208-103">선택적 단위 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="2e208-103">Run selective unit tests</span></span>

<span data-ttu-id="2e208-104">.NET Core에서 `dotnet test` 명령과 함께 필터 식을 사용하여 선택적 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="2e208-105">이 문서에서는 실행되는 테스트를 필터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="2e208-106">다음 예제에서는 `dotnet test`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="2e208-107">`vstest.console.exe`를 사용하는 경우 `--filter`를 `--testcasefilter:`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="2e208-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="2e208-108">문자 이스케이프</span><span class="sxs-lookup"><span data-stu-id="2e208-108">Character escaping</span></span>

<span data-ttu-id="2e208-109">`*nix`에서 느낌표(!)를 포함하는 필터를 사용하려면 이스케이프해야 합니다. `!`가 예약되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="2e208-110">예를 들어 이 필터는 네임스페이스에 IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`가 포함되어 있으면 모든 테스트를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="2e208-111">느낌표 앞에 백슬래시가 온다는 것을 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="2e208-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="2e208-112">제네릭 형식 매개 변수의 쉼표를 포함하는 `FullyQualifiedName` 값의 경우 `%2C`를 사용하여 쉼표를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="2e208-113">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2e208-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="2e208-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="2e208-114">MSTest</span></span>

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

| <span data-ttu-id="2e208-115">식</span><span class="sxs-lookup"><span data-stu-id="2e208-115">Expression</span></span> | <span data-ttu-id="2e208-116">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="2e208-117">`FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="2e208-118">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="2e208-119">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="2e208-120">`MSTestNamespace.UnitTest1` 클래스에 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="2e208-121">**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTest1`이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="2e208-122">`MSTestNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="2e208-123">`[TestCategory("CategoryA")]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="2e208-124">`[Priority(2)]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="2e208-125">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="2e208-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2e208-126">식</span><span class="sxs-lookup"><span data-stu-id="2e208-126">Expression</span></span> | <span data-ttu-id="2e208-127">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="2e208-128">`FullyQualifiedName`에 `UnitTest1`이 **있거나** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="2e208-129">`FullyQualifiedName`에 `UnitTest1`이 **있고** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2e208-130">`UnitTest1`을 포함하는 `FullyQualifiedName`이 **있고** `TestCategory`가 `CategoryA`**이거나**, `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="2e208-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="2e208-131">xUnit</span></span>

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

| <span data-ttu-id="2e208-132">식</span><span class="sxs-lookup"><span data-stu-id="2e208-132">Expression</span></span> | <span data-ttu-id="2e208-133">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="2e208-134">`XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="2e208-135">`XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="2e208-136">표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="2e208-137">코드 예제에서 `Category` 및 `Priority` 키로 정의된 특성은 필터링에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="2e208-138">식</span><span class="sxs-lookup"><span data-stu-id="2e208-138">Expression</span></span> | <span data-ttu-id="2e208-139">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="2e208-140">`FullyQualifiedName`에 `XUnit`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="2e208-141">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="2e208-142">`[Trait("Category", "CategoryA")]`가 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="2e208-143">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="2e208-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2e208-144">식</span><span class="sxs-lookup"><span data-stu-id="2e208-144">Expression</span></span> | <span data-ttu-id="2e208-145">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="2e208-146">`FullyQualifiedName`에 `TestClass1`이 **있거나** `Category`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="2e208-147">`FullyQualifiedName`에 `TestClass1`이 **있고** `Category`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2e208-148">`TestClass1`을 포함하는 `FullyQualifiedName`이 **있고** `Category`가 `CategoryA`**이거나**, `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="2e208-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="2e208-149">NUnit</span></span>

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

| <span data-ttu-id="2e208-150">식</span><span class="sxs-lookup"><span data-stu-id="2e208-150">Expression</span></span> | <span data-ttu-id="2e208-151">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="2e208-152">`FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="2e208-153">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="2e208-154">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="2e208-155">`NUnitNamespace.UnitTest1` 클래스에 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="2e208-156">`NUnitNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="2e208-157">`[Category("CategoryA")]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="2e208-158">`[Priority(2)]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="2e208-159">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="2e208-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2e208-160">식</span><span class="sxs-lookup"><span data-stu-id="2e208-160">Expression</span></span> | <span data-ttu-id="2e208-161">결과</span><span class="sxs-lookup"><span data-stu-id="2e208-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="2e208-162">`FullyQualifiedName`에 `UnitTest1`이 **있거나** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="2e208-163">`FullyQualifiedName`에 `UnitTest1`이 **있고** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2e208-164">`UnitTest1`을 포함하는 `FullyQualifiedName`이 **있고** `TestCategory`가 `CategoryA`**이거나**, `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e208-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="2e208-165">자세한 내용은 [TestCase 필터](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e208-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
