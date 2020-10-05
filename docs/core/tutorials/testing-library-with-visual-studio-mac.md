---
title: Mac용 Visual Studio를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트
description: .NET Core 클래스 라이브러리에 대한 단위 테스트 프로젝트를 만듭니다. .NET Core 클래스 라이브러리가 단위 테스트에서 올바르게 작동하는지 확인합니다.
ms.date: 06/08/2020
ms.openlocfilehash: 3adcddc96abf77012f89a28c1cf60ea57ae506a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180532"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="342ac-104">Visual Studio를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="342ac-104">Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="342ac-105">이 자습서에서는 솔루션에 테스트 프로젝트를 추가하여 단위 테스트를 자동화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="342ac-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="342ac-106">Prerequisites</span></span>

- <span data-ttu-id="342ac-107">이 자습서는 [Mac용 Visual Studio를 사용하여 .NET Standard 라이브러리 만들기](library-with-visual-studio-mac.md)에서 만든 솔루션에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-107">This tutorial works with the solution that you create in [Create a .NET Standard library using Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="342ac-108">단위 테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="342ac-108">Create a unit test project</span></span>

<span data-ttu-id="342ac-109">단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="342ac-110">[MSTest](https://github.com/Microsoft/testfx-docs)는 선택할 수 있는 세 가지 테스트 프레임워크 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="342ac-111">다른 프레임워크는 [xUnit](https://xunit.net/)과 [nUnit](https://nunit.org/)입니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="342ac-112">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-112">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="342ac-113">[Mac용 Visual Studio를 사용하여 .NET Standard 라이브러리 만들기](library-with-visual-studio-mac.md)에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library using Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="342ac-114">**솔루션** 패드에서 <kbd>ctrl</kbd>을 누른 채로 `ClassLibraryProjects` 솔루션을 클릭하고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-114">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="342ac-115">**새 프로젝트** 대화 상자의 **웹 및 콘솔** 노드에서 **테스트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-115">In the **New Project** dialog, select **Tests** from the **Web and Console** node.</span></span> <span data-ttu-id="342ac-116">**MSTest 프로젝트**와 **다음**을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-116">Select the **MSTest Project** followed by **Next**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-118">**.NET Core 3.1**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-118">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="342ac-119">새 프로젝트의 이름을 "StringLibraryTest"로 지정하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-119">Name the new project "StringLibraryTest" and select **Create**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

   <span data-ttu-id="342ac-121">Visual Studio는 다음 코드로 클래스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-121">Visual Studio creates a class file with the following code:</span></span>

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

   <span data-ttu-id="342ac-122">단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-122">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="342ac-123">단위 테스트에 사용되는 형식을 포함하는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-123">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="342ac-124"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성을 `UnitTest1` 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="342ac-125"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성을 `TestMethod1`에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to `TestMethod1`.</span></span>

   <span data-ttu-id="342ac-126">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)로 태그가 지정된 테스트 클래스에서 [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)로 태그가 지정된 각 메서드는 단위 테스트가 실행될 때 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-126">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="342ac-127">프로젝트 참조 추가</span><span class="sxs-lookup"><span data-stu-id="342ac-127">Add a project reference</span></span>

<span data-ttu-id="342ac-128">테스트 프로젝트가 `StringLibrary` 클래스에 대해 작동하도록 `StringLibrary` 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-128">For the test project to work with the `StringLibrary` class, add a reference to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="342ac-129">**솔루션** 패드에서 <kbd>ctrl</kbd> 키를 누른 채로 **StringLibraryTest**에서 **종속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-129">In the **Solution** pad, <kbd>ctrl</kbd>-click **Dependencies** under **StringLibraryTest**.</span></span> <span data-ttu-id="342ac-130">상황에 맞는 메뉴에서 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-130">Select **Add Reference** from the context menu.</span></span>

1. <span data-ttu-id="342ac-131">**참조** 대화 상자에서 **StringLibrary** 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-131">In the **References** dialog, select the **StringLibrary** project.</span></span> <span data-ttu-id="342ac-132">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-132">Select **OK**.</span></span>

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="342ac-134">단위 테스트 메서드 추가 및 실행</span><span class="sxs-lookup"><span data-stu-id="342ac-134">Add and run unit test methods</span></span>

