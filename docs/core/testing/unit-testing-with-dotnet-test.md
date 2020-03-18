---
title: dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 C# 단위 테스트
description: dotnet test 및 xUnit을 사용하여 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 C# 및 .NET Core의 단위 테스트 개념을 알아봅니다.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: c9e3d63a2cf4f560591459833340b729ffec1b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240898"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="9c7aa-103">dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 C# 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="9c7aa-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="9c7aa-104">이 자습서에서는 단위 테스트 프로젝트 및 소스 코드 프로젝트를 포함하는 솔루션을 빌드하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-104">This tutorial shows how to build a solution containing a unit test project and source code project.</span></span> <span data-ttu-id="9c7aa-105">미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려면 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-105">To follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span></span> <span data-ttu-id="9c7aa-106">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="9c7aa-107">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="9c7aa-107">Create the solution</span></span>

<span data-ttu-id="9c7aa-108">이 섹션에서는 원본 및 테스트 프로젝트를 포함하는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-108">In this section, a solution is created that contains the source and test projects.</span></span> <span data-ttu-id="9c7aa-109">완료된 솔루션은 다음과 같은 디렉터리 구조를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-109">The completed solution has the following directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.cs
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.cs
        PrimeServiceTests.csproj
```

<span data-ttu-id="9c7aa-110">다음 지침에서는 테스트 솔루션을 만드는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-110">The following instructions provide the steps to create the test solution.</span></span> <span data-ttu-id="9c7aa-111">한 단계로 테스트 솔루션을 만드는 방법에 대한 지침은 [테스트 솔루션을 만드는 명령](#create-test-cmd)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-111">See [Commands to create test solution](#create-test-cmd) for instructions to create the test solution in one step.</span></span>

* <span data-ttu-id="9c7aa-112">셸 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-112">Open a shell window.</span></span>
* <span data-ttu-id="9c7aa-113">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-113">Run the following command:</span></span>

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  <span data-ttu-id="9c7aa-114">[`dotnet new sln`](../tools/dotnet-new.md) 명령은 *unit-testing-using-dotnet-test* 디렉터리에서 새 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-114">The [`dotnet new sln`](../tools/dotnet-new.md) command creates a new solution in the *unit-testing-using-dotnet-test* directory.</span></span>
* <span data-ttu-id="9c7aa-115">디렉터리를 *unit-testing-using-dotnet-test* 폴더로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-115">Change directory to the *unit-testing-using-dotnet-test* folder.</span></span>
* <span data-ttu-id="9c7aa-116">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-116">Run the following command:</span></span>

  ```dotnetcli
  dotnet new classlib -o PrimeService
  ```

   <span data-ttu-id="9c7aa-117">[`dotnet new classlib`](../tools/dotnet-new.md) 명령은 *PrimeService* 폴더에 새 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-117">The [`dotnet new classlib`](../tools/dotnet-new.md) command creates a new class library project  in the *PrimeService* folder.</span></span> <span data-ttu-id="9c7aa-118">새 클래스 라이브러리에는 테스트할 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-118">The new class library will contain the code to be tested.</span></span>
* <span data-ttu-id="9c7aa-119">*Class1.cs*의 이름을 *PrimeService.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-119">Rename *Class1.cs* to *PrimeService.cs*.</span></span>
* <span data-ttu-id="9c7aa-120">*PrimeService.cs*의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-120">Replace the code in *PrimeService.cs* with the following code:</span></span>
  
  ```csharp
    using System;

    namespace Prime.Services
    {
        public class PrimeService
        {
            public bool IsPrime(int candidate)
            {
                throw new NotImplementedException("Not implemented.");
            }
        }
    }
  ```

* <span data-ttu-id="9c7aa-121">위의 코드는:</span><span class="sxs-lookup"><span data-stu-id="9c7aa-121">The preceding code:</span></span>
  * <span data-ttu-id="9c7aa-122">구현되지 않았음을 나타내는 메시지와 함께 <xref:System.NotImplementedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-122">Throws a <xref:System.NotImplementedException> with a message indicating it's not implemented.</span></span>
  * <span data-ttu-id="9c7aa-123">자습서의 뒷부분에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-123">Is updated later in the tutorial.</span></span>

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* <span data-ttu-id="9c7aa-124">*unit-testing-using-dotnet-test* 디렉터리에서 다음 명령을 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-124">In the *unit-testing-using-dotnet-test* directory, run the following command to add the class library project to the solution:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
  ```

