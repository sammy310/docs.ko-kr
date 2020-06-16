---
title: 이식 가능한 클래스 라이브러리로 크로스 플랫폼 개발
description: .NET에서 이식 가능한 클래스 라이브러리 프로젝트 형식을 사용 하 여 Microsoft 플랫폼용 플랫폼 간 앱 및 라이브러리를 빠르고 쉽게 빌드합니다.
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: be1a49f7da7ce98f9e5e3ff8d927ce5230bfa8d8
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769147"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="87feb-103">이식 가능한 클래스 라이브러리를 사용 하 여 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="87feb-103">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="87feb-104">Visual Studio의 이식 가능한 클래스 라이브러리 프로젝트 형식을 사용 하면 Microsoft 플랫폼용 플랫폼 간 앱 및 라이브러리를 빠르고 쉽게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-104">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="87feb-105">이식 가능한 클래스 라이브러리를 사용하면 코드 개발 및 테스트에 드는 시간과 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-105">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="87feb-106">이 프로젝트 형식을 사용 하 여 이식 가능한 .NET Framework 어셈블리를 작성 하 고 빌드한 다음 .NET Framework, iOS, Mac 등의 여러 플랫폼을 대상으로 하는 앱에서 해당 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-106">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="87feb-107">Visual Studio에서 이식 가능한 클래스 라이브러리 프로젝트를 만든 다음 해당 프로젝트 개발을 시작한 후에도 대상 플랫폼을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-107">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="87feb-108">Visual Studio는 새 어셈블리를 사용 하 여 라이브러리를 컴파일하여 코드에서 수행 해야 하는 변경 내용을 식별 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-108">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="87feb-109">이식 가능한 클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="87feb-109">Create a Portable Class Library project</span></span>

<span data-ttu-id="87feb-110">이식 가능한 클래스 라이브러리를 만들려면 Visual Studio에서 제공 하는 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-110">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="87feb-111">새 프로젝트를 만들고 (새 프로젝트**파일**  >  **New Project**) **새 프로젝트** 대화 상자에서 프로그래밍 언어 (Visual c # 또는 Visual Basic)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-111">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="87feb-112">그런 다음 **클래스 라이브러리 (레거시 이식 가능)** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-112">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="87feb-113">프로젝트의 이름을 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-113">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="87feb-114">**이식 가능한 클래스 라이브러리 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-114">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="87feb-115">대상을 두 개 이상 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-115">Choose two or more targets, and then choose **OK**.</span></span>

