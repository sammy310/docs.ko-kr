---
title: 애플리케이션 관리 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: dbc5bd9f699415fb47f21c6a45b1c58cfcff0f33
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124522"
---
# <a name="application-management-overview"></a><span data-ttu-id="98118-102">애플리케이션 관리 개요</span><span class="sxs-lookup"><span data-stu-id="98118-102">Application Management Overview</span></span>

<span data-ttu-id="98118-103">모든 애플리케이션은 애플리케이션 구현 및 관리에 적용하는 일반적인 기능 집합을 공유하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-103">All applications tend to share a common set of functionality that applies to application implementation and management.</span></span> <span data-ttu-id="98118-104">이 항목에서는 응용 프로그램을 만들고 관리 하기 위한 <xref:System.Windows.Application> 클래스의 기능에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-104">This topic provides an overview of the functionality in the <xref:System.Windows.Application> class for creating and managing applications.</span></span>

## <a name="the-application-class"></a><span data-ttu-id="98118-105">Application 클래스</span><span class="sxs-lookup"><span data-stu-id="98118-105">The Application Class</span></span>

<span data-ttu-id="98118-106">WPF에서 일반적인 응용 프로그램 범위 기능은 <xref:System.Windows.Application> 클래스에 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-106">In WPF, common application-scoped functionality is encapsulated in the <xref:System.Windows.Application> class.</span></span> <span data-ttu-id="98118-107"><xref:System.Windows.Application> 클래스에는 다음과 같은 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-107">The <xref:System.Windows.Application> class includes the following functionality:</span></span>

- <span data-ttu-id="98118-108">애플리케이션 수명 추적 및 상호 작용</span><span class="sxs-lookup"><span data-stu-id="98118-108">Tracking and interacting with application lifetime.</span></span>

- <span data-ttu-id="98118-109">명령줄 매개 변수 검색 및 처리</span><span class="sxs-lookup"><span data-stu-id="98118-109">Retrieving and processing command-line parameters.</span></span>

- <span data-ttu-id="98118-110">처리되지 않은 예외의 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="98118-110">Detecting and responding to unhandled exceptions.</span></span>

- <span data-ttu-id="98118-111">애플리케이션 범위 속성 및 리소스 공유</span><span class="sxs-lookup"><span data-stu-id="98118-111">Sharing application-scope properties and resources.</span></span>

- <span data-ttu-id="98118-112">독립 실행형 애플리케이션에서 창 관리</span><span class="sxs-lookup"><span data-stu-id="98118-112">Managing windows in standalone applications.</span></span>

- <span data-ttu-id="98118-113">탐색 추적 및 관리</span><span class="sxs-lookup"><span data-stu-id="98118-113">Tracking and managing navigation.</span></span>

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a><span data-ttu-id="98118-114">Application 클래스를 사용하여 일반적인 작업을 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="98118-114">How to Perform Common Tasks Using the Application Class</span></span>

<span data-ttu-id="98118-115"><xref:System.Windows.Application> 클래스에 대 한 모든 세부 정보에 관심이 없는 경우 다음 표에서는 <xref:System.Windows.Application>에 대 한 몇 가지 일반적인 작업과이를 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-115">If you are not interested in all of the details of the <xref:System.Windows.Application> class, the following table lists some of the common tasks for <xref:System.Windows.Application> and how to accomplish them.</span></span> <span data-ttu-id="98118-116">관련 API 및 항목을 확인하여 추가 정보 및 샘플 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-116">By viewing the related API and topics, you can find more information and sample code.</span></span>

