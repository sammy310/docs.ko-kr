---
title: dotnet test 및 NUnit을 사용하여 .NET Core에서 Visual Basic 단위 테스트
description: NUnit를 사용하여 샘플 Visual Basic 솔루션을 단계별로 빌드하는 대화형 환경을 통해 .NET Core의 단위 테스트 개념을 알아봅니다.
author: rprouse
ms.date: 10/04/2018
ms.openlocfilehash: a33447457344b241b4c2376d777b0deb7f556874
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240924"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="44d43-103">dotnet test 및 NUnit을 사용하여 Visual Basic .NET Core 라이브러리 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="44d43-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="44d43-104">이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="44d43-105">미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/).</span><span class="sxs-lookup"><span data-stu-id="44d43-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="44d43-106">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d43-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="44d43-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="44d43-107">Prerequisites</span></span>

- <span data-ttu-id="44d43-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="44d43-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="44d43-109">선택하는 텍스트 편집기 또는 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="44d43-110">소스 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="44d43-110">Creating the source project</span></span>

<span data-ttu-id="44d43-111">셸 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-111">Open a shell window.</span></span> <span data-ttu-id="44d43-112">솔루션을 저장하기 위한 *unit-testing-vb-nunit*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-112">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="44d43-113">이 새 디렉터리 내에서 다음 명령을 실행하여 클래스 라이브러리 및 테스트 프로젝트에 대한 새 솔루션 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="44d43-114">다음으로 *PrimeService* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="44d43-115">다음 개요는 지금까지의 파일 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-115">The following outline shows the file structure so far:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="44d43-116">*PrimeService*를 현재 디렉터리로 만들고 다음 명령을 실행하여 소스 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib -lang VB
```

<span data-ttu-id="44d43-117">*Class1.VB*의 이름을 *PrimeService.VB*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-117">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="44d43-118">다음과 같이 `PrimeService` 클래스의 실패 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-118">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first.")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="44d43-119">디렉터리를 다시 *unit-testing-vb-using-mstest* 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-119">Change the directory back to the *unit-testing-vb-using-mstest* directory.</span></span> <span data-ttu-id="44d43-120">다음 명령을 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="44d43-121">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="44d43-121">Creating the test project</span></span>

<span data-ttu-id="44d43-122">다음으로 *PrimeService.Tests* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="44d43-123">다음 개요에는 디렉터리 구조가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="44d43-124">*PrimeService.Tests* 디렉터리를 현재 디렉터리로 만들고 다음 명령을 사용하여 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit -lang VB
```

<span data-ttu-id="44d43-125">[dotnet new](../tools/dotnet-new.md) 명령은 NUnit를 테스트 라이브러리로 사용하는 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="44d43-126">생성된 템플릿은 *PrimeServiceTests.vbproj* 파일에 Test Runner를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-126">The generated template configures the test runner in the *PrimeServiceTests.vbproj* file:</span></span>

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

<span data-ttu-id="44d43-127">테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="44d43-128">이전 단계의 `dotnet new`는 NUnit 및 NUnit 테스트 어댑터를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-128">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="44d43-129">이제 `PrimeService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="44d43-130">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="44d43-131">GitHub의 [샘플 리포지토리](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj)에서 전체 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="44d43-132">최종 솔루션 레이아웃은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-132">You have the following final solution layout:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

<span data-ttu-id="44d43-133">*unit-testing-vb-nunit* 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-133">Execute the following command in the *unit-testing-vb-nunit* directory:</span></span>

```dotnetcli
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="44d43-134">첫 번째 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="44d43-134">Creating the first test</span></span>

<span data-ttu-id="44d43-135">하나의 실패 테스트를 작성하고, 테스트가 성공하도록 만듭니다. 이 작업을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="44d43-136">*PrimeService.Tests* 디렉터리에서 *UnitTest1.vb* 파일의 이름을 *PrimeService_IsPrimeShould.VB*로 변경하고 전체 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.vb* file to *PrimeService_IsPrimeShould.VB* and replace its entire contents with the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="44d43-137">`<TestFixture>` 특성은 테스트가 포함된 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-137">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="44d43-138">`<Test>` 특성은 Test Runner에서 실행하는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-138">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="44d43-139">*unit-testing-vb-nunit*에서 [`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-139">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="44d43-140">NUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="44d43-141">`dotnet test`는 만든 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="44d43-142">테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-142">Your test fails.</span></span> <span data-ttu-id="44d43-143">구현은 아직 만들지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="44d43-144">`PrimeService` 클래스에서 작동하는 가장 간단한 코드를 작성하여 이 테스트를 통과시킵니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="44d43-145">*unit-testing-vb-nunit* 디렉터리에서 `dotnet test`를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-145">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="44d43-146">`dotnet test` 명령은 `PrimeService` 프로젝트에 대한 빌드를 실행한 다음 `PrimeService.Tests` 프로젝트에 대한 빌드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="44d43-147">두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="44d43-148">전달합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="44d43-149">더 많은 기능 추가</span><span class="sxs-lookup"><span data-stu-id="44d43-149">Adding more features</span></span>

<span data-ttu-id="44d43-150">이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="44d43-151">소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1).</span><span class="sxs-lookup"><span data-stu-id="44d43-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="44d43-152">이러한 사례를 `<Test>` 특성과 함께 새 테스트로 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-152">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="44d43-153">비슷한 테스트 모음을 작성하는 데 사용할 수 있는 다른 xUnit 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-153">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="44d43-154">`<TestCase>` 특성은 같은 코드를 실행하는 테스트 모음을 나타내지만, 서로 다른 입력 인수를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-154">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="44d43-155">`<TestCase>` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-155">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="44d43-156">새 테스트를 만드는 대신 이 두 가지 특성을 적용하여 2보다 작은 일부 값(가장 낮은 소수)을 테스트하는 일련의 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-156">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="44d43-157">`dotnet test`를 실행합니다. 그러면 이러한 테스트 중 2개가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="44d43-158">모든 테스트를 통과하려면 *PrimeServices.cs* 파일에서 `Main` 메서드의 시작 부분에 있는 `if` 절을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-158">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeServices.cs* file:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="44d43-159">기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="44d43-160">[테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb)을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="44d43-161">작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="44d43-162">새 패키지 및 테스트 추가가 정상 워크플로에 포함되도록 솔루션을 구조화했습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="44d43-163">애플리케이션의 목표를 해결하는 데 대부분의 시간과 노력을 들였습니다.</span><span class="sxs-lookup"><span data-stu-id="44d43-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
