---
title: 선택적 단위 테스트 실행
description: 필터 식을 사용하여 .NET Core의 dotnet 테스트 명령을 통해 선택적 단위 테스트를 실행하는 방법입니다.
author: smadala
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: 6a6bbb0687742d1e3288d64fb88f6825dc678e28
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702987"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="4e066-103">선택적 단위 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="4e066-103">Run selective unit tests</span></span>

<span data-ttu-id="4e066-104">.NET Core에서 [`dotnet test`](../tools/dotnet-test.md) 명령과 함께 필터 식을 사용하여 선택적 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-104">With the [`dotnet test`](../tools/dotnet-test.md) command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="4e066-105">이 문서에서는 실행되는 테스트를 필터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="4e066-106">다음 예제에서는 `dotnet test`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="4e066-107">`vstest.console.exe`를 사용하는 경우 `--filter`를 `--testcasefilter:`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="4e066-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="4e066-108">문자 이스케이프</span><span class="sxs-lookup"><span data-stu-id="4e066-108">Character escaping</span></span>

<span data-ttu-id="4e066-109">`*nix`에서 느낌표(`!`)를 포함하는 필터를 사용하려면 이스케이프해야 합니다. `!`가 예약되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-109">Using filters that include exclamation mark `!` on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="4e066-110">예를 들어 다음 필터는 네임스페이스에 IntegrationTests가 포함되어 있으면 모든 테스트를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-110">For example, this filter skips all tests if the namespace contains IntegrationTests:</span></span>

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> <span data-ttu-id="4e066-111">이스케이프된 문자임을 나타내기 위해 느낌표 앞에 백슬래시가 나옵니다(`\!`).</span><span class="sxs-lookup"><span data-stu-id="4e066-111">The backslash precedes the exclamation mark to indicate it is an escaped character `\!`.</span></span>

<span data-ttu-id="4e066-112">제네릭 형식 매개 변수의 쉼표를 포함하는 `FullyQualifiedName` 값의 경우 `%2C`를 사용하여 쉼표를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="4e066-113">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4e066-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

:::zone pivot="mstest"

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod, Priority(1), TestCategory("CategoryA")]
        public void TestMethod1()
        {
        }

        [TestMethod, Priority(2)]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="4e066-114">식</span><span class="sxs-lookup"><span data-stu-id="4e066-114">Expression</span></span> | <span data-ttu-id="4e066-115">결과</span><span class="sxs-lookup"><span data-stu-id="4e066-115">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="4e066-116"><xref:System.Reflection.Module.FullyQualifiedName>에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-116">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="4e066-117">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-117">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="4e066-118">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-118">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="4e066-119">`MSTestNamespace.UnitTest1` 클래스에 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-119">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="4e066-120">**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTest1`이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-120">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="4e066-121">`MSTestNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-121">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="4e066-122">`[TestCategory("CategoryA")]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-122">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="4e066-123">`[Priority(2)]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-123">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="4e066-124">조건부 연산자 `|` 및 `&`를 사용하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-124">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="4e066-125"><xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`가 포함되거나 **또는** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>가 `"CategoryA"`인 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-125">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> is `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="4e066-126"><xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>가 `"CategoryA"`인 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-126">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="4e066-127"><xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>가 `"CategoryA"`이거나, **또는** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>의 우선 순위가 `1`인 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-127">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"` **or** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> with a priority of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="xunit"

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Fact, Trait("Priority", "1"), Trait("Category", "CategoryA")]
        public void Test1()
        {
        }

        [Fact, Trait("Priority", "2")]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="4e066-128">식</span><span class="sxs-lookup"><span data-stu-id="4e066-128">Expression</span></span> | <span data-ttu-id="4e066-129">결과</span><span class="sxs-lookup"><span data-stu-id="4e066-129">Result</span></span> |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="4e066-130">`XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-130">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="4e066-131">`XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-131">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="4e066-132">표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-132">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="4e066-133">코드 예제에서 `"Category"` 및 `"Priority"` 키로 정의된 특성은 필터링에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-133">In the code example, the defined traits with keys `"Category"` and `"Priority"` can be used for filtering.</span></span>