<span data-ttu-id="342ac-135">Visual Studio는 단위 테스트를 실행할 때 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성이 표시된 클래스에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성이 표시된 각 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="342ac-136">테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="342ac-137">가장 일반적인 테스트는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 클래스의 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="342ac-138">많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="342ac-139">`Assert` 클래스에서 가장 자주 호출되는 일부 메서드는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="342ac-140">Assert 메서드</span><span class="sxs-lookup"><span data-stu-id="342ac-140">Assert methods</span></span>     | <span data-ttu-id="342ac-141">기능</span><span class="sxs-lookup"><span data-stu-id="342ac-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="342ac-142">두 개의 값이나 개체가 같은지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="342ac-143">값이나 개체가 같지 않으면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="342ac-144">두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="342ac-145">변수가 서로 다른 개체를 참조하면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="342ac-146">조건이 `false`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="342ac-147">조건이 `true`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="342ac-148">개체가 `null`이 아닌지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="342ac-149">개체가 `null`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="342ac-150">테스트 메서드에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> 메서드를 사용하여 throw될 것으로 예상되는 예외의 유형을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="342ac-151">지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="342ac-152">`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="342ac-153">이러한 경우에 메서드가 `true`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="342ac-154">마찬가지로, 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="342ac-155">이러한 경우에 메서드가 `false`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="342ac-156">또한 라이브러리 메서드가 문자열을 처리하므로 [빈 문자열(`String.Empty`)](xref:System.String.Empty)(문자가 없고 해당 <xref:System.String.Length>가 0인 유효한 문자열) 및 `null` 문자열(초기화되지 않은 문자열)을 성공적으로 처리하는지 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="342ac-157">`StartsWithUpper`를 직접 정적 메서드로 호출하고 단일 <xref:System.String> 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="342ac-158">또는 `null`에 할당된 `string` 변수에 대한 확장 메서드로 `StartsWithUpper`를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="342ac-159">각 메서드가 문자열 배열의 각 요소에 대해 해당 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 메서드를 호출하는 메서드 세 개를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="342ac-160">테스트에 실패할 경우 표시될 오류 메시지를 지정할 수 있도록 하는 메서드 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="342ac-161">메시지는 실패를 일으킨 문자열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="342ac-162">테스트 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="342ac-162">To create the test methods:</span></span>

1. <span data-ttu-id="342ac-163">*UnitTest1.cs* 파일을 열고 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-163">Open the *UnitTest1.cs* file and replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="342ac-164">`TestStartsWithUpper` 메서드의 대문자 테스트에는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="342ac-165">`TestDoesNotStartWithUpper` 메서드의 소문자 테스트에는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="342ac-166">메뉴 모음에서 **파일** > **다른 이름으로 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-166">On the menu bar, select **File** > **Save As**.</span></span> <span data-ttu-id="342ac-167">대화 상자에서 **인코딩**이 **유니코드(UTF-8)** 로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-167">In the dialog, make sure that **Encoding** is set to **Unicode (UTF-8)**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-169">기존 파일을 바꿀지 묻는 메시지가 표시되면 **바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-169">When you're asked if you want to replace the existing file, select **Replace**.</span></span>

   <span data-ttu-id="342ac-170">소스 코드를 UTF8로 인코드된 파일에 저장하지 못하면 Visual Studio에서 해당 파일이 ASCII 파일로 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-170">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="342ac-171">이 경우 런타임은 ASCII 범위 밖의 UTF8 문자를 정확히 디코드하지 않으며 테스트 결과가 올바르지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-171">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="342ac-172">화면 오른쪽의 **단위 테스트** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-172">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="342ac-173">메뉴에서 **보기** > **테스트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-173">Select **View** > **Tests** from the menu.</span></span>

1. <span data-ttu-id="342ac-174">패널을 열어두려면 **고정** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-174">Click the **Dock** icon to keep the panel open.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-176">**모두 실행** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="342ac-177">모든 테스트가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-177">All tests pass.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

## <a name="handle-test-failures"></a><span data-ttu-id="342ac-179">테스트 실패 처리</span><span class="sxs-lookup"><span data-stu-id="342ac-179">Handle test failures</span></span>

<span data-ttu-id="342ac-180">TDD(테스트 기반 개발)를 수행하는 경우 먼저 테스트를 작성하고 첫 실행에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-180">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="342ac-181">그런 다음, 테스트를 성공하게 만드는 코드를 앱에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-181">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="342ac-182">이 자습서에서는 유효성을 검사하는 앱 코드를 작성한 후에 테스트를 만들었으므로 테스트에 실패하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-182">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="342ac-183">테스트가 실패할 것으로 예상되는 시점에 테스트가 실패하는지 확인하려면 테스트 입력에 잘못된 값을 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="342ac-183">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="342ac-184">`TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-184">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="342ac-185">테스트를 실행하도록 솔루션을 빌드하면 Visual Studio에서 열려 있는 파일을 자동으로 저장하기 때문에 파일을 저장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-185">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="342ac-186">테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-186">Run the tests again.</span></span>

   <span data-ttu-id="342ac-187">이때, **테스트 탐색기** 창에 두 가지 테스트는 성공하고 한 가지 테스트는 실패한 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-187">This time, the **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-189"><kbd>ctrl</kbd> 키를 누른 채로 실패한 테스트 `TestDoesNotStartWithUpper`를 클릭하고 상황에 맞는 메뉴에서 **결과 패드 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-189"><kbd>ctrl</kbd>-click the failed test, `TestDoesNotStartWithUpper`, and select **Show Results Pad** from the context menu.</span></span>

   <span data-ttu-id="342ac-190">**결과** 패드에 어설션이 생성하는 메시지가 표시됩니다. "Assert.IsFalse가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-190">The **Results** pad displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="342ac-191">'Error'에 필요한 값: false, 실제: True"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-191">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="342ac-192">이 오류 때문에 "Error" 다음에 나오는 배열의 문자열은 테스트되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-192">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-194">1단계에서 추가한 "Error" 문자열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-194">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="342ac-195">테스트를 다시 실행하면 테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-195">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="342ac-196">라이브러리의 릴리스 버전 테스트</span><span class="sxs-lookup"><span data-stu-id="342ac-196">Test the Release version of the library</span></span>

