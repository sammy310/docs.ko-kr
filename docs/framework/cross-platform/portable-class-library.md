---
title: 이식 가능한 클래스 라이브러리로 크로스 플랫폼 개발
description: .NET에서 이식 가능한 클래스 라이브러리 프로젝트 형식을 사용하여 Microsoft 플랫폼용 플랫폼 간 앱 및 라이브러리를 빠르고 쉽게 빌드합니다.
ms.date: 09/17/2018
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: ced595f62249609f4524d0b4b7bf734929619bfd
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "102402238"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a><span data-ttu-id="2a274-103">이식 가능한 클래스 라이브러리로 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="2a274-103">Cross-platform development with the Portable Class Library</span></span>

<span data-ttu-id="2a274-104">Visual Studio의 이식 가능한 클래스 라이브러리 프로젝트 형식으로 Microsoft 플랫폼용 플랫폼 간 앱 및 라이브러리를 빠르고 쉽게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-104">The Portable Class Library project type in Visual Studio helps you build cross-platform apps and libraries for Microsoft platforms quickly and easily.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

<span data-ttu-id="2a274-105">이식 가능한 클래스 라이브러리를 사용하면 코드 개발 및 테스트에 드는 시간과 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-105">Portable class libraries can help you reduce the time and costs of developing and testing code.</span></span> <span data-ttu-id="2a274-106">이 프로젝트 형식을 사용하여 이식 가능 .NET Framework 어셈블리를 작성하고 빌드한 다음, .NET Framework, iOS 또는 Mac과 같은 여러 플랫폼을 대상으로 하는 앱에서 해당 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-106">Use this project type to write and build portable .NET Framework assemblies, and then reference those assemblies from apps that target multiple platforms such as the .NET Framework, iOS, or Mac.</span></span>

<span data-ttu-id="2a274-107">Visual Studio에서 이식 가능한 클래스 라이브러리 프로젝트를 만든 다음 해당 프로젝트 개발을 시작한 후에도 대상 플랫폼을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-107">Even after you create a Portable Class Library project in Visual Studio and start developing it, you can change the target platforms.</span></span> <span data-ttu-id="2a274-108">Visual Studio는 새 어셈블리로 라이브러리를 컴파일하여 코드에서 변경해야 하는 내용을 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-108">Visual Studio compiles your library with the new assemblies, which helps you identify the changes you need to make in your code.</span></span>

## <a name="create-a-portable-class-library-project"></a><span data-ttu-id="2a274-109">이식 가능한 클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2a274-109">Create a Portable Class Library project</span></span>