| <span data-ttu-id="4e066-134">식</span><span class="sxs-lookup"><span data-stu-id="4e066-134">Expression</span></span> | <span data-ttu-id="4e066-135">결과</span><span class="sxs-lookup"><span data-stu-id="4e066-135">Result</span></span> |
|--|--|
| `dotnet test --filter XUnit` | <span data-ttu-id="4e066-136"><xref:System.Reflection.Module.FullyQualifiedName>에 `XUnit`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-136">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `XUnit`.</span></span>  <span data-ttu-id="4e066-137">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-137">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="4e066-138">`[Trait("Category", "CategoryA")]`가 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-138">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="4e066-139">조건부 연산자 `|` 및 `&`를 사용하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-139">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="4e066-140"><xref:System.Reflection.Module.FullyQualifiedName>에 `TestClass1`이 포함되거나 **또는** `"Category"` 키의 값이 `"CategoryA"`인 `Trait`가 있는 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-140">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

<span data-ttu-id="4e066-141"><xref:System.Reflection.Module.FullyQualifiedName>에 `TestClass1`이 포함**되면서** `"Category"` 키의 값이 `"CategoryA"`인 `Trait`가 있는 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-141">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

<span data-ttu-id="4e066-142"><xref:System.Reflection.Module.FullyQualifiedName>에 `TestClass1`이 포함**되면서** `"Category"` 키의 값이 `"CategoryA"`인 `Trait`가 있거나, **또는** `"Priority"` 키의 값이 `1`인 `Trait`가 있는 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-142">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `TestClass1` **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"` **or** have a `Trait` with a key of `"Priority"` and value of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="nunit"

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Test, Property("Priority", 1), Category("CategoryA")]
        public void TestMethod1()
        {
        }

        [Test, Property("Priority", 2)]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="4e066-143">식</span><span class="sxs-lookup"><span data-stu-id="4e066-143">Expression</span></span> | <span data-ttu-id="4e066-144">결과</span><span class="sxs-lookup"><span data-stu-id="4e066-144">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="4e066-145"><xref:System.Reflection.Module.FullyQualifiedName>에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-145">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="4e066-146">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-146">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="4e066-147">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-147">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="4e066-148">`NUnitNamespace.UnitTest1` 클래스에 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-148">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="4e066-149">`NUnitNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-149">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="4e066-150">`[Category("CategoryA")]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-150">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="4e066-151">`[Priority(2)]`로 주석이 달린 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-151">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="4e066-152">조건부 연산자 `|` 및 `&`를 사용하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e066-152">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="4e066-153"><xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함되거나 **또는** `Category`가 `"CategoryA"`인 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-153">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="4e066-154"><xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** `Category`가 `"CategoryA"`인 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-154">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="4e066-155"><xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** `Category`가 `"CategoryA"`이거나, **또는** `"Priority"`의 값이 `1`인 `Property`가 있는 테스트를 실행하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4e066-155">To run tests that have either a <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a `Category` of `"CategoryA"` **or** have a `Property` with a `"Priority"` of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

<span data-ttu-id="4e066-156">자세한 내용은 [TestCase 필터](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e066-156">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

:::zone-end

## <a name="see-also"></a><span data-ttu-id="4e066-157">참조</span><span class="sxs-lookup"><span data-stu-id="4e066-157">See also</span></span>

- [<span data-ttu-id="4e066-158">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4e066-158">dotnet test</span></span>](../tools/dotnet-test.md)
- [<span data-ttu-id="4e066-159">dotnet test --filter</span><span class="sxs-lookup"><span data-stu-id="4e066-159">dotnet test --filter</span></span>](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a><span data-ttu-id="4e066-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4e066-160">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4e066-161">단위 테스트 순서 지정</span><span class="sxs-lookup"><span data-stu-id="4e066-161">Order unit tests</span></span>](order-unit-tests.md)