|<span data-ttu-id="98118-117">Task</span><span class="sxs-lookup"><span data-stu-id="98118-117">Task</span></span>|<span data-ttu-id="98118-118">접근 방식</span><span class="sxs-lookup"><span data-stu-id="98118-118">Approach</span></span>|
|----------|--------------|
|<span data-ttu-id="98118-119">현재 애플리케이션을 나타내는 개체 가져오기</span><span class="sxs-lookup"><span data-stu-id="98118-119">Get an object that represents the current application</span></span>|<span data-ttu-id="98118-120"><xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-120">Use the <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> property.</span></span>|
|<span data-ttu-id="98118-121">애플리케이션에 시작 화면 추가</span><span class="sxs-lookup"><span data-stu-id="98118-121">Add a startup screen to an application</span></span>|<span data-ttu-id="98118-122">[WPF 응용 프로그램에 시작 화면 추가](how-to-add-a-splash-screen-to-a-wpf-application.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-122">See [Add a Splash Screen to a WPF Application](how-to-add-a-splash-screen-to-a-wpf-application.md).</span></span>|
|<span data-ttu-id="98118-123">애플리케이션 시작</span><span class="sxs-lookup"><span data-stu-id="98118-123">Start an application</span></span>|<span data-ttu-id="98118-124"><xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> 메서드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-124">Use the <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="98118-125">애플리케이션 중지</span><span class="sxs-lookup"><span data-stu-id="98118-125">Stop an application</span></span>|<span data-ttu-id="98118-126"><xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 개체의 <xref:System.Windows.Application.Shutdown%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-126">Use the <xref:System.Windows.Application.Shutdown%2A> method of the <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> object.</span></span>|
|<span data-ttu-id="98118-127">명령줄에서 인수 가져오기</span><span class="sxs-lookup"><span data-stu-id="98118-127">Get arguments from the command line</span></span>|<span data-ttu-id="98118-128"><xref:System.Windows.Application.Startup?displayProperty=nameWithType> 이벤트를 처리 하 고 <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-128">Handle the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event and use the <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="98118-129">예제는 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> 이벤트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-129">For an example, see the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event.</span></span>|
|<span data-ttu-id="98118-130">애플리케이션 종료 코드 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="98118-130">Get and set the application exit code</span></span>|<span data-ttu-id="98118-131"><xref:System.Windows.Application.Exit?displayProperty=nameWithType> 이벤트 처리기에서 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> 속성을 설정 하거나 <xref:System.Windows.Application.Shutdown%2A> 메서드를 호출 하 고 정수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-131">Set the <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> property in the <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event handler or call the <xref:System.Windows.Application.Shutdown%2A> method and pass in an integer.</span></span>|
|<span data-ttu-id="98118-132">처리되지 않은 예외의 검색 및 응답</span><span class="sxs-lookup"><span data-stu-id="98118-132">Detect and respond to unhandled exceptions</span></span>|<span data-ttu-id="98118-133"><xref:System.Windows.Application.DispatcherUnhandledException> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-133">Handle the <xref:System.Windows.Application.DispatcherUnhandledException> event.</span></span>|
|<span data-ttu-id="98118-134">애플리케이션 범위 리소스 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="98118-134">Get and set application-scoped resources</span></span>|<span data-ttu-id="98118-135"><xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-135">Use the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property.</span></span>|
|<span data-ttu-id="98118-136">애플리케이션 범위 리소스 사전 사용</span><span class="sxs-lookup"><span data-stu-id="98118-136">Use an application-scope resource dictionary</span></span>|<span data-ttu-id="98118-137">[응용 프로그램 범위 리소스 사전 사용](how-to-use-an-application-scope-resource-dictionary.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-137">See [Use an Application-Scope Resource Dictionary](how-to-use-an-application-scope-resource-dictionary.md).</span></span>|
|<span data-ttu-id="98118-138">애플리케이션 범위 속성 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="98118-138">Get and set application-scoped properties</span></span>|<span data-ttu-id="98118-139"><xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-139">Use the <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> property.</span></span>|
|<span data-ttu-id="98118-140">애플리케이션 상태 가져오기 및 저장</span><span class="sxs-lookup"><span data-stu-id="98118-140">Get and save an application's state</span></span>|<span data-ttu-id="98118-141">응용 프로그램 [세션 간에 응용 프로그램 범위 속성 유지 및 복원](persist-and-restore-application-scope-properties.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-141">See [Persist and Restore Application-Scope Properties Across Application Sessions](persist-and-restore-application-scope-properties.md).</span></span>|
|<span data-ttu-id="98118-142">리소스 파일, 콘텐츠 파일 및 원본 사이트 파일을 포함하여 비코드 데이터 파일 관리</span><span class="sxs-lookup"><span data-stu-id="98118-142">Manage non-code data files, including resource files, content files, and site-of-origin files.</span></span>|<span data-ttu-id="98118-143">[WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](wpf-application-resource-content-and-data-files.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-143">See [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>|
|<span data-ttu-id="98118-144">독립 실행형 애플리케이션의 창 관리</span><span class="sxs-lookup"><span data-stu-id="98118-144">Manage windows in standalone applications</span></span>|<span data-ttu-id="98118-145">[WPF 창 개요](wpf-windows-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-145">See [WPF Windows Overview](wpf-windows-overview.md).</span></span>|
|<span data-ttu-id="98118-146">탐색 추적 및 관리</span><span class="sxs-lookup"><span data-stu-id="98118-146">Track and manage navigation</span></span>|<span data-ttu-id="98118-147">[탐색 개요](navigation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-147">See [Navigation Overview](navigation-overview.md).</span></span>|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a><span data-ttu-id="98118-148">애플리케이션 정의</span><span class="sxs-lookup"><span data-stu-id="98118-148">The Application Definition</span></span>

<span data-ttu-id="98118-149"><xref:System.Windows.Application> 클래스의 기능을 활용 하려면 응용 프로그램 정의를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-149">To utilize the functionality of the <xref:System.Windows.Application> class, you must implement an application definition.</span></span> <span data-ttu-id="98118-150">WPF 응용 프로그램 정의는 <xref:System.Windows.Application>에서 파생 되 고 특수 MSBuild 설정을 사용 하 여 구성 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-150">A WPF application definition is a class that derives from <xref:System.Windows.Application> and is configured with a special MSBuild setting.</span></span>

### <a name="implementing-an-application-definition"></a><span data-ttu-id="98118-151">애플리케이션 정의 구현</span><span class="sxs-lookup"><span data-stu-id="98118-151">Implementing an Application Definition</span></span>

<span data-ttu-id="98118-152">일반적인 WPF 응용 프로그램 정의는 태그와 코드 숨김으로 모두 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-152">A typical WPF application definition is implemented using both markup and code-behind.</span></span> <span data-ttu-id="98118-153">따라서 코드 숨김에서 애플리케이션별 동작을 구현하고 이벤트를 처리하는 동시에 태그를 사용하여 애플리케이션 속성과 리소스를 선언적으로 설정하고 이벤트를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-153">This allows you to use markup to declaratively set application properties, resources, and register events, while handling events and implementing application-specific behavior in code-behind.</span></span>

<span data-ttu-id="98118-154">다음 예제에서는 태그 및 코드 숨김을 모두 사용하여 애플리케이션 정의를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-154">The following example shows how to implement an application definition using both markup and code-behind:</span></span>

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

<span data-ttu-id="98118-155">태그 파일과 코드 숨김 파일이 함께 작동하도록 하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-155">To allow a markup file and code-behind file to work together, the following needs to happen:</span></span>

- <span data-ttu-id="98118-156">태그에서 `Application` 요소는 `x:Class` 특성을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-156">In markup, the `Application` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="98118-157">응용 프로그램을 빌드할 때 태그 파일에 `x:Class` 있으면 MSBuild는 <xref:System.Windows.Application>에서 파생 되 고 `x:Class` 특성으로 지정 된 이름을 가진 `partial` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98118-157">When the application is built, the existence of `x:Class` in the markup file causes MSBuild to create a `partial` class that derives from <xref:System.Windows.Application> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="98118-158">이렇게 하려면 XAML 스키마 (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`)에 대 한 XML 네임 스페이스 선언을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-158">This requires the addition of an XML namespace declaration for the XAML schema (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).</span></span>

- <span data-ttu-id="98118-159">코드를 사용 하는 경우 클래스는 태그에서 `x:Class` 특성으로 지정 되는 동일한 이름을 가진 `partial` 클래스 여야 하며 <xref:System.Windows.Application>에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-159">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup and must derive from <xref:System.Windows.Application>.</span></span> <span data-ttu-id="98118-160">이렇게 하면 응용 프로그램을 빌드할 때 태그 파일에 대해 생성 된 `partial` 클래스와 코드 숨김이 연결 될 수 있습니다 ( [WPF 응용 프로그램 빌드](building-a-wpf-application-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="98118-160">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="98118-161">Visual Studio를 사용 하 여 새 WPF 응용 프로그램 프로젝트 또는 WPF 브라우저 응용 프로그램 프로젝트를 만드는 경우 응용 프로그램 정의는 기본적으로 포함 되며 태그와 코드 숨김으로 모두 사용 하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-161">When you create a new WPF Application project or WPF Browser Application project using Visual Studio, an application definition is included by default and is defined using both markup and code-behind.</span></span>

<span data-ttu-id="98118-162">이 코드는 애플리케이션 정의를 구현하는 데 필요한 최소한의 코드이지만,</span><span class="sxs-lookup"><span data-stu-id="98118-162">This code is the minimum that is required to implement an application definition.</span></span> <span data-ttu-id="98118-163">그러나 응용 프로그램을 빌드하고 실행 하기 전에 응용 프로그램 정의에 대 한 추가 MSBuild 구성을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-163">However, an additional MSBuild configuration needs to be made to the application definition before building and running the application.</span></span>

### <a name="configuring-the-application-definition-for-msbuild"></a><span data-ttu-id="98118-164">MSBuild용 애플리케이션 정의 구성</span><span class="sxs-lookup"><span data-stu-id="98118-164">Configuring the Application Definition for MSBuild</span></span>

<span data-ttu-id="98118-165">독립 실행형 응용 프로그램 및 Xbap (XAML 브라우저 응용 프로그램)는 특정 수준의 인프라를 구현 해야 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-165">Standalone applications and XAML browser applications (XBAPs) require the implementation of a certain level of infrastructure before they can run.</span></span> <span data-ttu-id="98118-166">이 인프라의 가장 중요한 부분은 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-166">The most important part of this infrastructure is the entry point.</span></span> <span data-ttu-id="98118-167">사용자가 애플리케이션을 시작하면 운영 체제에서는 잘 알려진 애플리케이션 시작 함수인 진입점을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-167">When an application is launched by a user, the operating system calls the entry point, which is a well-known function for starting applications.</span></span>

<span data-ttu-id="98118-168">일반적으로는 기술에 따라 개발자가 직접 이 코드 일부나 전체를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-168">Traditionally, developers have needed to write some or all of this code for themselves, depending on the technology.</span></span> <span data-ttu-id="98118-169">그러나 다음 MSBuild 프로젝트 파일에 표시 된 것 처럼 응용 프로그램 정의의 태그 파일이 MSBuild `ApplicationDefinition` 항목으로 구성 된 경우 WPF는이 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-169">However, WPF generates this code for you when the markup file of your application definition is configured as an MSBuild `ApplicationDefinition` item, as shown in the following MSBuild project file:</span></span>

```xml
<Project
  DefaultTargets="Build"
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  ...
  <ApplicationDefinition Include="App.xaml" />
  <Compile Include="App.xaml.cs" />
  ...
</Project>
```

<span data-ttu-id="98118-170">코드를 포함 하는 코드는 정상적인 코드를 포함 하기 때문에 MSBuild `Compile` 항목으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-170">Because the code-behind file contains code, it is marked as an MSBuild `Compile` item, as is normal.</span></span>

<span data-ttu-id="98118-171">응용 프로그램 정의의 태그 및 코드 숨김으로 이러한 MSBuild 구성을 적용 하면 MSBuild에서 다음과 같은 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-171">The application of these MSBuild configurations to the markup and code-behind files of an application definition causes MSBuild to generate code like the following:</span></span>

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

<span data-ttu-id="98118-172">결과 코드는 진입점 메서드 `Main`를 포함 하는 추가 인프라 코드를 사용 하 여 응용 프로그램 정의를 보강 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-172">The resulting code augments your application definition with additional infrastructure code, which includes the entry-point method `Main`.</span></span> <span data-ttu-id="98118-173"><xref:System.STAThreadAttribute> 특성은 WPF 응용 프로그램의 주 UI 스레드가 WPF 응용 프로그램에 필요한 STA 스레드 임을 나타내기 위해 `Main` 메서드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-173">The <xref:System.STAThreadAttribute> attribute is applied to the `Main` method to indicate that the main UI thread for the WPF application is an STA thread, which is required for WPF applications.</span></span> <span data-ttu-id="98118-174">`Main` 호출 되 면 `InitializeComponent` 메서드를 호출 하 여 이벤트를 등록 하 고 태그에 구현 된 속성을 설정 하기 전에 `App`의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98118-174">When called, `Main` creates a new instance of `App` before calling the `InitializeComponent` method to register the events and set the properties that are implemented in markup.</span></span> <span data-ttu-id="98118-175">`InitializeComponent` 생성 되기 때문에 <xref:System.Windows.Controls.Page> 및 <xref:System.Windows.Window> 구현에 대해 수행 하는 것 처럼 응용 프로그램 정의에서 `InitializeComponent`를 명시적으로 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-175">Because `InitializeComponent` is generated for you, you don't need to explicitly call `InitializeComponent` from an application definition like you do for <xref:System.Windows.Controls.Page> and <xref:System.Windows.Window> implementations.</span></span> <span data-ttu-id="98118-176">마지막으로, <xref:System.Windows.Application.Run%2A> 메서드를 호출 하 여 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-176">Finally, the <xref:System.Windows.Application.Run%2A> method is called to start the application.</span></span>

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a><span data-ttu-id="98118-177">현재 애플리케이션 가져오기</span><span class="sxs-lookup"><span data-stu-id="98118-177">Getting the Current Application</span></span>

<span data-ttu-id="98118-178"><xref:System.Windows.Application> 클래스의 기능은 응용 프로그램에서 공유 되므로 <xref:System.AppDomain>당 <xref:System.Windows.Application> 클래스의 인스턴스는 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-178">Because the functionality of the <xref:System.Windows.Application> class are shared across an application, there can be only one instance of the <xref:System.Windows.Application> class per <xref:System.AppDomain>.</span></span> <span data-ttu-id="98118-179">이를 적용 하기 위해 <xref:System.Windows.Application> 클래스는 singleton 클래스로 [ C# ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650316(v=pandp.10))구현 됩니다. 즉,의 단일 인스턴스를 만들고 `static`<xref:System.Windows.Application.Current%2A> 속성을 사용 하 여 공유 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-179">To enforce this, the <xref:System.Windows.Application> class is implemented as a singleton class (see [Implementing Singleton in C#](https://docs.microsoft.com/previous-versions/msp-n-p/ff650316(v=pandp.10))), which creates a single instance of itself and provides shared access to it with the `static`<xref:System.Windows.Application.Current%2A> property.</span></span>

<span data-ttu-id="98118-180">다음 코드에서는 현재 <xref:System.AppDomain>에 대 한 <xref:System.Windows.Application> 개체에 대 한 참조를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-180">The following code shows how to acquire a reference to the <xref:System.Windows.Application> object for the current <xref:System.AppDomain>.</span></span>

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<span data-ttu-id="98118-181"><xref:System.Windows.Application.Current%2A> <xref:System.Windows.Application> 클래스의 인스턴스에 대 한 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-181"><xref:System.Windows.Application.Current%2A> returns a reference to an instance of the <xref:System.Windows.Application> class.</span></span> <span data-ttu-id="98118-182"><xref:System.Windows.Application> 파생 클래스에 대 한 참조를 원하는 경우 다음 예제와 같이 <xref:System.Windows.Application.Current%2A> 속성의 값을 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-182">If you want a reference to your <xref:System.Windows.Application> derived class you must cast the value of the <xref:System.Windows.Application.Current%2A> property, as shown in the following example.</span></span>

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

<span data-ttu-id="98118-183"><xref:System.Windows.Application> 개체의 수명 동안 언제 든 <xref:System.Windows.Application.Current%2A>의 값을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-183">You can inspect the value of <xref:System.Windows.Application.Current%2A> at any point in the lifetime of an <xref:System.Windows.Application> object.</span></span> <span data-ttu-id="98118-184">하지만 이러한 검사를 수행할 때는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-184">However, you should be careful.</span></span> <span data-ttu-id="98118-185"><xref:System.Windows.Application> 클래스가 인스턴스화된 후에는 <xref:System.Windows.Application> 개체의 상태가 일치 하지 않는 기간이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-185">After the <xref:System.Windows.Application> class is instantiated, there is a period during which the state of the <xref:System.Windows.Application> object is inconsistent.</span></span> <span data-ttu-id="98118-186">이 기간 동안에는 응용 프로그램 인프라를 설정 하 고, 속성을 설정 하 고, 이벤트를 등록 하는 작업을 포함 하 여 코드를 실행 하는 데 필요한 다양 한 초기화 작업을 <xref:System.Windows.Application> 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-186">During this period, <xref:System.Windows.Application> is performing the various initialization tasks that are required by your code to run, including establishing application infrastructure, setting properties, and registering events.</span></span> <span data-ttu-id="98118-187">이 기간 동안 <xref:System.Windows.Application> 개체를 사용 하려고 하면 코드에서 예기치 않은 결과가 발생할 수 있으며,이는 특히 설정 되는 다양 한 <xref:System.Windows.Application> 속성에 따라 달라 지는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-187">If you try to use the <xref:System.Windows.Application> object during this period, your code may have unexpected results, particularly if it depends on the various <xref:System.Windows.Application> properties being set.</span></span>

<span data-ttu-id="98118-188"><xref:System.Windows.Application> 초기화 작업을 완료 하면 수명이 실제로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-188">When <xref:System.Windows.Application> completes its initialization work, its lifetime truly begins.</span></span>

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a><span data-ttu-id="98118-189">애플리케이션 수명</span><span class="sxs-lookup"><span data-stu-id="98118-189">Application Lifetime</span></span>

<span data-ttu-id="98118-190">WPF 응용 프로그램의 수명은 응용 프로그램의 시작, 활성화 및 비활성화 및 종료 된 시기를 알려 주는 <xref:System.Windows.Application>에 의해 발생 하는 몇 가지 이벤트로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-190">The lifetime of a WPF application is marked by several events that are raised by <xref:System.Windows.Application> to let you know when your application has started, has been activated and deactivated, and has been shut down.</span></span>

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a><span data-ttu-id="98118-191">시작 화면</span><span class="sxs-lookup"><span data-stu-id="98118-191">Splash Screen</span></span>

<span data-ttu-id="98118-192">.NET Framework 3.5 s p 1 부터는 시작 창 또는 *시작 화면*에서 사용할 이미지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-192">Starting in the .NET Framework 3.5 SP1, you can specify an image to be used in a startup window, or *splash screen*.</span></span> <span data-ttu-id="98118-193"><xref:System.Windows.SplashScreen> 클래스를 사용 하면 응용 프로그램을 로드 하는 동안 시작 창을 쉽게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-193">The <xref:System.Windows.SplashScreen> class makes it easy to display a startup window while your application is loading.</span></span> <span data-ttu-id="98118-194"><xref:System.Windows.Application.Run%2A>를 호출 하기 전에 <xref:System.Windows.SplashScreen> 창이 만들어지고 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-194">The <xref:System.Windows.SplashScreen> window is created and shown before <xref:System.Windows.Application.Run%2A> is called.</span></span> <span data-ttu-id="98118-195">자세한 내용은 [응용 프로그램 시작 시간](../advanced/application-startup-time.md) 및 [WPF 응용 프로그램에 시작 화면 추가](how-to-add-a-splash-screen-to-a-wpf-application.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-195">For more information, see [Application Startup Time](../advanced/application-startup-time.md) and [Add a Splash Screen to a WPF Application](how-to-add-a-splash-screen-to-a-wpf-application.md).</span></span>

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a><span data-ttu-id="98118-196">애플리케이션 시작</span><span class="sxs-lookup"><span data-stu-id="98118-196">Starting an Application</span></span>

<span data-ttu-id="98118-197"><xref:System.Windows.Application.Run%2A>를 호출 하 고 응용 프로그램을 초기화 한 후에는 응용 프로그램을 실행할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-197">After <xref:System.Windows.Application.Run%2A> is called and the application is initialized, the application is ready to run.</span></span> <span data-ttu-id="98118-198">이 순간은 <xref:System.Windows.Application.Startup> 이벤트가 발생할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-198">This moment is signified when the <xref:System.Windows.Application.Startup> event is raised:</span></span>

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

<span data-ttu-id="98118-199">응용 프로그램 수명의이 시점에서 가장 일반적인 작업은 UI를 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-199">At this point in an application's lifetime, the most common thing to do is to show a UI.</span></span>

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a><span data-ttu-id="98118-200">사용자 인터페이스 표시</span><span class="sxs-lookup"><span data-stu-id="98118-200">Showing a User Interface</span></span>

<span data-ttu-id="98118-201">대부분의 독립 실행형 Windows 응용 프로그램은 실행을 시작할 때 <xref:System.Windows.Window>을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98118-201">Most standalone Windows applications open a <xref:System.Windows.Window> when they begin running.</span></span> <span data-ttu-id="98118-202"><xref:System.Windows.Application.Startup> 이벤트 처리기는 다음 코드에 표시 된 것 처럼이 작업을 수행할 수 있는 한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-202">The <xref:System.Windows.Application.Startup> event handler is one location from which you can do this, as demonstrated by the following code.</span></span>

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> <span data-ttu-id="98118-203">독립 실행형 응용 프로그램에서 인스턴스화될 첫 번째 <xref:System.Windows.Window>는 기본적으로 주 응용 프로그램 창이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-203">The first <xref:System.Windows.Window> to be instantiated in a standalone application becomes the main application window by default.</span></span> <span data-ttu-id="98118-204">이 <xref:System.Windows.Window> 개체는 <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> 속성에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-204">This <xref:System.Windows.Window> object is referenced by the <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="98118-205">처음 인스턴스화된 <xref:System.Windows.Window> 아닌 다른 창이 주 창인 경우 <xref:System.Windows.Application.MainWindow%2A> 속성의 값을 프로그래밍 방식으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-205">The value of the <xref:System.Windows.Application.MainWindow%2A> property can be changed programmatically if a different window than the first instantiated <xref:System.Windows.Window> should be the main window.</span></span>

<span data-ttu-id="98118-206">XBAP가 처음 시작 될 때 <xref:System.Windows.Controls.Page>으로 이동 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-206">When an XBAP first starts, it will most likely navigate to a <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="98118-207">다음 코드에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-207">This is shown in the following code.</span></span>

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

<span data-ttu-id="98118-208"><xref:System.Windows.Application.Startup>를 처리 하 여 <xref:System.Windows.Window>만 열거나 <xref:System.Windows.Controls.Page>로 이동 하는 경우 태그에서 `StartupUri` 특성을 대신 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-208">If you handle <xref:System.Windows.Application.Startup> to only open a <xref:System.Windows.Window> or navigate to a <xref:System.Windows.Controls.Page>, you can set the `StartupUri` attribute in markup instead.</span></span>

<span data-ttu-id="98118-209">다음 예제에서는 독립 실행형 응용 프로그램에서 <xref:System.Windows.Application.StartupUri%2A>를 사용 하 여 <xref:System.Windows.Window>을 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-209">The following example shows how to use the <xref:System.Windows.Application.StartupUri%2A> from a standalone application to open a <xref:System.Windows.Window>.</span></span>

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

<span data-ttu-id="98118-210">다음 예제에서는 XBAP에서 <xref:System.Windows.Application.StartupUri%2A>를 사용 하 여 <xref:System.Windows.Controls.Page>탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-210">The following example shows how to use <xref:System.Windows.Application.StartupUri%2A> from an XBAP to navigate to a <xref:System.Windows.Controls.Page>.</span></span>

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

<span data-ttu-id="98118-211">이 태그는 창을 여는 이전 코드와 같은 효과를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-211">This markup has the same effect as the previous code for opening a window.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-212">탐색에 대 한 자세한 내용은 [탐색 개요](navigation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-212">For more information on navigation, see [Navigation Overview](navigation-overview.md).</span></span>

<span data-ttu-id="98118-213">매개 변수가 없는 생성자를 사용 하 여 인스턴스화해야 하는 경우 <xref:System.Windows.Window>를 열려면 <xref:System.Windows.Application.Startup> 이벤트를 처리 해야 합니다. 또는 해당 속성을 표시 하기 전에 해당 속성을 설정 하거나 해당 이벤트를 구독 해야 하거나 응용 프로그램을 시작할 때 제공 된 명령줄 인수를 처리 해야 하는 경우에 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-213">You need to handle the <xref:System.Windows.Application.Startup> event to open a <xref:System.Windows.Window> if you need to instantiate it using a non-parameterless constructor, or you need to set its properties or subscribe to its events before showing it, or you need to process any command-line arguments that were supplied when the application was launched.</span></span>

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a><span data-ttu-id="98118-214">명령줄 인수 처리</span><span class="sxs-lookup"><span data-stu-id="98118-214">Processing Command-Line Arguments</span></span>

<span data-ttu-id="98118-215">Windows에서 독립 실행형 응용 프로그램은 명령 프롬프트 또는 바탕 화면에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-215">In Windows, standalone applications can be launched from either a command prompt or the desktop.</span></span> <span data-ttu-id="98118-216">두 경우 모두 명령줄 인수를 애플리케이션으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-216">In both cases, command-line arguments can be passed to the application.</span></span> <span data-ttu-id="98118-217">다음 예제에서는 단일 명령줄 인수 "/StartMinimized"를 사용하여 시작되는 애플리케이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-217">The following example shows an application that is launched with a single command-line argument, "/StartMinimized":</span></span>

`wpfapplication.exe /StartMinimized`

<span data-ttu-id="98118-218">응용 프로그램을 초기화 하는 동안 WPF는 운영 체제에서 명령줄 인수를 검색 하 고 <xref:System.Windows.StartupEventArgs> 매개 변수의 <xref:System.Windows.StartupEventArgs.Args%2A> 속성을 통해 <xref:System.Windows.Application.Startup> 이벤트 처리기에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-218">During application initialization, WPF retrieves the command-line arguments from the operating system and passes them to the <xref:System.Windows.Application.Startup> event handler via the <xref:System.Windows.StartupEventArgs.Args%2A> property of the <xref:System.Windows.StartupEventArgs> parameter.</span></span> <span data-ttu-id="98118-219">다음과 같은 코드를 사용하여 명령줄 인수를 검색하고 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-219">You can retrieve and store the command-line arguments using code like the following.</span></span>

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

<span data-ttu-id="98118-220">코드를 처리 하 여 **/start최소화** 된 명령줄 인수가 제공 되었는지 여부를 확인 <xref:System.Windows.Application.Startup> 합니다. 이 경우 <xref:System.Windows.WindowState.Minimized><xref:System.Windows.WindowState> 있는 주 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="98118-220">The code handles <xref:System.Windows.Application.Startup> to check whether the **/StartMinimized** command-line argument was provided; if so, it opens the main window with a <xref:System.Windows.WindowState> of <xref:System.Windows.WindowState.Minimized>.</span></span> <span data-ttu-id="98118-221"><xref:System.Windows.Window.WindowState%2A> 속성을 프로그래밍 방식으로 설정 해야 하므로 주 <xref:System.Windows.Window>를 코드에서 명시적으로 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-221">Note that because the <xref:System.Windows.Window.WindowState%2A> property must be set programmatically, the main <xref:System.Windows.Window> must be opened explicitly in code.</span></span>

<span data-ttu-id="98118-222">Xbap는 ClickOnce 배포를 사용 하 여 시작 되기 때문에 명령줄 인수를 검색 하 고 처리할 수 없습니다 ( [WPF 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="98118-222">XBAPs cannot retrieve and process command-line arguments because they are launched using ClickOnce deployment (see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md)).</span></span> <span data-ttu-id="98118-223">그러나 XBAP를 시작하는 데 사용되는 URL에서 쿼리 문자열 매개 변수를 검색하고 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-223">However, they can retrieve and process query string parameters from the URLs that are used to launch them.</span></span>

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a><span data-ttu-id="98118-224">애플리케이션 활성화 및 비활성화</span><span class="sxs-lookup"><span data-stu-id="98118-224">Application Activation and Deactivation</span></span>

<span data-ttu-id="98118-225">Windows에서는 사용자가 응용 프로그램 간에 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-225">Windows allows users to switch between applications.</span></span> <span data-ttu-id="98118-226">가장 일반적인 방법은 ALT+TAB 키 조합을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-226">The most common way is to use the ALT+TAB key combination.</span></span> <span data-ttu-id="98118-227">응용 프로그램은 사용자가 선택할 수 있는 <xref:System.Windows.Window> 표시 되는 경우에만 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-227">An application can only be switched to if it has a visible <xref:System.Windows.Window> that a user can select.</span></span> <span data-ttu-id="98118-228">현재 선택 된 <xref:System.Windows.Window>은 *활성 창* ( *전경 창*이 라고도 함) 이며 사용자 입력을 받는 <xref:System.Windows.Window>입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-228">The currently selected <xref:System.Windows.Window> is the *active window* (also known as the *foreground window*) and is the <xref:System.Windows.Window> that receives user input.</span></span> <span data-ttu-id="98118-229">활성 창이 있는 응용 프로그램은 *활성 응용 프로그램* (또는 *포그라운드 응용 프로그램*)입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-229">The application with the active window is the *active application* (or *foreground application*).</span></span> <span data-ttu-id="98118-230">다음과 같은 경우에 애플리케이션이 활성 애플리케이션이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-230">An application becomes the active application in the following circumstances:</span></span>

- <span data-ttu-id="98118-231">시작 되 고 <xref:System.Windows.Window>표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-231">It is launched and shows a <xref:System.Windows.Window>.</span></span>

- <span data-ttu-id="98118-232">사용자는 응용 프로그램에서 <xref:System.Windows.Window>를 선택 하 여 다른 응용 프로그램에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-232">A user switches from another application by selecting a <xref:System.Windows.Window> in the application.</span></span>

<span data-ttu-id="98118-233"><xref:System.Windows.Application.Activated?displayProperty=nameWithType> 이벤트를 처리 하 여 응용 프로그램이 활성화 되는 시기를 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-233">You can detect when an application becomes active by handling the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> event.</span></span>

<span data-ttu-id="98118-234">마찬가지로 다음과 같은 경우에는 애플리케이션이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-234">Likewise, an application can become inactive in the following circumstances:</span></span>

- <span data-ttu-id="98118-235">사용자가 현재 애플리케이션에서 다른 애플리케이션으로 전환하는 경우</span><span class="sxs-lookup"><span data-stu-id="98118-235">A user switches to another application from the current one.</span></span>

- <span data-ttu-id="98118-236">애플리케이션이 종료되는 경우</span><span class="sxs-lookup"><span data-stu-id="98118-236">When the application shuts down.</span></span>

<span data-ttu-id="98118-237"><xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 이벤트를 처리 하 여 응용 프로그램이 비활성 상태가 되는 경우를 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-237">You can detect when an application becomes inactive by handling the <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> event.</span></span>

<span data-ttu-id="98118-238">다음 코드에서는 <xref:System.Windows.Application.Activated> 및 <xref:System.Windows.Application.Deactivated> 이벤트를 처리 하 여 응용 프로그램이 활성 상태 인지 여부를 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-238">The following code shows how to handle the <xref:System.Windows.Application.Activated> and <xref:System.Windows.Application.Deactivated> events to determine whether an application is active.</span></span>

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

<span data-ttu-id="98118-239"><xref:System.Windows.Window>를 활성화 하 고 비활성화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-239">A <xref:System.Windows.Window> can also be activated and deactivated.</span></span> <span data-ttu-id="98118-240">자세한 내용은 <xref:System.Windows.Window.Activated?displayProperty=nameWithType> 및 <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-240">See <xref:System.Windows.Window.Activated?displayProperty=nameWithType> and <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType> for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-241"><xref:System.Windows.Application.Activated?displayProperty=nameWithType> 또는 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>는 Xbap에 대해 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-241">Neither <xref:System.Windows.Application.Activated?displayProperty=nameWithType> nor <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> is raised for XBAPs.</span></span>

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a><span data-ttu-id="98118-242">애플리케이션 종료</span><span class="sxs-lookup"><span data-stu-id="98118-242">Application Shutdown</span></span>

<span data-ttu-id="98118-243">다음과 같은 이유로 애플리케이션이 종료되면 애플리케이션 수명이 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="98118-243">The life of an application ends when it is shut down, which can occur for the following reasons:</span></span>

- <span data-ttu-id="98118-244">사용자는 모든 <xref:System.Windows.Window>를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-244">A user closes every <xref:System.Windows.Window>.</span></span>

- <span data-ttu-id="98118-245">사용자가 기본 <xref:System.Windows.Window>를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-245">A user closes the main <xref:System.Windows.Window>.</span></span>

- <span data-ttu-id="98118-246">사용자가 로그 오프 하거나 종료 하 여 Windows 세션을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-246">A user ends the Windows session by logging off or shutting down.</span></span>

- <span data-ttu-id="98118-247">애플리케이션별 조건이 충족된 경우</span><span class="sxs-lookup"><span data-stu-id="98118-247">An application-specific condition has been met.</span></span>

<span data-ttu-id="98118-248">응용 프로그램 종료를 관리 하는 데 도움을 주는 <xref:System.Windows.Application> <xref:System.Windows.Application.Shutdown%2A> 메서드, <xref:System.Windows.Application.ShutdownMode%2A> 속성 및 <xref:System.Windows.Application.SessionEnding> 및 <xref:System.Windows.Application.Exit> 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-248">To help you manage application shutdown, <xref:System.Windows.Application> provides the <xref:System.Windows.Application.Shutdown%2A> method, the <xref:System.Windows.Application.ShutdownMode%2A> property, and the <xref:System.Windows.Application.SessionEnding> and <xref:System.Windows.Application.Exit> events.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-249"><xref:System.Windows.Application.Shutdown%2A>는 <xref:System.Security.Permissions.UIPermission>있는 응용 프로그램 에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-249"><xref:System.Windows.Application.Shutdown%2A> can only be called from applications that have <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="98118-250">독립 실행형 WPF 응용 프로그램에는 항상이 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-250">Standalone WPF applications always have this permission.</span></span> <span data-ttu-id="98118-251">그러나 인터넷 영역 부분 신뢰 보안 샌드박스에서 실행 되는 Xbap는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-251">However, XBAPs running in the Internet zone partial-trust security sandbox do not.</span></span>

#### <a name="shutdown-mode"></a><span data-ttu-id="98118-252">종료 모드</span><span class="sxs-lookup"><span data-stu-id="98118-252">Shutdown Mode</span></span>

<span data-ttu-id="98118-253">대부분의 애플리케이션은 모든 창을 닫거나 주 창을 닫으면 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-253">Most applications shut down either when all the windows are closed or when the main window is closed.</span></span> <span data-ttu-id="98118-254">하지만 다른 애플리케이션과 관련된 조건이 특정 애플리케이션의 종료 시점을 결정하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-254">Sometimes, however, other application-specific conditions may determine when an application shuts down.</span></span> <span data-ttu-id="98118-255">다음 <xref:System.Windows.ShutdownMode> 열거형 값 중 하나를 사용 하 여 <xref:System.Windows.Application.ShutdownMode%2A>를 설정 하 여 응용 프로그램이 종료 되는 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-255">You can specify the conditions under which your application will shut down by setting <xref:System.Windows.Application.ShutdownMode%2A> with one of the following <xref:System.Windows.ShutdownMode> enumeration values:</span></span>

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

<span data-ttu-id="98118-256"><xref:System.Windows.Application.ShutdownMode%2A>의 기본값은 <xref:System.Windows.ShutdownMode.OnLastWindowClose>입니다. 즉, 사용자가 응용 프로그램의 마지막 창을 닫을 때 응용 프로그램이 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-256">The default value of <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnLastWindowClose>, which means that an application automatically shuts down when the last window in the application is closed by the user.</span></span> <span data-ttu-id="98118-257">그러나 주 창을 닫을 때 응용 프로그램을 종료 해야 하는 경우에는 <xref:System.Windows.Application.ShutdownMode%2A>를 <xref:System.Windows.ShutdownMode.OnMainWindowClose>로 설정 하면 WPF가 자동으로이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-257">However, if your application should be shut down when the main window is closed, WPF automatically does that if you set <xref:System.Windows.Application.ShutdownMode%2A> to <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span> <span data-ttu-id="98118-258">이는 다음 예에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-258">This is shown in the following example.</span></span>

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

<span data-ttu-id="98118-259">응용 프로그램 특정 종료 조건이 있는 경우 <xref:System.Windows.Application.ShutdownMode%2A>를 <xref:System.Windows.ShutdownMode.OnExplicitShutdown>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-259">When you have application-specific shutdown conditions, you set <xref:System.Windows.Application.ShutdownMode%2A> to <xref:System.Windows.ShutdownMode.OnExplicitShutdown>.</span></span> <span data-ttu-id="98118-260">이 경우 <xref:System.Windows.Application.Shutdown%2A> 메서드를 명시적으로 호출 하 여 응용 프로그램을 종료 하는 것은 사용자의 책임입니다. 그렇지 않으면 모든 창이 닫혀 있어도 응용 프로그램은 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-260">In this case, it is your responsibility to shut an application down by explicitly calling the <xref:System.Windows.Application.Shutdown%2A> method; otherwise, your application will continue running even if all the windows are closed.</span></span> <span data-ttu-id="98118-261"><xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnLastWindowClose> 또는 <xref:System.Windows.ShutdownMode.OnMainWindowClose>일 경우 <xref:System.Windows.Application.Shutdown%2A>가 암시적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-261">Note that <xref:System.Windows.Application.Shutdown%2A> is called implicitly when the <xref:System.Windows.Application.ShutdownMode%2A> is either <xref:System.Windows.ShutdownMode.OnLastWindowClose> or <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-262"><xref:System.Windows.Application.ShutdownMode%2A>는 XBAP에서 설정할 수 있지만 무시 됩니다. XBAP는 브라우저에서 벗어나거나 XBAP를 호스트 하는 브라우저가 닫히면 항상 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-262"><xref:System.Windows.Application.ShutdownMode%2A> can be set from an XBAP, but it is ignored; an XBAP is always shut down when it is navigated away from in a browser or when the browser that hosts the XBAP is closed.</span></span> <span data-ttu-id="98118-263">자세한 내용은 [탐색 개요](navigation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-263">For more information, see [Navigation Overview](navigation-overview.md).</span></span>

#### <a name="session-ending"></a><span data-ttu-id="98118-264">세션 종료</span><span class="sxs-lookup"><span data-stu-id="98118-264">Session Ending</span></span>

<span data-ttu-id="98118-265"><xref:System.Windows.Application.ShutdownMode%2A> 속성에서 설명 하는 종료 조건은 응용 프로그램에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-265">The shutdown conditions that are described by the <xref:System.Windows.Application.ShutdownMode%2A> property are specific to an application.</span></span> <span data-ttu-id="98118-266">하지만 외부 조건에 따라 애플리케이션이 종료되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-266">In some cases, though, an application may shut down as a result of an external condition.</span></span> <span data-ttu-id="98118-267">가장 일반적인 외부 조건은 사용자가 다음 작업을 통해 Windows 세션을 종료할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-267">The most common external condition occurs when a user ends the Windows session by the following actions:</span></span>

- <span data-ttu-id="98118-268">로그오프</span><span class="sxs-lookup"><span data-stu-id="98118-268">Logging off</span></span>

- <span data-ttu-id="98118-269">종료</span><span class="sxs-lookup"><span data-stu-id="98118-269">Shutting down</span></span>

- <span data-ttu-id="98118-270">다시 시작</span><span class="sxs-lookup"><span data-stu-id="98118-270">Restarting</span></span>

- <span data-ttu-id="98118-271">최대 절전 모드</span><span class="sxs-lookup"><span data-stu-id="98118-271">Hibernating</span></span>

<span data-ttu-id="98118-272">Windows 세션이 종료 되는 시기를 검색 하기 위해 다음 예제와 같이 <xref:System.Windows.Application.SessionEnding> 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-272">To detect when a Windows session ends, you can handle the <xref:System.Windows.Application.SessionEnding> event, as illustrated in the following example.</span></span>

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

<span data-ttu-id="98118-273">이 예제에서 코드는 <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> 속성을 검사 하 여 Windows 세션이 종료 되는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-273">In this example, the code inspects the <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> property to determine how the Windows session is ending.</span></span> <span data-ttu-id="98118-274">또한 이 값을 사용하여 사용자에게 확인 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-274">It uses this value to display a confirmation message to the user.</span></span> <span data-ttu-id="98118-275">사용자가 세션을 종료 하지 않으려는 경우 코드는 `true`으로 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 설정 하 여 Windows 세션을 종료 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-275">If the user does not want the session to end, the code sets <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> to `true` to prevent the Windows session from ending.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-276"><xref:System.Windows.Application.SessionEnding>는 Xbap에 대해 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-276"><xref:System.Windows.Application.SessionEnding> is not raised for XBAPs.</span></span>

#### <a name="exit"></a><span data-ttu-id="98118-277">끝내기</span><span class="sxs-lookup"><span data-stu-id="98118-277">Exit</span></span>

<span data-ttu-id="98118-278">애플리케이션이 종료될 때 애플리케이션 상태 유지와 같은 몇 가지 최종 처리를 수행해야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-278">When an application shuts down, it may need to perform some final processing, such as persisting application state.</span></span> <span data-ttu-id="98118-279">이러한 경우 `App_Exit` 이벤트 처리기가 다음 예제에서 수행 하므로 <xref:System.Windows.Application.Exit> 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-279">For these situations, you can handle the <xref:System.Windows.Application.Exit> event, as the `App_Exit` event handler does in the following example.</span></span> <span data-ttu-id="98118-280">이 클래스는 *app.xaml* 파일에서 이벤트 처리기로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-280">It is defined as an event handler in the *App.xaml* file.</span></span> <span data-ttu-id="98118-281">해당 구현은 *App.xaml.cs* 및 *응용 프로그램 .xaml* 파일에서 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-281">Its implementation is highlighted in the *App.xaml.cs* and *Application.xaml.vb* files.</span></span>

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

<span data-ttu-id="98118-282">전체 예제는 [응용 프로그램 세션 간에 응용 프로그램 범위 속성 유지 및 복원](persist-and-restore-application-scope-properties.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-282">For the complete example, see [Persist and Restore Application-Scope Properties Across Application Sessions](persist-and-restore-application-scope-properties.md).</span></span>

<span data-ttu-id="98118-283"><xref:System.Windows.Application.Exit>는 독립 실행형 응용 프로그램과 Xbap 모두에서 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-283"><xref:System.Windows.Application.Exit> can be handled by both standalone applications and XBAPs.</span></span> <span data-ttu-id="98118-284">Xbap의 경우 다음과 같은 경우 <xref:System.Windows.Application.Exit> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-284">For XBAPs, <xref:System.Windows.Application.Exit> is raised when in the following circumstances:</span></span>

- <span data-ttu-id="98118-285">에서 XBAP를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-285">An XBAP is navigated away from.</span></span>

- <span data-ttu-id="98118-286">Internet Explorer에서 XBAP를 호스트 하는 탭이 닫혀 있는 경우</span><span class="sxs-lookup"><span data-stu-id="98118-286">In Internet Explorer, when the tab that is hosting the XBAP is closed.</span></span>

- <span data-ttu-id="98118-287">브라우저가 닫힌 경우</span><span class="sxs-lookup"><span data-stu-id="98118-287">When the browser is closed.</span></span>

#### <a name="exit-code"></a><span data-ttu-id="98118-288">종료 코드</span><span class="sxs-lookup"><span data-stu-id="98118-288">Exit Code</span></span>

<span data-ttu-id="98118-289">대부분의 경우 애플리케이션은 운영 체제에서 사용자 요청에 대한 응답으로 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-289">Applications are mostly launched by the operating system in response to a user request.</span></span> <span data-ttu-id="98118-290">하지만 다른 애플리케이션에서 일부 특정 작업을 수행하기 위해 애플리케이션을 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-290">However, an application can be launched by another application to perform some specific task.</span></span> <span data-ttu-id="98118-291">시작된 애플리케이션이 종료될 경우 시작하는 애플리케이션에서 시작된 애플리케이션이 종료되는 조건을 알고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-291">When the launched application shuts down, the launching application may want to know the condition under which the launched application shut down.</span></span> <span data-ttu-id="98118-292">이러한 상황에서 Windows는 응용 프로그램이 종료 될 때 응용 프로그램 종료 코드를 반환할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-292">In these situations, Windows allows applications to return an application exit code on shutdown.</span></span> <span data-ttu-id="98118-293">기본적으로 WPF 응용 프로그램은 종료 코드 값 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-293">By default, WPF applications return an exit code value of 0.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-294">Visual Studio에서 디버그할 때 응용 프로그램이 종료 되 면 **출력** 창에 다음과 같은 메시지에서 응용 프로그램 종료 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-294">When you debug from Visual Studio, the application exit code is displayed in the **Output** window when the application shuts down, in a message that looks like the following:</span></span>
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> <span data-ttu-id="98118-295">**보기** 메뉴에서 **출력** 을 클릭 하 여 **출력** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98118-295">You open the **Output** window by clicking **Output** on the **View** menu.</span></span>

<span data-ttu-id="98118-296">종료 코드를 변경 하려면 정수 인수를 허용 하는 <xref:System.Windows.Application.Shutdown%28System.Int32%29> 오버 로드를 호출 하 여 종료 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-296">To change the exit code, you can call the <xref:System.Windows.Application.Shutdown%28System.Int32%29> overload, which accepts an integer argument to be the exit code:</span></span>

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

<span data-ttu-id="98118-297"><xref:System.Windows.Application.Exit> 이벤트를 처리 하 여 종료 코드의 값을 검색 하 고 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-297">You can detect the value of the exit code, and change it, by handling the <xref:System.Windows.Application.Exit> event.</span></span> <span data-ttu-id="98118-298"><xref:System.Windows.Application.Exit> 이벤트 처리기에는 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> 속성을 사용 하 여 종료 코드에 대 한 액세스를 제공 하는 <xref:System.Windows.ExitEventArgs> 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-298">The <xref:System.Windows.Application.Exit> event handler is passed an <xref:System.Windows.ExitEventArgs> which provides access to the exit code with the <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> property.</span></span> <span data-ttu-id="98118-299">자세한 내용은 <xref:System.Windows.Application.Exit>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-299">For more information, see <xref:System.Windows.Application.Exit>.</span></span>

> [!NOTE]
> <span data-ttu-id="98118-300">독립 실행형 응용 프로그램과 Xbap 모두에서 종료 코드를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-300">You can set the exit code in both standalone applications and XBAPs.</span></span> <span data-ttu-id="98118-301">그러나 Xbap의 종료 코드 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-301">However, the exit code value is ignored for XBAPs.</span></span>

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a><span data-ttu-id="98118-302">처리되지 않은 예외</span><span class="sxs-lookup"><span data-stu-id="98118-302">Unhandled Exceptions</span></span>

<span data-ttu-id="98118-303">원하지 않는 예외를 throw하는 경우와 같이 애플리케이션이 비정상적인 상황에서 종료되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-303">Sometimes an application may shut down under abnormal conditions, such as when an unanticipated exception is thrown.</span></span> <span data-ttu-id="98118-304">이런 경우에는 애플리케이션에 예외를 검색하고 처리할 코드가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-304">In this case, the application may not have the code to detect and process the exception.</span></span> <span data-ttu-id="98118-305">이런 형식의 예외가 처리되지 않은 예외이며, 애플리케이션이 닫히기 전에 다음 그림에 표시된 것과 비슷한 알림으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-305">This type of exception is an unhandled exception; a notification similar to that shown in the following figure is displayed before the application is closed.</span></span>

![처리 되지 않은 예외 알림을 보여 주는 스크린샷](./media/application-management-overview/unhandled-exception-notification.png)

<span data-ttu-id="98118-307">사용자 환경의 관점에서는 애플리케이션에서 다음과 같은 작업의 일부 또는 전부를 수행하여 이러한 기본 동작을 방지하는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-307">From the user experience perspective, it is better for an application to avoid this default behavior by doing some or all of the following:</span></span>

- <span data-ttu-id="98118-308">사용자에게 친숙한 정보 표시</span><span class="sxs-lookup"><span data-stu-id="98118-308">Displaying user-friendly information.</span></span>

- <span data-ttu-id="98118-309">애플리케이션을 실행 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="98118-309">Attempting to keep an application running.</span></span>

- <span data-ttu-id="98118-310">Windows 이벤트 로그에 자세한 개발자에 게 친숙 한 예외 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-310">Recording detailed, developer-friendly exception information in the Windows event log.</span></span>

<span data-ttu-id="98118-311">이러한 지원을 구현 하는 것은 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트가 발생 하는 처리 되지 않은 예외를 검색할 수 있는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="98118-311">Implementing this support depends on being able to detect unhandled exceptions, which is what the <xref:System.Windows.Application.DispatcherUnhandledException> event is raised for.</span></span>

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

<span data-ttu-id="98118-312"><xref:System.Windows.Application.DispatcherUnhandledException> 이벤트 처리기에는 예외 자체 (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>)를 포함 하 여 처리 되지 않은 예외와 관련 된 컨텍스트 정보를 포함 하는 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> 매개 변수가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-312">The <xref:System.Windows.Application.DispatcherUnhandledException> event handler is passed a <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parameter that contains contextual information regarding the unhandled exception, including the exception itself (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="98118-313">이 정보를 사용하여 예외를 처리하는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-313">You can use this information to determine how to handle the exception.</span></span>

<span data-ttu-id="98118-314"><xref:System.Windows.Application.DispatcherUnhandledException>를 처리 하는 경우 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> 속성을 `true`로 설정 해야 합니다. 그렇지 않으면 WPF는 예외를 아직 처리 되지 않은 것으로 간주 하 고 앞에서 설명한 기본 동작으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="98118-314">When you handle <xref:System.Windows.Application.DispatcherUnhandledException>, you should set the <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> property to `true`; otherwise, WPF still considers the exception to be unhandled and reverts to the default behavior described earlier.</span></span> <span data-ttu-id="98118-315">처리 되지 않은 예외가 발생 하 고 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트가 처리 되지 않거나 이벤트가 처리 되 고 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A>을 `false`로 설정 하면 응용 프로그램이 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-315">If an unhandled exception is raised and either the <xref:System.Windows.Application.DispatcherUnhandledException> event is not handled, or the event is handled and <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> is set to `false`, the application shuts down immediately.</span></span> <span data-ttu-id="98118-316">또한 다른 <xref:System.Windows.Application> 이벤트는 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-316">Furthermore, no other <xref:System.Windows.Application> events are raised.</span></span> <span data-ttu-id="98118-317">따라서 응용 프로그램이 종료 되기 전에 실행 해야 하는 코드가 응용 프로그램에 있는 경우 <xref:System.Windows.Application.DispatcherUnhandledException>를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-317">Consequently, you need to handle <xref:System.Windows.Application.DispatcherUnhandledException> if your application has code that must run before the application shuts down.</span></span>

<span data-ttu-id="98118-318">처리되지 않은 예외의 결과로 애플리케이션이 종료될 수는 있지만 애플리케이션은 대개 다음 섹션에서 설명하는 것처럼 사용자 요청에 대한 응답으로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-318">Although an application may shut down as a result of an unhandled exception, an application usually shuts down in response to a user request, as discussed in the next section.</span></span>

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a><span data-ttu-id="98118-319">애플리케이션 수명 이벤트</span><span class="sxs-lookup"><span data-stu-id="98118-319">Application Lifetime Events</span></span>

<span data-ttu-id="98118-320">독립 실행형 응용 프로그램 및 Xbap는 정확히 동일한 수명이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="98118-320">Standalone applications and XBAPs don't have exactly the same lifetimes.</span></span> <span data-ttu-id="98118-321">다음 그림에서는 독립 실행형 애플리케이션 수명에서의 주요 이벤트와 이러한 이벤트가 발생하는 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-321">The following figure illustrates the key events in the lifetime of a standalone application and shows the sequence in which they are raised.</span></span>

<span data-ttu-id="98118-322">![독립 실행형 &#45; 응용 프로그램 응용 프로그램 개체 이벤트](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")</span><span class="sxs-lookup"><span data-stu-id="98118-322">![Standalone Application &#45; Application Object Events](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")</span></span>

<span data-ttu-id="98118-323">마찬가지로, 다음 그림은 XBAP의 수명에서 키 이벤트를 보여 주고이 이벤트가 발생 하는 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-323">Likewise, the following figure illustrates the key events in the lifetime of an XBAP, and shows the sequence in which they are raised.</span></span>

<span data-ttu-id="98118-324">![XBAP &#45; 응용 프로그램 개체 이벤트](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")</span><span class="sxs-lookup"><span data-stu-id="98118-324">![XBAP &#45; Application Object Events](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")</span></span>

## <a name="see-also"></a><span data-ttu-id="98118-325">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98118-325">See also</span></span>

- <xref:System.Windows.Application>
- [<span data-ttu-id="98118-326">WPF 창 개요</span><span class="sxs-lookup"><span data-stu-id="98118-326">WPF Windows Overview</span></span>](wpf-windows-overview.md)
- [<span data-ttu-id="98118-327">탐색 개요</span><span class="sxs-lookup"><span data-stu-id="98118-327">Navigation Overview</span></span>](navigation-overview.md)
- [<span data-ttu-id="98118-328">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="98118-328">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
- [<span data-ttu-id="98118-329">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="98118-329">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- <span data-ttu-id="98118-330">[응용 프로그램 모델: 방법 도움말 항목](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="98118-330">[Application Model: How-to Topics](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))</span></span>
- [<span data-ttu-id="98118-331">애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="98118-331">Application Development</span></span>](index.md)