![Visual Studio에서 이식 가능한 클래스 라이브러리 대상 추가](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="87feb-117">변경 대상</span><span class="sxs-lookup"><span data-stu-id="87feb-117">Change targets</span></span>

<span data-ttu-id="87feb-118">이식 가능한 클래스 라이브러리 프로젝트를 만들거나 개발을 시작한 후에는 대상 플랫폼을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-118">You can change the target platforms of a portable class library project when you create it or after you've started development.</span></span> <span data-ttu-id="87feb-119">프로젝트를 만든 후 대상을 변경 하려면 **솔루션 탐색기**에서 이식 가능한 클래스 라이브러리 프로젝트 (솔루션이 아님)에 대 한 바로 가기 메뉴를 열고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-119">If you want to change the targets after you've created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="87feb-120">프로젝트 속성 페이지의 **라이브러리** 탭에는 현재 프로젝트에서 대상으로 하는 플랫폼이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-120">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![Visual Studio의 이식 가능한 클래스 라이브러리에 대 한 프로젝트 속성](media/pcl-project-properties.png)

<span data-ttu-id="87feb-122">대상을 추가 하거나 제거 하려면 **변경** 단추를 선택한 다음 해당 확인란을 선택 하 고 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-122">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="87feb-123">대상을 변경하면 프로젝트 개발에 사용할 수 있는 API가 선택에 맞춰 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-123">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="87feb-124">Visual Studio에서는 대상 변경의 결과로 발생할 수 있는 오류 및 경고를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-124">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="87feb-125">Visual Studio를 변경 하기 전에 어셈블리의 이식성을 평가 하려는 경우 [.Net 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-125">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="87feb-126">지원되는 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="87feb-126">Supported types and members</span></span>

<span data-ttu-id="87feb-127">이식 가능한 클래스 라이브러리 프로젝트에서 사용할 수 있는 형식 및 멤버는 다음과 같이 여러 호환성 요소로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-127">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

- <span data-ttu-id="87feb-128">이들은 선택한 대상 간에 공유되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-128">They must be shared across the targets you selected.</span></span>

- <span data-ttu-id="87feb-129">이들은 이러한 여러 대상에서 유사하게 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-129">The must behave similarly across those targets.</span></span>

- <span data-ttu-id="87feb-130">이들은 사용 중단 후보가 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-130">They must not be candidates for deprecation.</span></span>

- <span data-ttu-id="87feb-131">이들은 특히 지원하는 멤버를 이식할 수 없을 때 이식 가능한 환경에서 의미가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-131">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="87feb-132">멤버가 이식 가능한 클래스 라이브러리에서 그리고 선택한 대상에 대해 지원되는 경우 IntelliSense의 프로젝트에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-132">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="87feb-133">그러나 이식 가능한 클래스 라이브러리에서 API가 지원될 수는 있지만 API를 사용할 수 있는지 여부는 선택한 대상에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-133">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="87feb-134">이식 가능한 클래스 라이브러리에서의 API 차이점</span><span class="sxs-lookup"><span data-stu-id="87feb-134">API differences in the Portable Class Library</span></span>

<span data-ttu-id="87feb-135">이식 가능한 클래스 라이브러리 어셈블리가 지원되는 모든 플랫폼에서 호환되도록 하기 위해 이식 가능한 클래스 라이브러리에서 일부 멤버가 약간 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-135">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="87feb-136">이식 가능한 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="87feb-136">Use the Portable Class Library</span></span>

<span data-ttu-id="87feb-137">이식 가능한 클래스 라이브러리 프로젝트를 빌드한 후에는 다른 프로젝트에서 이 프로젝트를 참조하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-137">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="87feb-138">액세스하려는 클래스가 포함된 프로젝트 또는 특정 어셈블리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-138">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="87feb-139">이식 가능한 클래스 라이브러리 어셈블리를 참조하는 앱을 실행하려면 대상 플랫폼의 필수 버전(또는 이후 버전)이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-139">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="87feb-140">Visual Studio에는 필요한 모든 프레임워크가 포함되므로 앱을 개발하는 데 사용한 컴퓨터에서 더 이상의 수정 없이 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-140">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="87feb-141">유니버설 Windows 앱 배포</span><span class="sxs-lookup"><span data-stu-id="87feb-141">Deploy a Universal Windows app</span></span>

<span data-ttu-id="87feb-142">이식 가능한 클래스 라이브러리 어셈블리를 참조 하는 유니버설 Windows 앱을 만드는 경우 앱을 배포 하는 데 필요한 모든 항목이 앱 패키지에 포함 되며 추가 단계가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-142">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="87feb-143">.NET Framework 앱 배포</span><span class="sxs-lookup"><span data-stu-id="87feb-143">Deploy a .NET Framework app</span></span>

<span data-ttu-id="87feb-144">이식 가능한 클래스 라이브러리 어셈블리를 참조하는 .NET Framework 앱을 배포할 때 종속성을 올바른 .NET Framework 버전에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-144">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="87feb-145">이 종속성을 지정하여 응용 프로그램에 필수 버전이 설치되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-145">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

- <span data-ttu-id="87feb-146">ClickOnce 배포를 사용 하 여 종속성을 만들려면: **솔루션 탐색기**에서 게시할 프로젝트에 대 한 프로젝트 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-146">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="87feb-147">이식 가능한 클래스 라이브러리 프로젝트를 참조 하는 프로젝트입니다. 메뉴 모음에서 **프로젝트**  >  **속성**을 선택한 다음 **게시** 탭을 선택 합니다. **게시** 페이지에서 **필수 구성 요소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-147">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="87feb-148">필수 .NET Framework 버전을 필수 구성 요소로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-148">Select the required .NET Framework version as a prerequisite.</span></span>

- <span data-ttu-id="87feb-149">설치 프로젝트를 사용 하 여 종속성을 만들려면: **솔루션 탐색기**에서 설치 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-149">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="87feb-150">메뉴 모음에서 **프로젝트**  >  **속성**  >  **필수 구성 요소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-150">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="87feb-151">필수 .NET Framework 버전을 필수 구성 요소로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87feb-151">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="87feb-152">.NET Framework 앱을 배포 하는 방법에 대 한 자세한 내용은 [개발자를 위한 배포 가이드](../../framework/deployment/deployment-guide-for-developers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87feb-152">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="87feb-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87feb-153">See also</span></span>

- [<span data-ttu-id="87feb-154">MVVM과 함께 이식 가능한 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="87feb-154">Using Portable Class Library with MVVM</span></span>](using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="87feb-155">여러 플랫폼을 대상으로 하는 라이브러리의 앱 리소스</span><span class="sxs-lookup"><span data-stu-id="87feb-155">App Resources for Libraries That Target Multiple Platforms</span></span>](app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="87feb-156">.NET 이식성 분석기</span><span class="sxs-lookup"><span data-stu-id="87feb-156">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="87feb-157">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="87feb-157">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="87feb-158">배포</span><span class="sxs-lookup"><span data-stu-id="87feb-158">Deployment</span></span>](../../framework/deployment/net-framework-applications.md)