<span data-ttu-id="2a274-110">이식 가능한 클래스 라이브러리를 만들려면 Visual Studio에서 제공하는 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-110">To create a Portable Class Library, use the template provided in Visual Studio.</span></span> <span data-ttu-id="2a274-111">새 프로젝트를 만들고(**파일** > **새 프로젝트**) **새 프로젝트** 대화 상자에서 프로그래밍 언어(Visual C# 또는 Visual Basic)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-111">Create a new project (**File** > **New Project**), and in the **New Project** dialog box, select your programming language (Visual C# or Visual Basic).</span></span> <span data-ttu-id="2a274-112">그런 다음, **클래스 라이브러리(레거시 이식 가능)** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-112">Then, select the **Class Library (Legacy Portable)** template.</span></span> <span data-ttu-id="2a274-113">프로젝트 이름을 입력하고 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-113">Enter a name for your project and choose **OK**.</span></span>

<span data-ttu-id="2a274-114">**이식 가능한 클래스 라이브러리 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-114">The **Add Portable Class Library** dialog box appears.</span></span> <span data-ttu-id="2a274-115">대상을 두 개 이상 선택한 다음, **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-115">Choose two or more targets, and then choose **OK**.</span></span>

![Visual Studio에서 이식 가능한 클래스 라이브러리 대상 추가](media/add-portable-class-library.png)

## <a name="change-targets"></a><span data-ttu-id="2a274-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="2a274-117">Change targets</span></span>

<span data-ttu-id="2a274-118">이식 가능한 클래스 라이브러리 프로젝트를 만들 때 또는 개발을 시작한 후에 해당 프로젝트의 대상 플랫폼을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-118">You can change the target platforms of a portable class library project when you create it or after you've started development.</span></span> <span data-ttu-id="2a274-119">프로젝트를 만든 후 대상을 변경하려면 **솔루션 탐색기** 에서 이식 가능한 클래스 라이브러리 프로젝트(솔루션 아님)의 바로 가기 메뉴를 연 다음, **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-119">If you want to change the targets after you've created your project, in **Solution Explorer**, open the shortcut menu for your Portable Class Library project (not the solution), and then choose **Properties**.</span></span> <span data-ttu-id="2a274-120">프로젝트 속성 페이지의 **라이브러리** 탭에는 프로젝트에서 현재 대상으로 지정한 플랫폼이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-120">On the project properties page, the **Library** tab shows the platforms that your project currently targets.</span></span>

![Visual Studio에서 이식 가능한 클래스 라이브러리의 프로젝트 속성](media/pcl-project-properties.png)

<span data-ttu-id="2a274-122">대상을 추가하거나 제거하려면 **변경** 단추를 선택한 다음, 해당 확인란을 선택하고 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-122">To add or remove targets, choose the **Change** button, and then select and clear the appropriate check boxes.</span></span>

<span data-ttu-id="2a274-123">대상을 변경하면 프로젝트 개발에 사용할 수 있는 API가 선택에 맞춰 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-123">When you change the targets, the APIs that are available to you for developing your project will change to match your selection.</span></span> <span data-ttu-id="2a274-124">Visual Studio에서는 대상 변경의 결과로 발생할 수 있는 오류 및 경고를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-124">Visual Studio reports the errors and warnings that may occur as a result of the targets changing.</span></span>

<span data-ttu-id="2a274-125">Visual Studio에서 변경하기 전에 어셈블리의 이식성을 평가하려는 경우 [.NET 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-125">If you want to evaluate the portability of your assemblies before you make changes in Visual Studio, you can use the [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).</span></span>

## <a name="supported-types-and-members"></a><span data-ttu-id="2a274-126">지원되는 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="2a274-126">Supported types and members</span></span>

<span data-ttu-id="2a274-127">이식 가능한 클래스 라이브러리 프로젝트에서 사용할 수 있는 형식 및 멤버는 다음과 같이 여러 호환성 요소로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-127">The types and members that are available in Portable Class Library projects are constrained by several compatibility factors:</span></span>

- <span data-ttu-id="2a274-128">이들은 선택한 대상 간에 공유되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-128">They must be shared across the targets you selected.</span></span>

- <span data-ttu-id="2a274-129">이들은 이러한 여러 대상에서 유사하게 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-129">The must behave similarly across those targets.</span></span>

- <span data-ttu-id="2a274-130">이들은 사용 중단 후보가 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-130">They must not be candidates for deprecation.</span></span>

- <span data-ttu-id="2a274-131">이들은 특히 지원하는 멤버를 이식할 수 없을 때 이식 가능한 환경에서 의미가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-131">They must make sense in a portable environment, especially when supporting members are not portable.</span></span>

<span data-ttu-id="2a274-132">멤버가 이식 가능한 클래스 라이브러리에서 그리고 선택한 대상에 대해 지원되는 경우 IntelliSense의 프로젝트에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-132">If a member is supported in the Portable Class Library and for your selected targets, it will appear in your project in IntelliSense.</span></span> <span data-ttu-id="2a274-133">그러나 이식 가능한 클래스 라이브러리에서 API가 지원될 수는 있지만 API를 사용할 수 있는지 여부는 선택한 대상에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-133">However, remember that an API may be supported in the Portable Class Library, but whether you can use the API depends on the targets you select.</span></span>

## <a name="api-differences-in-the-portable-class-library"></a><span data-ttu-id="2a274-134">이식 가능한 클래스 라이브러리에서의 API 차이점</span><span class="sxs-lookup"><span data-stu-id="2a274-134">API differences in the Portable Class Library</span></span>

<span data-ttu-id="2a274-135">이식 가능한 클래스 라이브러리 어셈블리가 지원되는 모든 플랫폼에서 호환되도록 하기 위해 이식 가능한 클래스 라이브러리에서 일부 멤버가 약간 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-135">To make Portable Class Library assemblies compatible across all supported platforms, some members have been slightly changed in the Portable Class Library.</span></span>

## <a name="use-the-portable-class-library"></a><span data-ttu-id="2a274-136">이식 가능한 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="2a274-136">Use the Portable Class Library</span></span>

<span data-ttu-id="2a274-137">이식 가능한 클래스 라이브러리 프로젝트를 빌드한 후에는 다른 프로젝트에서 이 프로젝트를 참조하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-137">After you build your Portable Class Library project, you just reference it from other projects.</span></span> <span data-ttu-id="2a274-138">액세스하려는 클래스가 포함된 프로젝트 또는 특정 어셈블리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-138">You can reference either the project or specific assemblies that contain the classes you want to access.</span></span>

<span data-ttu-id="2a274-139">이식 가능한 클래스 라이브러리 어셈블리를 참조하는 앱을 실행하려면 대상 플랫폼의 필수 버전(또는 이후 버전)이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-139">To run an app that references a Portable Class Library assembly, the required version (or later) of the targeted platforms must be installed on your computer.</span></span> <span data-ttu-id="2a274-140">Visual Studio에는 필요한 모든 프레임워크가 포함되므로 앱을 개발하는 데 사용한 컴퓨터에서 더 이상의 수정 없이 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-140">Visual Studio contains all the required frameworks, so you can run the app without further modification on the computer that you used to develop the app.</span></span>

### <a name="deploy-a-universal-windows-app"></a><span data-ttu-id="2a274-141">유니버설 Windows 앱 배포</span><span class="sxs-lookup"><span data-stu-id="2a274-141">Deploy a Universal Windows app</span></span>

<span data-ttu-id="2a274-142">이식 가능한 클래스 라이브러리 어셈블리를 참조하는 유니버설 Windows 앱을 만드는 경우 만든 앱을 배포하는 데 필요한 모든 것이 앱 패키지에 들어 있으므로 추가 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-142">When you create a Universal Windows app that references a Portable Class Library assembly, everything you need to deploy the app is included in the app package, and no further steps are required.</span></span>

### <a name="deploy-a-net-framework-app"></a><span data-ttu-id="2a274-143">.NET Framework 앱 배포</span><span class="sxs-lookup"><span data-stu-id="2a274-143">Deploy a .NET Framework app</span></span>

<span data-ttu-id="2a274-144">이식 가능한 클래스 라이브러리 어셈블리를 참조하는 .NET Framework 앱을 배포할 때 종속성을 올바른 .NET Framework 버전에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-144">When you deploy a .NET Framework app that references a Portable Class Library assembly, you must specify a dependency on the correct version of the .NET Framework.</span></span> <span data-ttu-id="2a274-145">이 종속성을 지정하여 응용 프로그램에 필수 버전이 설치되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-145">By specifying this dependency, you ensure that the required version is installed with your app.</span></span>

- <span data-ttu-id="2a274-146">ClickOnce 배포를 사용하여 종속성을 만들려면 **솔루션 탐색기** 에서 게시할 프로젝트의 프로젝트 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-146">To create a dependency with ClickOnce deployment: In **Solution Explorer**, choose the project node for the project you want to publish.</span></span> <span data-ttu-id="2a274-147">(해당 프로젝트는 이식 가능한 클래스 라이브러리 프로젝트를 참조하는 프로젝트입니다.) 메뉴 모음에서 **프로젝트** > **속성** 을 선택한 다음, **게시** 탭을 선택합니다. **게시** 페이지에서 **필수 구성 요소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-147">(This is the project that references the Portable Class Library project.) On the menu bar, choose **Project** > **Properties**, and then choose the **Publish** tab. On the **Publish** page, choose **Prerequisites**.</span></span> <span data-ttu-id="2a274-148">필수 .NET Framework 버전을 필수 구성 요소로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-148">Select the required .NET Framework version as a prerequisite.</span></span>

- <span data-ttu-id="2a274-149">설치 프로젝트를 사용하여 종속성을 만들려면 **솔루션 탐색기** 에서 설치 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-149">To create a dependency with a setup project: In **Solution Explorer**, choose the setup project.</span></span> <span data-ttu-id="2a274-150">메뉴 모음에서 **프로젝트** > **속성** > **필수 구성 요소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-150">On the menu bar, choose **Project** > **Properties** > **Prerequisites**.</span></span> <span data-ttu-id="2a274-151">필수 .NET Framework 버전을 필수 구성 요소로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a274-151">Select the required .NET Framework version as a prerequisite.</span></span>

<span data-ttu-id="2a274-152">.NET Framework 앱 배포에 관한 자세한 내용은 [개발자를 위한 배포 가이드](../../framework/deployment/deployment-guide-for-developers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a274-152">For more information about deploying .NET Framework apps, see [Deployment Guide for Developers](../../framework/deployment/deployment-guide-for-developers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a274-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a274-153">See also</span></span>

- [<span data-ttu-id="2a274-154">MVVM과 함께 이식 가능한 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="2a274-154">Using Portable Class Library with MVVM</span></span>](using-portable-class-library-with-model-view-view-model.md)
- [<span data-ttu-id="2a274-155">여러 플랫폼을 대상으로 하는 라이브러리의 앱 리소스</span><span class="sxs-lookup"><span data-stu-id="2a274-155">App Resources for Libraries That Target Multiple Platforms</span></span>](app-resources-for-libraries-that-target-multiple-platforms.md)
- [<span data-ttu-id="2a274-156">.NET 이식성 분석기</span><span class="sxs-lookup"><span data-stu-id="2a274-156">.NET Portability Analyzer</span></span>](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [<span data-ttu-id="2a274-157">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="2a274-157">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)
- [<span data-ttu-id="2a274-158">배포</span><span class="sxs-lookup"><span data-stu-id="2a274-158">Deployment</span></span>](../../framework/deployment/net-framework-applications.md)
