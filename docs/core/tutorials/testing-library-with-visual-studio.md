---
title: Visual Studio를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트
description: .NET Core 클래스 라이브러리에 대한 단위 테스트 프로젝트를 만듭니다. .NET Core 클래스 라이브러리가 단위 테스트에서 올바르게 작동하는지 확인합니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 049f0636b1c2c2df33461714aea5a11810ef00ad
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359196"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="160e1-104">자습서: Visual Studio를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="160e1-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="160e1-105">이 자습서에서는 솔루션에 테스트 프로젝트를 추가하여 단위 테스트를 자동화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="160e1-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="160e1-106">Prerequisites</span></span>

- <span data-ttu-id="160e1-107">이 자습서는 [Visual Studio를 사용하여 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)에서 만든 솔루션에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-107">This tutorial works with the solution that you create in [Create a .NET Standard library using Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="160e1-108">단위 테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="160e1-108">Create a unit test project</span></span>

<span data-ttu-id="160e1-109">단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="160e1-110">[MSTest](https://github.com/Microsoft/testfx-docs)는 선택할 수 있는 세 가지 테스트 프레임워크 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="160e1-111">다른 프레임워크는 [xUnit](https://xunit.net/)과 [nUnit](https://nunit.org/)입니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="160e1-112">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-112">Start Visual Studio.</span></span>

1. <span data-ttu-id="160e1-113">[Visual Studio를 사용하여 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library using Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="160e1-114">"StringLibraryTest"라는 새 단위 테스트 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-114">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="160e1-115">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-115">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="160e1-116">**새 프로젝트 추가** 페이지의 검색 상자에 **mstest**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-116">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="160e1-117">언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-117">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="160e1-118">**MSTest 테스트 프로젝트(.NET Core)** 템플릿을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-118">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="160e1-119">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibraryTest**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-119">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="160e1-120">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-120">Then choose **Create**.</span></span>

1. <span data-ttu-id="160e1-121">Visual Studio는 프로젝트를 만들고 코드 창에서 다음 코드가 포함된 클래스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-121">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="160e1-122">사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-122">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   <span data-ttu-id="160e1-123">단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-123">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="160e1-124">단위 테스트에 사용되는 형식을 포함하는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-124">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="160e1-125"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성을 `UnitTest1` 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="160e1-126"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성을 적용하여 `TestMethod1`(C#) 또는 `TestSub`(Visual Basic)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-126">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="160e1-127">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)로 태그가 지정된 테스트 클래스에서 [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)로 태그가 지정된 각 메서드는 단위 테스트가 실행될 때 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-127">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="160e1-128">프로젝트 참조 추가</span><span class="sxs-lookup"><span data-stu-id="160e1-128">Add a project reference</span></span>

<span data-ttu-id="160e1-129">테스트 라이브러리가 `StringLibrary` 클래스에 대해 작동하도록 하기 위해 **StringLibraryTest** 프로젝트의 참조를 `StringLibrary` 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-129">For the test project to work with the `StringLibrary` class, add a reference in the **StringLibraryTest** project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="160e1-130">**솔루션 탐색기**에서 **StringLibraryTest** 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **프로젝트 참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-130">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="160e1-131">**참조 관리자** 대화 상자에서 **프로젝트** 노드를 확장하고 **StringLibrary** 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-131">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="160e1-132">`StringLibrary` 어셈블리에 대한 참조를 추가하면 컴파일러가 **StringLibraryTest** 프로젝트를 컴파일하면서 **StringLibrary** 메서드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-132">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="160e1-133">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-133">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="160e1-134">단위 테스트 메서드 추가 및 실행</span><span class="sxs-lookup"><span data-stu-id="160e1-134">Add and run unit test methods</span></span>

<span data-ttu-id="160e1-135">Visual Studio는 단위 테스트를 실행할 때 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성이 표시된 클래스에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성이 표시된 각 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="160e1-136">테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="160e1-137">가장 일반적인 테스트는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 클래스의 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="160e1-138">많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="160e1-139">`Assert` 클래스에서 가장 자주 호출되는 일부 메서드는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="160e1-140">Assert 메서드</span><span class="sxs-lookup"><span data-stu-id="160e1-140">Assert methods</span></span>     | <span data-ttu-id="160e1-141">기능</span><span class="sxs-lookup"><span data-stu-id="160e1-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="160e1-142">두 개의 값이나 개체가 같은지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="160e1-143">값이나 개체가 같지 않으면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="160e1-144">두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="160e1-145">변수가 서로 다른 개체를 참조하면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="160e1-146">조건이 `false`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="160e1-147">조건이 `true`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="160e1-148">개체가 `null`이 아닌지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="160e1-149">개체가 `null`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="160e1-150">테스트 메서드에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> 메서드를 사용하여 throw될 것으로 예상되는 예외의 유형을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="160e1-151">지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="160e1-152">`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="160e1-153">이러한 경우에 메서드가 `true`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="160e1-154">마찬가지로, 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="160e1-155">이러한 경우에 메서드가 `false`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="160e1-156">또한 라이브러리 메서드가 문자열을 처리하므로 [빈 문자열(`String.Empty`)](xref:System.String.Empty)(문자가 없고 해당 <xref:System.String.Length>가 0인 유효한 문자열) 및 `null` 문자열(초기화되지 않은 문자열)을 성공적으로 처리하는지 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="160e1-157">`StartsWithUpper`를 직접 정적 메서드로 호출하고 단일 <xref:System.String> 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="160e1-158">또는 `null`에 할당된 `string` 변수에 대한 확장 메서드로 `StartsWithUpper`를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="160e1-159">각 메서드가 문자열 배열의 각 요소에 대해 해당 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 메서드를 호출하는 메서드 세 개를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="160e1-160">테스트에 실패할 경우 표시될 오류 메시지를 지정할 수 있도록 하는 메서드 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="160e1-161">메시지는 실패를 일으킨 문자열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="160e1-162">테스트 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="160e1-162">To create the test methods:</span></span>

1. <span data-ttu-id="160e1-163">*UnitTest1.cs* 또는 *UnitTest1.vb* 코드 창에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-163">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="160e1-164">`TestStartsWithUpper` 메서드의 대문자 테스트에는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="160e1-165">`TestDoesNotStartWithUpper` 메서드의 소문자 테스트에는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="160e1-166">메뉴 모음에서 **파일** > **다른 이름으로 UnitTest1.cs 저장** 또는 **파일** > **다른 이름으로 UnitTest1.vb 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-166">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="160e1-167">**다른 이름으로 파일 저장** 대화 상자에서 **저장** 단추 옆에 있는 화살표를 선택한 다음 **인코딩하여 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-167">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-168">![Visual Studio 다른 이름으로 파일 저장 대화 상자](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-168">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="160e1-169">**다른 이름으로 저장 확인** 대화 상자에서 **예** 단추를 선택하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-169">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="160e1-170">**고급 저장 옵션** 대화 상자의 **인코딩** 드롭다운 목록에서 **유니코드(시그니처가 있는 UTF-8) - 코드 페이지 65001**을 선택한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-170">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-171">![Visual Studio 고급 저장 옵션 대화 상자](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-171">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="160e1-172">소스 코드를 UTF8로 인코드된 파일에 저장하지 못하면 Visual Studio에서 해당 파일이 ASCII 파일로 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-172">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="160e1-173">이 경우 런타임은 ASCII 범위 밖의 UTF8 문자를 정확히 디코드하지 않으며 테스트 결과가 올바르지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-173">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="160e1-174">메뉴 모음에서 **테스트** > **모든 테스트 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-174">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="160e1-175">**테스트 탐색기** 창이 열리지 않으면 **테스트** > **테스트 탐색기**를 선택하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-175">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="160e1-176">세 가지 테스트가 **통과한 테스트** 섹션에 표시되고 **요약** 섹션에 테스트 실행 결과가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-176">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-177">![테스트를 통과한 테스트 탐색기 창](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-177">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="160e1-178">테스트 실패 처리</span><span class="sxs-lookup"><span data-stu-id="160e1-178">Handle test failures</span></span>

<span data-ttu-id="160e1-179">TDD(테스트 기반 개발)를 수행하는 경우 먼저 테스트를 작성하고 첫 실행에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-179">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="160e1-180">그런 다음, 테스트를 성공하게 만드는 코드를 앱에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-180">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="160e1-181">이 자습서에서는 유효성을 검사하는 앱 코드를 작성한 후에 테스트를 만들었으므로 테스트에 실패하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-181">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="160e1-182">테스트가 실패할 것으로 예상되는 시점에 테스트가 실패하는지 확인하려면 테스트 입력에 잘못된 값을 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="160e1-182">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="160e1-183">`TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-183">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="160e1-184">테스트를 실행하도록 솔루션을 빌드하면 Visual Studio에서 열려 있는 파일을 자동으로 저장하기 때문에 파일을 저장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-184">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="160e1-185">메뉴 모음에서 **테스트** > **모든 테스트 실행**을 선택하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-185">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="160e1-186">**테스트 탐색기** 창에 두 가지 테스트는 성공하고 한 가지 테스트는 실패한 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-186">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-187">![테스트를 실패한 테스트 탐색기 창](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-187">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="160e1-188">실패한 테스트인 `TestDoesNotStartWith`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-188">Select the failed test, `TestDoesNotStartWith`.</span></span>

   <span data-ttu-id="160e1-189">**테스트 탐색기** 창에 어설션이 생성하는 메시지 "Assert.IsFalse가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-189">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="160e1-190">'Error'에 필요한 값: false, 실제: True"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-190">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="160e1-191">이 오류 때문에 "Error" 다음에 나오는 배열의 문자열은 테스트되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-191">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-192">![Is False 어설션 실패를 표시하는 테스트 탐색기 창](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-192">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="160e1-193">1단계에서 추가한 "Error" 문자열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-193">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="160e1-194">테스트를 다시 실행하면 테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-194">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="160e1-195">라이브러리의 릴리스 버전 테스트</span><span class="sxs-lookup"><span data-stu-id="160e1-195">Test the Release version of the library</span></span>

<span data-ttu-id="160e1-196">라이브러리의 디버그 빌드를 실행할 때 테스트에 모두 통과했으므로 라이브러리의 릴리스 빌드에 대해 추가로 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-196">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="160e1-197">컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-197">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="160e1-198">릴리스 빌드를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="160e1-198">To test the Release build:</span></span>

1. <span data-ttu-id="160e1-199">Visual Studio 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-199">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-200">![릴리스 빌드가 강조 표시된 Visual Studio 도구 모음](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-200">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="160e1-201">**솔루션 탐색기**에서 **StringLibrary** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **빌드**를 선택하여 라이브러리를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-201">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="160e1-202">![빌드 명령이 있는 StringLibrary 상황에 맞는 메뉴](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="160e1-202">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="160e1-203">메뉴 모음에서 **테스트 실행** > **모든 테스트**를 선택하여 단위 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-203">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="160e1-204">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-204">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="160e1-205">추가 자료</span><span class="sxs-lookup"><span data-stu-id="160e1-205">Additional resources</span></span>

* [<span data-ttu-id="160e1-206">단위 테스트 기본 사항 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="160e1-206">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
* [<span data-ttu-id="160e1-207">.NET Core 및 .NET Standard의 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="160e1-207">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="160e1-208">다음 단계</span><span class="sxs-lookup"><span data-stu-id="160e1-208">Next steps</span></span>

<span data-ttu-id="160e1-209">이 자습서에서는 클래스 라이브러리의 단위 테스트를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-209">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="160e1-210">[NuGet](https://nuget.org)에 패키지로 라이브러리를 게시하면 다른 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-210">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="160e1-211">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-211">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="160e1-212">Visual Studio를 사용하여 NuGet 패키지 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="160e1-212">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="160e1-213">라이브러리를 NuGet 패키지로 게시하면 다른 사용자가 설치하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-213">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="160e1-214">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-214">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="160e1-215">Visual Studio에서 패키지 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="160e1-215">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="160e1-216">라이브러리는 패키지로 배포하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-216">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="160e1-217">라이브러리를 사용하는 콘솔 앱과 함께 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="160e1-217">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="160e1-218">콘솔 앱을 게시하는 방법을 알아보려면 이 시리즈의 이전 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="160e1-218">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="160e1-219">Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="160e1-219">Publish a .NET Core console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
