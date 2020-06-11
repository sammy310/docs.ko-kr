---
title: Visual Studio Code에서 .NET Core를 사용하여 .NET Standard 클래스 라이브러리 테스트
description: .NET Core 클래스 라이브러리에 대한 단위 테스트 프로젝트를 만듭니다. .NET Core 클래스 라이브러리가 단위 테스트에서 올바르게 작동하는지 확인합니다.
ms.date: 05/29/2020
ms.openlocfilehash: be227453bd441028cc6ce348c00fad944140238f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292164"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio-code"></a><span data-ttu-id="e7523-104">자습서: Visual Studio Code에서 .NET Core를 사용하여 .NET Standard 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="e7523-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>

<span data-ttu-id="e7523-105">이 자습서에서는 솔루션에 테스트 프로젝트를 추가하여 단위 테스트를 자동화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7523-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7523-106">Prerequisites</span></span>

- <span data-ttu-id="e7523-107">이 자습서는 [Visual Studio Code에서 .NET Standard 라이브러리 만들기](library-with-visual-studio-code.md)에서 만든 솔루션에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="e7523-108">단위 테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="e7523-108">Create a unit test project</span></span>

1. <span data-ttu-id="e7523-109">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-109">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="e7523-110">[Visual Studio에서 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-110">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="e7523-111">“StringLibraryTest”라는 단위 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-111">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="e7523-112">프로젝트 템플릿에서 다음 코드를 사용하여 UnitTest1.cs 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-112">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="e7523-113">단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-113">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="e7523-114">단위 테스트에 사용되는 형식을 포함하는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-114">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="e7523-115"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성을 `UnitTest1` 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-115">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="e7523-116"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성을 적용하여 `TestMethod1`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-116">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="e7523-117">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)로 태그가 지정된 테스트 클래스에서 [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)로 태그가 지정된 각 메서드는 단위 테스트가 실행될 때 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-117">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7523-118">MSTest는 선택할 수 있는 세 가지 테스트 프레임워크 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-118">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="e7523-119">다른 프레임워크는 xUnit과 nUnit입니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-119">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="e7523-120">테스트 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-120">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

1. <span data-ttu-id="e7523-121">다음 명령을 실행하여 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-121">Create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="e7523-122">단위 테스트 메서드 추가 및 실행</span><span class="sxs-lookup"><span data-stu-id="e7523-122">Add and run unit test methods</span></span>

<span data-ttu-id="e7523-123">Visual Studio는 단위 테스트를 실행할 때 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성이 표시된 클래스에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성이 표시된 각 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-123">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="e7523-124">테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-124">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="e7523-125">가장 일반적인 테스트는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 클래스의 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-125">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="e7523-126">많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-126">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="e7523-127">`Assert` 클래스에서 가장 자주 호출되는 일부 메서드는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-127">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="e7523-128">Assert 메서드</span><span class="sxs-lookup"><span data-stu-id="e7523-128">Assert methods</span></span>     | <span data-ttu-id="e7523-129">기능</span><span class="sxs-lookup"><span data-stu-id="e7523-129">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="e7523-130">두 개의 값이나 개체가 같은지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-130">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="e7523-131">값이나 개체가 같지 않으면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-131">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="e7523-132">두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-132">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="e7523-133">변수가 서로 다른 개체를 참조하면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-133">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="e7523-134">조건이 `false`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-134">Verifies that a condition is `false`.</span></span> <span data-ttu-id="e7523-135">조건이 `true`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-135">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="e7523-136">개체가 `null`이 아닌지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-136">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="e7523-137">개체가 `null`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-137">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="e7523-138">테스트 메서드에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> 메서드를 사용하여 throw될 것으로 예상되는 예외의 유형을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-138">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="e7523-139">지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-139">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="e7523-140">`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-140">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="e7523-141">이러한 경우에 메서드가 `true`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-141">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e7523-142">마찬가지로, 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-142">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="e7523-143">이러한 경우에 메서드가 `false`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-143">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e7523-144">라이브러리 메서드가 문자열을 처리하므로, 이 메서드에서 [빈 문자열(`String.Empty`)](xref:System.String.Empty) 및 `null` 문자열이 성공적으로 처리되는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-144">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="e7523-145">빈 문자열은 문자가 없고 <xref:System.String.Length>가 0인 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-145">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="e7523-146">`null` 문자열은 초기화되지 않은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-146">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="e7523-147">`StartsWithUpper`를 직접 정적 메서드로 호출하고 단일 <xref:System.String> 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-147">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="e7523-148">또는 `null`에 할당된 `string` 변수에 대한 확장 메서드로 `StartsWithUpper`를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-148">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="e7523-149">각 메서드가 문자열 배열의 각 요소에 대해 해당 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 메서드를 반복적으로 호출하는 메서드 세 개를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-149">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="e7523-150">첫 번째 오류가 발생하는 즉시 테스트 메서드가 실패하기 때문에 메서드 호출에 사용되는 문자열 값을 나타내는 문자열을 전달할 수 있도록 하는 메서드 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-150">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="e7523-151">테스트 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e7523-151">To create the test methods:</span></span>

