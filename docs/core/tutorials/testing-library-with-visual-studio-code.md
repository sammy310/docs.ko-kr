---
title: Visual Studio Code를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트
description: .NET Core 클래스 라이브러리에 대한 단위 테스트 프로젝트를 만듭니다. .NET Core 클래스 라이브러리가 단위 테스트에서 올바르게 작동하는지 확인합니다.
ms.date: 06/08/2020
ms.openlocfilehash: a61fd952eea2dec0d5a9f351d3f3d01c738e8fad
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701035"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a><span data-ttu-id="6b85b-104">자습서: Visual Studio Code를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="6b85b-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="6b85b-105">이 자습서에서는 솔루션에 테스트 프로젝트를 추가하여 단위 테스트를 자동화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b85b-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b85b-106">Prerequisites</span></span>

- <span data-ttu-id="6b85b-107">이 자습서는 [Visual Studio Code에서 .NET Standard 라이브러리 만들기](library-with-visual-studio-code.md)에서 만든 솔루션에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="6b85b-108">단위 테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="6b85b-108">Create a unit test project</span></span>

<span data-ttu-id="6b85b-109">단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="6b85b-110">이 자습서에서 사용하는 테스트 프레임워크는 MSTest입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-110">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="6b85b-111">[MSTest](https://github.com/Microsoft/testfx-docs)는 선택할 수 있는 세 가지 테스트 프레임워크 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-111">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="6b85b-112">다른 프레임워크는 [xUnit](https://xunit.net/)과 [nUnit](https://nunit.org/)입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-112">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="6b85b-113">Visual Studio Code를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="6b85b-114">[Visual Studio에서 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-114">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="6b85b-115">“StringLibraryTest”라는 단위 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-115">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="6b85b-116">프로젝트 템플릿에서 다음 코드를 사용하여 UnitTest1.cs 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-116">The project template creates a UnitTest1.cs file with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   <span data-ttu-id="6b85b-117">단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-117">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="6b85b-118">단위 테스트에 사용되는 형식을 포함하는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-118">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="6b85b-119"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성을 `UnitTest1` 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="6b85b-120"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성을 적용하여 `TestMethod1`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-120">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="6b85b-121">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)로 태그가 지정된 테스트 클래스에서 [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)로 태그가 지정된 각 메서드는 단위 테스트가 실행될 때 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-121">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="6b85b-122">테스트 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-122">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="6b85b-123">프로젝트 참조 추가</span><span class="sxs-lookup"><span data-stu-id="6b85b-123">Add a project reference</span></span>

<span data-ttu-id="6b85b-124">테스트 라이브러리가 `StringLibrary` 클래스에 대해 작동하도록 하기 위해 `StringLibraryTest` 프로젝트의 참조를 `StringLibrary` 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-124">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="6b85b-125">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-125">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="6b85b-126">단위 테스트 메서드 추가 및 실행</span><span class="sxs-lookup"><span data-stu-id="6b85b-126">Add and run unit test methods</span></span>

<span data-ttu-id="6b85b-127">Visual Studio는 단위 테스트를 실행할 때 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성이 표시된 클래스에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성이 표시된 각 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-127">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="6b85b-128">테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-128">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="6b85b-129">가장 일반적인 테스트는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 클래스의 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-129">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="6b85b-130">많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-130">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="6b85b-131">`Assert` 클래스에서 가장 자주 호출되는 일부 메서드는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-131">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="6b85b-132">Assert 메서드</span><span class="sxs-lookup"><span data-stu-id="6b85b-132">Assert methods</span></span>     | <span data-ttu-id="6b85b-133">기능</span><span class="sxs-lookup"><span data-stu-id="6b85b-133">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="6b85b-134">두 개의 값이나 개체가 같은지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-134">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="6b85b-135">값이나 개체가 같지 않으면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-135">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="6b85b-136">두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-136">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="6b85b-137">변수가 서로 다른 개체를 참조하면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-137">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="6b85b-138">조건이 `false`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-138">Verifies that a condition is `false`.</span></span> <span data-ttu-id="6b85b-139">조건이 `true`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-139">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="6b85b-140">개체가 `null`이 아닌지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-140">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="6b85b-141">개체가 `null`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-141">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="6b85b-142">테스트 메서드에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> 메서드를 사용하여 throw될 것으로 예상되는 예외의 유형을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-142">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="6b85b-143">지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-143">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="6b85b-144">`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-144">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="6b85b-145">이러한 경우에 메서드가 `true`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-145">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6b85b-146">마찬가지로, 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-146">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="6b85b-147">이러한 경우에 메서드가 `false`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-147">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6b85b-148">라이브러리 메서드가 문자열을 처리하므로, 이 메서드에서 [빈 문자열(`String.Empty`)](xref:System.String.Empty) 및 `null` 문자열이 성공적으로 처리되는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-148">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="6b85b-149">빈 문자열은 문자가 없고 <xref:System.String.Length>가 0인 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-149">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="6b85b-150">`null` 문자열은 초기화되지 않은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-150">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="6b85b-151">`StartsWithUpper`를 직접 정적 메서드로 호출하고 단일 <xref:System.String> 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-151">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="6b85b-152">또는 `null`에 할당된 `string` 변수에 대한 확장 메서드로 `StartsWithUpper`를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-152">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="6b85b-153">각 메서드가 문자열 배열의 각 요소에 대해 해당 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 메서드를 호출하는 메서드 세 개를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-153">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="6b85b-154">테스트에 실패할 경우 표시될 오류 메시지를 지정할 수 있도록 하는 메서드 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-154">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="6b85b-155">메시지는 실패를 일으킨 문자열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-155">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="6b85b-156">테스트 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6b85b-156">To create the test methods:</span></span>

1. <span data-ttu-id="6b85b-157">*StringLibraryTest/UnitTest1.cs*를 열고 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-157">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="6b85b-158">`TestStartsWithUpper` 메서드의 대문자 테스트에는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-158">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="6b85b-159">`TestDoesNotStartWithUpper` 메서드의 소문자 테스트에는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-159">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="6b85b-160">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-160">Save your changes.</span></span>

1. <span data-ttu-id="6b85b-161">테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-161">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="6b85b-162">터미널 출력에 모든 테스트를 통과했음이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-162">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="6b85b-163">테스트 실패 처리</span><span class="sxs-lookup"><span data-stu-id="6b85b-163">Handle test failures</span></span>

<span data-ttu-id="6b85b-164">TDD(테스트 기반 개발)를 수행하는 경우 먼저 테스트를 작성하고 첫 실행에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-164">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="6b85b-165">그런 다음, 테스트를 성공하게 만드는 코드를 앱에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-165">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="6b85b-166">이 자습서에서는 유효성을 검사하는 앱 코드를 작성한 후에 테스트를 만들었으므로 테스트에 실패하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-166">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="6b85b-167">테스트가 실패할 것으로 예상되는 시점에 테스트가 실패하는지 확인하려면 테스트 입력에 잘못된 값을 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="6b85b-167">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="6b85b-168">`TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-168">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="6b85b-169">테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-169">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="6b85b-170">터미널 출력에 테스트 하나가 실패했음이 확인되고 실패한 테스트에 대한 오류 메시지가 제공됩니다. "Assert.IsFalse가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-170">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="6b85b-171">'Error'에 필요한 값: false, 실제: True"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-171">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="6b85b-172">이 오류 때문에 "Error" 다음에 나오는 배열의 문자열은 테스트되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-172">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
     at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper()
       in C:\Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
   Total time: 1.7825 Seconds
   ```

1. <span data-ttu-id="6b85b-173">1단계에서 추가한 "Error" 문자열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-173">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="6b85b-174">테스트를 다시 실행하면 테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-174">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="6b85b-175">라이브러리의 릴리스 버전 테스트</span><span class="sxs-lookup"><span data-stu-id="6b85b-175">Test the Release version of the library</span></span>

<span data-ttu-id="6b85b-176">라이브러리의 디버그 빌드를 실행할 때 테스트에 모두 통과했으므로 라이브러리의 릴리스 빌드에 대해 추가로 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-176">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="6b85b-177">컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-177">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="6b85b-178">릴리스 빌드 구성을 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-178">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="6b85b-179">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-179">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b85b-180">추가 자료</span><span class="sxs-lookup"><span data-stu-id="6b85b-180">Additional resources</span></span>

* [<span data-ttu-id="6b85b-181">.NET Core 및 .NET Standard의 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="6b85b-181">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="6b85b-182">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6b85b-182">Next steps</span></span>

<span data-ttu-id="6b85b-183">이 자습서에서는 클래스 라이브러리의 단위 테스트를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-183">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="6b85b-184">[NuGet](https://nuget.org)에 패키지로 라이브러리를 게시하면 다른 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-184">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="6b85b-185">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-185">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b85b-186">dotnet CLI를 사용하여 패키지 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="6b85b-186">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="6b85b-187">라이브러리를 NuGet 패키지로 게시하면 다른 사용자가 설치하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-187">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="6b85b-188">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-188">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b85b-189">dotnet CLI를 사용하여 패키지 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="6b85b-189">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="6b85b-190">라이브러리는 패키지로 배포하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-190">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="6b85b-191">라이브러리를 사용하는 콘솔 앱과 함께 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b85b-191">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="6b85b-192">콘솔 앱을 게시하는 방법을 알아보려면 이 시리즈의 이전 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b85b-192">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b85b-193">Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="6b85b-193">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