<span data-ttu-id="342ac-197">라이브러리의 디버그 빌드를 실행할 때 테스트에 모두 통과했으므로 라이브러리의 릴리스 빌드에 대해 추가로 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-197">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="342ac-198">컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-198">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="342ac-199">릴리스 빌드를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="342ac-199">To test the Release build:</span></span>

1. <span data-ttu-id="342ac-200">Visual Studio 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-200">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-202">**솔루션** 패드에서 <kbd>ctrl</kbd> 키를 누른 채로 **StringLibrary** 프로젝트를 클릭하고 상황에 맞는 메뉴에서 **빌드**를 클릭하여 라이브러리를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-202">In the **Solution** pad, <kbd>ctrl</kbd>-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="테스트 프로젝트를 만드는 Visual Studio Mac 새 프로젝트 대화 상자":::

1. <span data-ttu-id="342ac-204">단위 테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-204">Run the unit tests again.</span></span>

   <span data-ttu-id="342ac-205">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-205">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="342ac-206">테스트 디버그</span><span class="sxs-lookup"><span data-stu-id="342ac-206">Debug tests</span></span>

<span data-ttu-id="342ac-207">Mac용 Visual Studio를 IDE로 사용하는 경우 [자습서: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그](debugging-with-visual-studio-mac.md)에 표시된 것과 동일한 프로세스로 단위 테스트 프로젝트를 사용하는 코드를 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-207">If you're using Visual Studio for Mac as your IDE, you can use the same process shown in [Tutorial: Debug a .NET Core console application using Visual Studio for Mac](debugging-with-visual-studio-mac.md) to debug code using your unit test project.</span></span> <span data-ttu-id="342ac-208">*ShowCase* 앱 프로젝트를 시작하는 대신 <kbd>Ctrl</kbd> 키를 누른 채로 **StringLibraryTests** 프로젝트를 클릭한 다음 상황에 맞는 메뉴에서 **프로젝트 디버그 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-208">Instead of starting the *ShowCase* app project, <kbd>ctrl</kbd>-click the **StringLibraryTests** project, and select **Start Debugging Project** from the context menu.</span></span>

<span data-ttu-id="342ac-209">Visual Studio에서 디버거를 연결한 상태로 테스트 프로젝트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-209">Visual Studio starts the test project with the debugger attached.</span></span> <span data-ttu-id="342ac-210">테스트 프로젝트에 추가한 중단점 또는 기본 라이브러리 코드에서 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-210">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="342ac-211">추가 자료</span><span class="sxs-lookup"><span data-stu-id="342ac-211">Additional resources</span></span>

* [<span data-ttu-id="342ac-212">.NET Core 및 .NET Standard의 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="342ac-212">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="342ac-213">다음 단계</span><span class="sxs-lookup"><span data-stu-id="342ac-213">Next steps</span></span>

<span data-ttu-id="342ac-214">이 자습서에서는 클래스 라이브러리의 단위 테스트를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-214">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="342ac-215">[NuGet](https://nuget.org)에 패키지로 라이브러리를 게시하면 다른 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-215">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="342ac-216">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-216">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="342ac-217">패키지 만들기 및 게시(dotnet CLI)</span><span class="sxs-lookup"><span data-stu-id="342ac-217">Create and publish a package (dotnet CLI)</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="342ac-218">라이브러리를 NuGet 패키지로 게시하면 다른 사용자가 설치하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-218">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="342ac-219">방법을 알아보려면 NuGet 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-219">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="342ac-220">Mac용 Visual Studio에서 패키지 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="342ac-220">Install and use a package in Visual Studio for Mac</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

<span data-ttu-id="342ac-221">라이브러리는 패키지로 배포하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-221">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="342ac-222">라이브러리를 사용하는 콘솔 앱과 함께 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342ac-222">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="342ac-223">콘솔 앱을 게시하는 방법을 알아보려면 이 시리즈의 이전 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="342ac-223">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="342ac-224">Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="342ac-224">Publish a .NET Core console application using Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