1. <span data-ttu-id="e7523-152">*StringLibraryTest/UnitTest1.cs*를 열고 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-152">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="e7523-153">`TestStartsWithUpper` 메서드의 대문자 테스트에는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-153">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="e7523-154">`TestDoesNotStartWithUpper` 메서드의 소문자 테스트에는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-154">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="e7523-155">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-155">Save your changes.</span></span>

1. <span data-ttu-id="e7523-156">테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-156">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="e7523-157">터미널 출력에 모든 테스트를 통과했음이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-157">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="e7523-158">테스트 실패 처리</span><span class="sxs-lookup"><span data-stu-id="e7523-158">Handle test failures</span></span>

<span data-ttu-id="e7523-159">TDD(테스트 기반 개발)를 수행하는 경우 먼저 테스트를 작성하고 첫 실행에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-159">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="e7523-160">그런 다음, 테스트를 성공하게 만드는 코드를 앱에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-160">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="e7523-161">이 예제에서는 유효성을 검사하는 앱 코드를 작성한 후에 테스트를 만들었으므로 테스트에 실패하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-161">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="e7523-162">테스트가 실패할 것으로 예상되는 시점에 테스트가 실패하는지 확인하려면 테스트 입력에 잘못된 값을 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="e7523-162">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="e7523-163">`TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-163">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="e7523-164">테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-164">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="e7523-165">터미널 출력에 테스트 하나가 실패했음이 확인되고 실패한 테스트에 대한 오류 메시지가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-165">The terminal output shows that one test fails, and it provides an error message for the failed test.</span></span>

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

1. <span data-ttu-id="e7523-166">1단계에서 수행한 수정을 실행 취소하고 “오류” 문자열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-166">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="e7523-167">테스트를 다시 실행하면 테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-167">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="e7523-168">라이브러리의 릴리스 버전 테스트</span><span class="sxs-lookup"><span data-stu-id="e7523-168">Test the Release version of the library</span></span>

<span data-ttu-id="e7523-169">라이브러리의 디버그 버전을 실행할 때 테스트에 모두 통과했으므로 라이브러리의 릴리스 빌드에 대해 추가로 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-169">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="e7523-170">컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-170">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="e7523-171">릴리스 빌드 구성을 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-171">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="e7523-172">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-172">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7523-173">추가 자료</span><span class="sxs-lookup"><span data-stu-id="e7523-173">Additional resources</span></span>

- [<span data-ttu-id="e7523-174">.NET Core 및 .NET Standard의 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="e7523-174">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="e7523-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e7523-175">Next steps</span></span>

<span data-ttu-id="e7523-176">이 자습서에서는 클래스 라이브러리의 단위 테스트를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-176">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="e7523-177">[NuGet](https://nuget.org)에 패키지로 라이브러리를 게시하면 다른 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-177">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="e7523-178">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-178">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e7523-179">dotnet CLI를 사용하여 패키지 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="e7523-179">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="e7523-180">라이브러리를 NuGet 패키지로 게시하면 다른 사용자가 설치하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-180">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="e7523-181">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-181">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e7523-182">dotnet CLI를 사용하여 패키지 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="e7523-182">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="e7523-183">라이브러리는 패키지로 배포하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-183">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="e7523-184">라이브러리를 사용하는 콘솔 앱과 함께 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7523-184">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="e7523-185">콘솔 앱을 게시하는 방법을 알아보려면 이 시리즈의 이전 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7523-185">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e7523-186">Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="e7523-186">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