* <span data-ttu-id="9c7aa-125">다음 명령을 실행하여 *PrimeService.Tests* 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-125">Create the *PrimeService.Tests* project by running the following command:</span></span>

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* <span data-ttu-id="9c7aa-126">이전 명령은</span><span class="sxs-lookup"><span data-stu-id="9c7aa-126">The preceding command:</span></span>
  * <span data-ttu-id="9c7aa-127">*PrimeService.Tests* 디렉터리에 *PrimeService.Tests* 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-127">Creates the *PrimeService.Tests* project in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="9c7aa-128">테스트 프로젝트는 [xUnit](https://xunit.github.io/)을 테스트 라이브러리로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-128">The test project uses [xUnit](https://xunit.github.io/) as the test library.</span></span>
  * <span data-ttu-id="9c7aa-129">프로젝트 파일에 다음 `<PackageReference />` 요소를 추가하여 Test Runner를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-129">Configures the test runner by adding the following `<PackageReference />`elements to the project file:</span></span>
    * <span data-ttu-id="9c7aa-130">"Microsoft.NET.Test.Sdk"</span><span class="sxs-lookup"><span data-stu-id="9c7aa-130">"Microsoft.NET.Test.Sdk"</span></span>
    * <span data-ttu-id="9c7aa-131">"xunit"</span><span class="sxs-lookup"><span data-stu-id="9c7aa-131">"xunit"</span></span>
    * <span data-ttu-id="9c7aa-132">"xunit.runner.visualstudio"</span><span class="sxs-lookup"><span data-stu-id="9c7aa-132">"xunit.runner.visualstudio"</span></span>

* <span data-ttu-id="9c7aa-133">다음 명령을 실행하여 솔루션 파일에 테스트 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-133">Add the test project to the solution file by running the following command:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* <span data-ttu-id="9c7aa-134">`PrimeService` 클래스 라이브러리를 *PrimeService.Tests* 프로젝트에 대한 종속성으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-134">Add the `PrimeService` class library as a dependency to the *PrimeService.Tests* project:</span></span>

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a><span data-ttu-id="9c7aa-135">솔루션을 만드는 명령</span><span class="sxs-lookup"><span data-stu-id="9c7aa-135">Commands to create the solution</span></span>

<span data-ttu-id="9c7aa-136">이 섹션에는 이전 섹션의 모든 명령이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-136">This section summarizes all the commands in the previous section.</span></span> <span data-ttu-id="9c7aa-137">이전 섹션의 단계를 완료한 경우에는 이 섹션을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-137">Skip this section if you've completed the steps in the previous section.</span></span>

<span data-ttu-id="9c7aa-138">다음 명령은 Windows 머신에서 테스트 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-138">The following commands create the test solution on a windows machine.</span></span> <span data-ttu-id="9c7aa-139">macOS 및 Unix의 경우 `ren` 명령을 `ren` OS 버전으로 업데이트하여 파일 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-139">For macOS and Unix, update the `ren` command to the OS version of `ren` to rename a file:</span></span>

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.cs PrimeService.cs
dotnet sln add ./PrimeService/PrimeService.csproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

<span data-ttu-id="9c7aa-140">이전 섹션에 있는 "*PrimeService.cs*의 코드를 다음 코드로 바꾸기" 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-140">Follow the instructions for "Replace the code in *PrimeService.cs* with the following code" in the previous section.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="9c7aa-141">테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="9c7aa-141">Create a test</span></span>

<span data-ttu-id="9c7aa-142">TDD(테스트 기반 개발)에서 널리 사용되는 방식은 대상 코드를 구현하기 전에 테스트를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-142">A popular approach in test driven development (TDD) is to write a test before implementing the target code.</span></span> <span data-ttu-id="9c7aa-143">이 자습서에서는 TDD 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-143">This tutorial uses the TDD approach.</span></span> <span data-ttu-id="9c7aa-144">`IsPrime` 메서드는 호출할 수 있지만 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-144">The `IsPrime` method is callable, but not implemented.</span></span> <span data-ttu-id="9c7aa-145">`IsPrime`에 대한 테스트 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-145">A test call to `IsPrime` fails.</span></span> <span data-ttu-id="9c7aa-146">TDD를 사용하면 실패하는 것으로 알려진 테스트가 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-146">With TDD, a test is written that is known to fail.</span></span> <span data-ttu-id="9c7aa-147">테스트가 통과하도록 대상 코드가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-147">The target code is updated to make the test pass.</span></span> <span data-ttu-id="9c7aa-148">이 방식을 계속 반복하여 실패한 테스트를 작성한 후 대상 코드를 업데이트하여 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-148">You keep repeating this approach, writing a failing test and then updating the target code to pass.</span></span>

<span data-ttu-id="9c7aa-149">*PrimeService.Tests* 프로젝트 업데이트:</span><span class="sxs-lookup"><span data-stu-id="9c7aa-149">Update the *PrimeService.Tests* project:</span></span>

* <span data-ttu-id="9c7aa-150">*PrimeService.Tests/UnitTest1.cs*를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-150">Delete *PrimeService.Tests/UnitTest1.cs*.</span></span>
* <span data-ttu-id="9c7aa-151">*PrimeService.Tests/PrimeService_IsPrimeShould.cs* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-151">Create a *PrimeService.Tests/PrimeService_IsPrimeShould.cs*  file.</span></span>
* <span data-ttu-id="9c7aa-152">*PrimeService_IsPrimeShould.cs*의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-152">Replace the code in *PrimeService_IsPrimeShould.cs* with the following code:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="9c7aa-153">`[Fact]` 특성은 Test Runner에서 실행하는 테스트 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-153">The `[Fact]` attribute declares a test method that's run by the test runner.</span></span> <span data-ttu-id="9c7aa-154">*Primeservice.tests* 폴더에서 `dotnet test`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-154">From the *PrimeService.Tests* folder, run `dotnet test`.</span></span> <span data-ttu-id="9c7aa-155">[dotnet test](../tools/dotnet-test.md) 명령은 두 프로젝트를 모두 빌드하고 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-155">The [dotnet test](../tools/dotnet-test.md) command builds both projects and runs the tests.</span></span> <span data-ttu-id="9c7aa-156">xUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-156">The xUnit test runner contains the program entry point to run the tests.</span></span> <span data-ttu-id="9c7aa-157">`dotnet test`는 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-157">`dotnet test` starts the test runner using the unit test project.</span></span>

<span data-ttu-id="9c7aa-158">`IsPrime`이 구현되지 않았기 때문에 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-158">The test fails because `IsPrime` hasn't been implemented.</span></span> <span data-ttu-id="9c7aa-159">TDD 방식을 사용하여 이 테스트가 통과할 수 있는 코드만 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-159">Using the TDD approach, write only enough code so this test passes.</span></span> <span data-ttu-id="9c7aa-160">다음 코드를 사용하여 `IsPrime`을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-160">Update `IsPrime` with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

<span data-ttu-id="9c7aa-161">`dotnet test`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-161">Run `dotnet test`.</span></span> <span data-ttu-id="9c7aa-162">테스트가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-162">The test passes.</span></span>

### <a name="add-more-tests"></a><span data-ttu-id="9c7aa-163">더 많은 테스트 추가</span><span class="sxs-lookup"><span data-stu-id="9c7aa-163">Add more tests</span></span>

<span data-ttu-id="9c7aa-164">0 및 -1에 대한 소수 테스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-164">Add prime number tests for 0 and -1.</span></span> <span data-ttu-id="9c7aa-165">이전 테스트를 복사하고 다음 코드를 변경하여 0 및 -1을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-165">You could copy the preceding test and change the following code to use 0 and -1:</span></span>

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

<span data-ttu-id="9c7aa-166">매개 변수만 변경될 때 테스트 코드를 복사하면 코드 중복 및 테스트 블로트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-166">Copying test code when only a parameter changes results in code duplication and test bloat.</span></span> <span data-ttu-id="9c7aa-167">다음 xUnit 특성은 유사한 테스트 모음을 작성하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-167">The following xUnit attributes enable writing a suite of similar tests:</span></span>

- <span data-ttu-id="9c7aa-168">`[Theory]`는 같은 코드를 실행하지만, 다른 입력 인수가 포함된 테스트 모음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-168">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>

- <span data-ttu-id="9c7aa-169">`[InlineData]` 특성은 해당 입력에 대한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-169">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="9c7aa-170">새 테스트를 만들지 않고 앞의 xUnit 특성을 적용하여 단일 이론을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-170">Rather than creating new tests, apply the preceding xUnit attributes to create a single theory.</span></span> <span data-ttu-id="9c7aa-171">코드 바꾸기 대상:</span><span class="sxs-lookup"><span data-stu-id="9c7aa-171">Replace the following code:</span></span>

```csharp
[Fact]
public void IsPrime_InputIs1_ReturnFalse()
{
    var result = _primeService.IsPrime(1);

    Assert.False(result, "1 should not be prime");
}
```

<span data-ttu-id="9c7aa-172">다음 코드와 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-172">with the following code:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-dotnet-test/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="9c7aa-173">앞의 코드에서 `[Theory]` 및 `[InlineData]`를 사용하여 2보다 작은 몇 가지 값을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-173">In the preceding code, `[Theory]` and `[InlineData]` enable testing several values less than two.</span></span> <span data-ttu-id="9c7aa-174">2는 가장 작은 소수입니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-174">Two is the smallest prime number.</span></span>

<span data-ttu-id="9c7aa-175">`dotnet test`를 실행하면 두 가지 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-175">Run `dotnet test`, two of the tests fail.</span></span> <span data-ttu-id="9c7aa-176">모든 테스트를 통과하도록 하려면 다음 코드를 사용하여 `IsPrime` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-176">To make all of the tests pass, update the `IsPrime` method with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate < 2)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

<span data-ttu-id="9c7aa-177">TDD 방식에 따라 실패하는 테스트를 더 추가한 후 대상 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-177">Following the TDD approach, add more failing tests, then update the target code.</span></span> <span data-ttu-id="9c7aa-178">[테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-178">See the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="9c7aa-179">완료된 `IsPrime` 메서드는 소수판별 테스트를 위한 효율적인 알고리즘이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9c7aa-179">The completed `IsPrime` method is not an efficient algorithm for testing primality.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9c7aa-180">추가 자료</span><span class="sxs-lookup"><span data-stu-id="9c7aa-180">Additional resources</span></span>

- [<span data-ttu-id="9c7aa-181">xUnit.net 공식 사이트</span><span class="sxs-lookup"><span data-stu-id="9c7aa-181">xUnit.net official site</span></span>](https://xunit.github.io)
- [<span data-ttu-id="9c7aa-182">ASP.NET Core에서 컨트롤러 논리 테스트</span><span class="sxs-lookup"><span data-stu-id="9c7aa-182">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
