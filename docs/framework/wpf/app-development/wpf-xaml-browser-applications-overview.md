---
title: WPF XAML 브라우저 애플리케이션 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XBAP [WPF], XAML browser application
- WPF XAML browser applications (XBAP)
- XAML browser applications (XBAP)
- browser-hosted applications [WPF]
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
ms.openlocfilehash: a4d3b808aee14d5d2f29053b0c60798f9f626e8c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636330"
---
# <a name="wpf-xaml-browser-applications-overview"></a><span data-ttu-id="0fd0e-102">WPF XAML 브라우저 애플리케이션 개요</span><span class="sxs-lookup"><span data-stu-id="0fd0e-102">WPF XAML Browser Applications Overview</span></span>
<a name="introduction"></a><span data-ttu-id="0fd0e-103">Xbap (XAML 브라우저 응용 프로그램)는 웹 응용 프로그램과 리치 클라이언트 응용 프로그램의 기능을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-103">XAML browser applications (XBAPs) combines features of both Web applications and rich-client applications.</span></span> <span data-ttu-id="0fd0e-104">XBAP는 웹 애플리케이션처럼 웹 서버에 배포할 수 있으며 Internet Explorer 또는 Firefox에서 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-104">Like Web applications, XBAPs can be deployed to a Web server and started from Internet Explorer or Firefox.</span></span> <span data-ttu-id="0fd0e-105">풍부한 클라이언트 응용 프로그램과 마찬가지로 Xbap는 WPF의 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-105">Like rich-client applications, XBAPs can take advantage of the capabilities of WPF.</span></span> <span data-ttu-id="0fd0e-106">XBAP를 개발하는 것은 리치 클라이언트 개발과도 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-106">Developing XBAPs is also similar to rich-client development.</span></span> <span data-ttu-id="0fd0e-107">이 항목에서는 XBAP 개발에 대한 간단하고 고급 수준의 소개를 제공하며 XBAP 개발이 표준 리치 클라이언트 개발과 다른 점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-107">This topic provides a simple, high-level introduction to XBAP development and describes where XBAP development differs from standard rich-client development.</span></span>

 <span data-ttu-id="0fd0e-108">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-108">This topic contains the following sections:</span></span>

- [<span data-ttu-id="0fd0e-109">새 XBAP(XAML 브라우저 애플리케이션) 만들기</span><span class="sxs-lookup"><span data-stu-id="0fd0e-109">Creating a New XAML Browser Application (XBAP)</span></span>](#creating_a_new_xaml_browser_application_xbap)

- [<span data-ttu-id="0fd0e-110">XBAP 배포</span><span class="sxs-lookup"><span data-stu-id="0fd0e-110">Deploying an XBAP</span></span>](#deploying_a_xbap)

- [<span data-ttu-id="0fd0e-111">호스트 웹 페이지와 통신</span><span class="sxs-lookup"><span data-stu-id="0fd0e-111">Communicating with the Host Web Page</span></span>](#communicating_with_the_host_web_page)

- [<span data-ttu-id="0fd0e-112">XBAP 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0fd0e-112">XBAP Security Considerations</span></span>](#xbap_security_considerations)

- [<span data-ttu-id="0fd0e-113">XBAP 시작 시간 성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0fd0e-113">XBAP Start Time Performance Considerations</span></span>](#xbap_start_time_performance_considerations)

<a name="creating_a_new_xaml_browser_application_xbap"></a>
## <a name="creating-a-new-xaml-browser-application-xbap"></a><span data-ttu-id="0fd0e-114">새 XBAP(XAML 브라우저 애플리케이션) 만들기</span><span class="sxs-lookup"><span data-stu-id="0fd0e-114">Creating a New XAML Browser Application (XBAP)</span></span>
 <span data-ttu-id="0fd0e-115">새 XBAP 프로젝트를 만드는 가장 간단한 방법은 Visual Studio를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-115">The simplest way to create a new XBAP project is with Visual Studio.</span></span> <span data-ttu-id="0fd0e-116">새 프로젝트를 만들려면 템플릿 목록에서 **WPF 브라우저 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-116">When creating a new project, select **WPF Browser Application** from the list of templates.</span></span> <span data-ttu-id="0fd0e-117">자세한 내용은 [방법: 새 WPF 브라우저 애플리케이션 프로젝트 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-117">For more information, see [How to: Create a New WPF Browser Application Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).</span></span>

 <span data-ttu-id="0fd0e-118">XBAP 프로젝트를 실행하면 독립 실행형 창이 아닌 브라우저 창에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-118">When you run the XBAP project, it opens in a browser window instead of a stand-alone window.</span></span> <span data-ttu-id="0fd0e-119">Visual Studio에서 XBAP를 디버깅할 때 응용 프로그램은 인터넷 영역 권한으로 실행 되므로 이러한 사용 권한을 초과 하는 경우 보안 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-119">When you debug the XBAP from Visual Studio, the application runs with Internet zone permission and will therefore throw security exceptions if those permissions are exceeded.</span></span> <span data-ttu-id="0fd0e-120">자세한 내용은 [보안](../security-wpf.md) 및 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-120">For more information, see [Security](../security-wpf.md) and [WPF Partial Trust Security](../wpf-partial-trust-security.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0fd0e-121">Visual Studio를 사용 하 여 개발 하지 않거나 프로젝트 파일에 대 한 자세한 내용을 보려면 [WPF 응용 프로그램 빌드](building-a-wpf-application-wpf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-121">If you are not developing with Visual Studio or want to learn more about the project files, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>

<a name="deploying_a_xbap"></a>
## <a name="deploying-an-xbap"></a><span data-ttu-id="0fd0e-122">XBAP 배포</span><span class="sxs-lookup"><span data-stu-id="0fd0e-122">Deploying an XBAP</span></span>
 <span data-ttu-id="0fd0e-123">XBAP를 빌드하는 경우 출력에는 다음 세 가지 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-123">When you build an XBAP, the output includes the following three files:</span></span>

|<span data-ttu-id="0fd0e-124">File</span><span class="sxs-lookup"><span data-stu-id="0fd0e-124">File</span></span>|<span data-ttu-id="0fd0e-125">설명</span><span class="sxs-lookup"><span data-stu-id="0fd0e-125">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="0fd0e-126">실행 파일(.exe)</span><span class="sxs-lookup"><span data-stu-id="0fd0e-126">Executable (.exe)</span></span>|<span data-ttu-id="0fd0e-127">컴파일된 코드가 포함되며 확장명이 .exe입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-127">This contains the compiled code and has an .exe extension.</span></span>|
|<span data-ttu-id="0fd0e-128">애플리케이션 매니페스트(.manifest)</span><span class="sxs-lookup"><span data-stu-id="0fd0e-128">Application manifest (.manifest)</span></span>|<span data-ttu-id="0fd0e-129">애플리케이션과 연결된 메타데이터가 포함되며 확장명이 .manifest입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-129">This contains metadata associated with the application and has a .manifest extension.</span></span>|
|<span data-ttu-id="0fd0e-130">배포 매니페스트(.xbap)</span><span class="sxs-lookup"><span data-stu-id="0fd0e-130">Deployment manifest (.xbap)</span></span>|<span data-ttu-id="0fd0e-131">이 파일은 ClickOnce에서 응용 프로그램을 배포 하는 데 사용 하는 정보를 포함 하며 확장명이입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-131">This file contains the information that ClickOnce uses to deploy the application and has the .xbap extension.</span></span>|

 <span data-ttu-id="0fd0e-132">웹 서버 (예: Microsoft 인터넷 정보 서비스 (IIS) 5.0 이상 버전)에 Xbap를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-132">You deploy XBAPs to a Web server, for example Microsoft Internet Information Services (IIS) 5.0 or later versions.</span></span> <span data-ttu-id="0fd0e-133">웹 서버에 .NET Framework을 설치할 필요는 없지만 WPF 다목적 MIME (인터넷 메일 확장) 형식 및 파일 이름 확장명을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-133">You do not have to install the .NET Framework on the Web server, but you do have to register the WPF Multipurpose Internet Mail Extensions (MIME) types and file name extensions.</span></span> <span data-ttu-id="0fd0e-134">자세한 내용은 [IIS 5.0 및 IIS 6.0을 구성하여 WPF 애플리케이션 배포](how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-134">For more information, see [Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications](how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md).</span></span>

 <span data-ttu-id="0fd0e-135">배포를 위해 XBAP를 준비하려면 .exe 및 연결된 매니페스트를 웹 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-135">To prepare your XBAP for deployment, copy the .exe and the associated manifests to the Web server.</span></span> <span data-ttu-id="0fd0e-136">확장명이 .xbap인 파일인 배포 매니페스트를 여는 하이퍼링크가 포함된 HTML 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-136">Create an HTML page that contains a hyperlink to open the deployment manifest, which is the file that has the .xbap extension.</span></span> <span data-ttu-id="0fd0e-137">사용자가 xbap 파일에 대 한 링크를 클릭 하면 ClickOnce에서 응용 프로그램을 다운로드 하 고 시작 하는 메커니즘을 자동으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-137">When the user clicks the link to the .xbap file, ClickOnce automatically handles the mechanics of downloading and starting the application.</span></span> <span data-ttu-id="0fd0e-138">다음 예제 코드는 XBAP를 가리키는 하이퍼링크가 포함된 HTML 페이지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-138">The following example code shows an HTML page that contains a hyperlink that points to an XBAP.</span></span>

```html
<html>
    <head></head>
    <body>
        <a href="XbapEx.xbap">Click this link to launch the application</a>
    </body>
</html>
```

 <span data-ttu-id="0fd0e-139">웹 페이지 프레임에서 XBAP를 호스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-139">You can also host an XBAP in the frame of a Web page.</span></span> <span data-ttu-id="0fd0e-140">하나 이상의 프레임이 있는 웹 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-140">Create a Web page with one or more frames.</span></span> <span data-ttu-id="0fd0e-141">프레임의 원본 속성을 배포 매니페스트 파일로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-141">Set the source property of a frame to the deployment manifest file.</span></span> <span data-ttu-id="0fd0e-142">호스팅 웹 페이지와 XBAP 간의 통신에 기본 제공 메커니즘을 사용하려면 프레임에 애플리케이션을 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-142">If you want to use the built-in mechanism to communicate between the hosting Web page and the XBAP, you must host the application in a frame.</span></span> <span data-ttu-id="0fd0e-143">다음 예제 코드는 두 프레임이 있는 HTML 페이지를 보여 주며 두 번째 프레임의 원본은 XBAP로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-143">The following example code shows an HTML page with two frames, the source for the second frame is set to an XBAP.</span></span>

```html
<html>
    <head>
        <title>A page with frames</title>
    </head>
    <frameset cols="50%,50%">
        <frame src="introduction.htm">
        <frame src="XbapEx.xbap">
    </frameset>
</html>
```

### <a name="clearing-cached-xbaps"></a><span data-ttu-id="0fd0e-144">캐시된 XBAP 지우기</span><span class="sxs-lookup"><span data-stu-id="0fd0e-144">Clearing Cached XBAPs</span></span>
 <span data-ttu-id="0fd0e-145">XBAP를 다시 빌드하여 시작한 후 일부 경우에 이전 버전의 XBAP가 열린 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-145">In some situations after rebuilding and starting your XBAP, you may find that an earlier version of the XBAP is opened.</span></span> <span data-ttu-id="0fd0e-146">예를 들어 XBAP 어셈블리 버전 번호가 정적이고 명령줄에서 XBAP를 시작하는 경우 이러한 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-146">For example, this behavior may occur when your XBAP assembly version number is static and you start the XBAP from the command line.</span></span> <span data-ttu-id="0fd0e-147">이 경우 캐시된 버전(이전에 시작된 버전)과 새 버전 사이 버전 번호가 같게 유지되므로 XBAP의 새 버전이 다운로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-147">In this case, because the version number between the cached version (the version that was previously started) and the new version remains the same, the new version of the XBAP is not downloaded.</span></span> <span data-ttu-id="0fd0e-148">대신, 캐시된 버전이 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-148">Instead, the cached version is loaded.</span></span>

 <span data-ttu-id="0fd0e-149">이러한 경우 명령 프롬프트에서 **Mage** 명령 (Visual Studio 또는 Windows SDK와 함께 설치 됨)을 사용 하 여 캐시 된 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-149">In these situations, you can remove the cached version by using the **Mage** command (installed with Visual Studio or the Windows SDK) at the command prompt.</span></span> <span data-ttu-id="0fd0e-150">다음 명령은 애플리케이션 캐시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-150">The following command clears the application cache.</span></span>

 ```console
 Mage.exe -cc
 ```

 <span data-ttu-id="0fd0e-151">이 명령은 최신 버전의 XBAP가 시작되도록 보장해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-151">This command guarantees that the latest version of your XBAP is started.</span></span> <span data-ttu-id="0fd0e-152">Visual Studio에서 응용 프로그램을 디버깅 하는 경우 최신 버전의 XBAP를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-152">When you debug your application in Visual Studio, the latest version of your XBAP should be started.</span></span> <span data-ttu-id="0fd0e-153">일반적으로 배포 시마다 배포 버전 번호를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-153">In general, you should update your deployment version number with each build.</span></span> <span data-ttu-id="0fd0e-154">Mage에 자세한 내용은 [Mage.exe(매니페스트 생성 및 편집 도구)](../../tools/mage-exe-manifest-generation-and-editing-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-154">For more information about Mage, see [Mage.exe (Manifest Generation and Editing Tool)](../../tools/mage-exe-manifest-generation-and-editing-tool.md).</span></span>

<a name="communicating_with_the_host_web_page"></a>
## <a name="communicating-with-the-host-web-page"></a><span data-ttu-id="0fd0e-155">호스트 웹 페이지와 통신</span><span class="sxs-lookup"><span data-stu-id="0fd0e-155">Communicating with the Host Web Page</span></span>
 <span data-ttu-id="0fd0e-156">애플리케이션이 HTML 프레임에서 호스팅되는 경우 XBAP가 포함된 웹 페이지와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-156">When the application is hosted in an HTML frame, you can communicate with the Web page that contains the XBAP.</span></span> <span data-ttu-id="0fd0e-157"><xref:System.Windows.Interop.BrowserInteropHelper>의 <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> 속성을 검색 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-157">You do this by retrieving the <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> property of <xref:System.Windows.Interop.BrowserInteropHelper>.</span></span> <span data-ttu-id="0fd0e-158">이 속성은 HTML 창을 나타내는 스크립트 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-158">This property returns a script object that represents the HTML window.</span></span> <span data-ttu-id="0fd0e-159">그런 다음 정규 점(dot) 구문을 사용하여 [창 개체](https://go.microsoft.com/fwlink/?LinkId=160274)에서 속성, 메서드 및 이벤트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-159">You can then access the properties, methods, and events on the [window object](https://go.microsoft.com/fwlink/?LinkId=160274) by using regular dot syntax.</span></span> <span data-ttu-id="0fd0e-160">또한 스크립트 메서드 및 전역 변수에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-160">You can also access script methods and global variables.</span></span> <span data-ttu-id="0fd0e-161">다음 예제에서는 스크립트 개체를 검색하고 브라우저를 닫는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-161">The following example shows how to retrieve the script object and close the browser.</span></span>

 [!code-csharp[XbapBrowserInterop#10](~/samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]

### <a name="debugging-xbaps-that-use-hostscript"></a><span data-ttu-id="0fd0e-162">HostScript를 사용하는 XBAP 디버깅</span><span class="sxs-lookup"><span data-stu-id="0fd0e-162">Debugging XBAPs that Use HostScript</span></span>
 <span data-ttu-id="0fd0e-163">XBAP에서 <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> 개체를 사용 하 여 HTML 창과 통신 하는 경우 Visual Studio에서 응용 프로그램을 실행 하 고 디버깅 하기 위해 지정 해야 하는 두 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-163">If your XBAP uses the <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> object to communicate with the HTML window, there are two settings that you must specify to run and debug the application in Visual Studio.</span></span> <span data-ttu-id="0fd0e-164">애플리케이션은 원본 사이트에 대한 액세스 권한이 있어야 하고 XBAP가 포함된 HTML 페이지로 애플리케이션을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-164">The application must have access to its site of origin and you must start the application with the HTML page that contains the XBAP.</span></span> <span data-ttu-id="0fd0e-165">다음 단계는 이러한 두 설정을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-165">The following steps describe how to check these two settings:</span></span>

1. <span data-ttu-id="0fd0e-166">Visual Studio에서 프로젝트 속성을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-166">In Visual Studio, open the project properties.</span></span>

2. <span data-ttu-id="0fd0e-167">**보안** 탭에서 **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-167">On the **Security** tab, click **Advanced**.</span></span>

     <span data-ttu-id="0fd0e-168">고급 보안 설정 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-168">The Advanced Security Settings dialog box appears.</span></span>

3. <span data-ttu-id="0fd0e-169">**원본 사이트에 애플리케이션 액세스 허용** 확인란을 선택했는지 확인한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-169">Make sure that the **Grant the application access to its site of origin** check box is checked and then click **OK**.</span></span>

4. <span data-ttu-id="0fd0e-170">**디버그** 탭에서 **다음 URL로 브라우저 시작** 옵션을 선택하고 XBAP가 포함된 HTML 페이지의 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-170">On the **Debug** tab, select the **Start browser with URL** option and specify the URL for the HTML page that contains the XBAP.</span></span>

5. <span data-ttu-id="0fd0e-171">Internet Explorer에서 **도구** 단추를 클릭하고 **인터넷 옵션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-171">In Internet Explorer, click the **Tools** button and then select **Internet Options**.</span></span>

     <span data-ttu-id="0fd0e-172">인터넷 옵션 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-172">The Internet Options dialog box appears.</span></span>

6. <span data-ttu-id="0fd0e-173">**고급** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-173">Click the **Advanced** tab.</span></span>

7. <span data-ttu-id="0fd0e-174">**보안** 아래 **설정** 목록에서 **[내 컴퓨터]에 있는 파일에서 액티브 콘텐츠가 실행되는 것을 허용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-174">In the **Settings** list under **Security**, check the **Allow active content to run in files on My Computer** check box.</span></span>

8. <span data-ttu-id="0fd0e-175">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-175">Click **OK**.</span></span>

     <span data-ttu-id="0fd0e-176">변경 내용을 적용하려면 Internet Explorer를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-176">The changes will take effect after you restart Internet Explorer.</span></span>

> [!CAUTION]
> <span data-ttu-id="0fd0e-177">Internet Explorer에서 액티브 콘텐츠가 실행되도록 하면 컴퓨터가 위험에 처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-177">Enabling active content in Internet Explorer may put your computer at risk.</span></span> <span data-ttu-id="0fd0e-178">Internet Explorer 보안 설정을 변경 하지 않으려는 경우 서버에서 HTML 페이지를 시작 하 고이 프로세스에 Visual Studio 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-178">If you do not want to change your Internet Explorer security settings, you can launch the HTML page from a server and attach the Visual Studio debugger to the process.</span></span>

<a name="xbap_security_considerations"></a>
## <a name="xbap-security-considerations"></a><span data-ttu-id="0fd0e-179">XBAP 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0fd0e-179">XBAP Security Considerations</span></span>
 <span data-ttu-id="0fd0e-180">일반적으로 XBAP는 인터넷 영역 권한 설정으로 제한된 부분 신뢰 보안 샌드박스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-180">XBAPs typically execute in a partial-trust security sandbox that is restricted to the Internet zone permission set.</span></span> <span data-ttu-id="0fd0e-181">따라서 구현은 인터넷 영역에서 지원 되는 WPF 요소의 하위 집합을 지원 하거나 응용 프로그램의 권한을 높여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-181">Consequently, your implementation must support the subset of WPF elements that are supported in the Internet zone or you must elevate the permissions of your application.</span></span> <span data-ttu-id="0fd0e-182">자세한 내용은 [보안](../security-wpf.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-182">For more information, see [Security](../security-wpf.md).</span></span>

 <span data-ttu-id="0fd0e-183">응용 프로그램에서 <xref:System.Windows.Controls.WebBrowser> 컨트롤을 사용 하는 경우 WPF는 내부적으로 네이티브 WebBrowser ActiveX 컨트롤을 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-183">When you use a <xref:System.Windows.Controls.WebBrowser> control in your application, WPF internally instantiates the native WebBrowser ActiveX control.</span></span> <span data-ttu-id="0fd0e-184">애플리케이션이 Internet Explorer에서 실행되는 부분 신뢰 XBAP인 경우 ActiveX 컨트롤은 Internet Explorer 프로세스의 전용 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-184">When your application is a partial-trust XBAP running in Internet Explorer, the ActiveX control runs in a dedicated thread of the Internet Explorer process.</span></span> <span data-ttu-id="0fd0e-185">따라서 다음 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-185">Therefore, the following limitations apply:</span></span>

- <span data-ttu-id="0fd0e-186"><xref:System.Windows.Controls.WebBrowser> 컨트롤은 보안 제한 사항을 포함 하 여 호스트 브라우저와 유사한 동작을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-186">The <xref:System.Windows.Controls.WebBrowser> control should provide behavior similar to the host browser, including security restrictions.</span></span> <span data-ttu-id="0fd0e-187">이러한 보안 제한 사항 중 일부는 Internet Explorer 보안 설정을 통해 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-187">Some of these security restrictions can be controlled through the Internet Explorer security settings.</span></span> <span data-ttu-id="0fd0e-188">자세한 내용은 [보안](../security-wpf.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-188">For more information, see [Security](../security-wpf.md).</span></span>

- <span data-ttu-id="0fd0e-189">XBAP가 HTML 페이지의 도메인 간에 로드되면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-189">An exception is thrown when an XBAP is loaded cross-domain in an HTML page.</span></span>

- <span data-ttu-id="0fd0e-190">입력은 WPF <xref:System.Windows.Controls.WebBrowser>와 별도의 스레드에 있으므로 키보드 입력을 가로챌 수 없으며 IME 상태가 공유 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-190">Input is on a separate thread from the WPF <xref:System.Windows.Controls.WebBrowser>, so keyboard input cannot be intercepted and the IME state is not shared.</span></span>

- <span data-ttu-id="0fd0e-191">탐색 시간 또는 순서는 다른 스레드에서 실행 중인 ActiveX 컨트롤로 인해 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-191">The timing or order of navigation may be different due to the ActiveX control running on another thread.</span></span> <span data-ttu-id="0fd0e-192">예를 들어 페이지 탐색은 다른 탐색 요청을 시작할 때 항상 취소되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-192">For example, navigating to a page is not always cancelled by starting another navigation request.</span></span>

- <span data-ttu-id="0fd0e-193">WPF 애플리케이션은 별도의 스레드에서 실행되므로 사용자 지정 ActiveX 컨트롤이 통신하는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-193">A custom ActiveX control may have trouble with communication since the WPF application is running in a separate thread.</span></span>

- <span data-ttu-id="0fd0e-194"><xref:System.Windows.Interop.HwndHost> 다른 스레드나 프로세스에서 실행 되는 창을 서브클래싱하 할 수 없기 때문에 <xref:System.Windows.Interop.HwndHost.MessageHook> 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-194"><xref:System.Windows.Interop.HwndHost.MessageHook> does not get raised because <xref:System.Windows.Interop.HwndHost> cannot subclass a window running in another thread or process.</span></span>

### <a name="creating-a-full-trust-xbap"></a><span data-ttu-id="0fd0e-195">완전 신뢰 XBAP 만들기</span><span class="sxs-lookup"><span data-stu-id="0fd0e-195">Creating a Full-Trust XBAP</span></span>
 <span data-ttu-id="0fd0e-196">XBAP에 완전 신뢰가 필요한 경우 이 권한을 사용하도록 프로젝트를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-196">If your XBAP requires full trust, you can change your project to enable this permission.</span></span> <span data-ttu-id="0fd0e-197">다음 단계는 완전 권한을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-197">The following steps describe how to enable full trust:</span></span>

1. <span data-ttu-id="0fd0e-198">Visual Studio에서 프로젝트 속성을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-198">In Visual Studio, open the project properties.</span></span>

2. <span data-ttu-id="0fd0e-199">**보안** 탭에서 **완전 신뢰 애플리케이션** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-199">On the **Security** tab, select the **This is a full trust application** option.</span></span>

 <span data-ttu-id="0fd0e-200">이 설정으로 다음이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-200">This setting makes the following changes:</span></span>

- <span data-ttu-id="0fd0e-201">프로젝트 파일에서 `<TargetZone>` 요소 값이 `Custom`으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-201">In the project file, the `<TargetZone>` element value is changed to `Custom`.</span></span>

- <span data-ttu-id="0fd0e-202">응용 프로그램 매니페스트 (manifest.xml)에서 `Unrestricted="true"` 특성이 '<xref:System.Security.PermissionSet> 요소에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-202">In the application manifest (app.manifest), an `Unrestricted="true"` attribute is added to the \`<xref:System.Security.PermissionSet> element.</span></span>

    ```xml
    <PermissionSet class="System.Security.PermissionSet"
                   version="1"
                   ID="Custom"
                   SameSite="site"
                   Unrestricted="true" />
    ```

### <a name="deploying-a-full-trust-xbap"></a><span data-ttu-id="0fd0e-203">완전 신뢰 XBAP 배포</span><span class="sxs-lookup"><span data-stu-id="0fd0e-203">Deploying a Full-Trust XBAP</span></span>
 <span data-ttu-id="0fd0e-204">ClickOnce 신뢰 배포 모델을 따르지 않는 완전 신뢰 XBAP를 배포하면 사용자가 애플리케이션을 실행할 때의 동작이 보안 영역에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-204">When you deploy a full-trust XBAP that does not follow the ClickOnce Trusted Deployment model, the behavior when the user runs the application will depend on the security zone.</span></span> <span data-ttu-id="0fd0e-205">일부 경우에는 사용자가 설치를 시도할 때 경고를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-205">In some cases, the user will receive a warning when they attempt to install it.</span></span> <span data-ttu-id="0fd0e-206">사용자는 설치를 계속하거나 취소하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-206">The user can choose to continue or cancel the installation.</span></span> <span data-ttu-id="0fd0e-207">다음 표에서 각 보안 영역의 동작 및 애플리케이션이 완전 신뢰를 받기 위해 수행해야 하는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-207">The following table describes the behavior of the application for each security zone and what you have to do for the application to receive full trust.</span></span>

|<span data-ttu-id="0fd0e-208">보안 영역</span><span class="sxs-lookup"><span data-stu-id="0fd0e-208">Security Zone</span></span>|<span data-ttu-id="0fd0e-209">동작</span><span class="sxs-lookup"><span data-stu-id="0fd0e-209">Behavior</span></span>|<span data-ttu-id="0fd0e-210">완전 신뢰 얻기</span><span class="sxs-lookup"><span data-stu-id="0fd0e-210">Getting Full Trust</span></span>|
|-------------------|--------------|------------------------|
|<span data-ttu-id="0fd0e-211">로컬 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="0fd0e-211">Local computer</span></span>|<span data-ttu-id="0fd0e-212">자동 완전 신뢰</span><span class="sxs-lookup"><span data-stu-id="0fd0e-212">Automatic full trust</span></span>|<span data-ttu-id="0fd0e-213">작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-213">No action is needed.</span></span>|
|<span data-ttu-id="0fd0e-214">인트라넷 및 신뢰할 수 있는 사이트</span><span class="sxs-lookup"><span data-stu-id="0fd0e-214">Intranet and trusted sites</span></span>|<span data-ttu-id="0fd0e-215">완전 신뢰 확인</span><span class="sxs-lookup"><span data-stu-id="0fd0e-215">Prompt for full trust</span></span>|<span data-ttu-id="0fd0e-216">사용자가 프롬프트에서 소스를 볼 수 있도록 인증서로 XBAP에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-216">Sign the XBAP with a certificate so that the user sees the source in the prompt.</span></span>|
|<span data-ttu-id="0fd0e-217">인터넷</span><span class="sxs-lookup"><span data-stu-id="0fd0e-217">Internet</span></span>|<span data-ttu-id="0fd0e-218">"신뢰할 수 없음"과 함께 실패</span><span class="sxs-lookup"><span data-stu-id="0fd0e-218">Fails with "Trust Not Granted"</span></span>|<span data-ttu-id="0fd0e-219">인증서로 XBAP를 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-219">Sign the XBAP with a certificate.</span></span>|

> [!NOTE]
> <span data-ttu-id="0fd0e-220">위의 표에 설명된 동작은 ClickOnce 신뢰 배포 모델을 따르지 않는 완전 신뢰 XBAP에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-220">The behavior described in the previous table is for full-trust XBAPs that do not follow the ClickOnce Trusted Deployment model.</span></span>

 <span data-ttu-id="0fd0e-221">완전 신뢰 XBAP를 배포하는 데 ClickOnce 신뢰 배포 모델을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-221">It is recommended that you use the ClickOnce Trusted Deployment model for deploying a full-trust XBAP.</span></span> <span data-ttu-id="0fd0e-222">이 모델을 통해 보안 영역에 관계없이 XBAP에 완전 신뢰를 자동으로 부여할 수 있으므로 사용자에게 확인 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-222">This model allows your XBAP to be granted full trust automatically, regardless of the security zone, so that the user is not prompted.</span></span> <span data-ttu-id="0fd0e-223">이 모델의 일부로, 신뢰할 수 있는 게시자의 인증서로 애플리케이션을 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-223">As part of this model, you must sign your application with a certificate from a trusted publisher.</span></span> <span data-ttu-id="0fd0e-224">자세한 내용은 [신뢰할 수 있는 애플리케이션 배포 개요](/visualstudio/deployment/trusted-application-deployment-overview) 및 [코드 서명 소개](https://go.microsoft.com/fwlink/?LinkId=166327)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-224">For more information, see [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview) and [Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=166327).</span></span>

<a name="xbap_start_time_performance_considerations"></a>
## <a name="xbap-start-time-performance-considerations"></a><span data-ttu-id="0fd0e-225">XBAP 시작 시간 성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0fd0e-225">XBAP Start Time Performance Considerations</span></span>
 <span data-ttu-id="0fd0e-226">XBAP 성능에서 중요한 측면은 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-226">An important aspect of XBAP performance is its start time.</span></span> <span data-ttu-id="0fd0e-227">XBAP가 로드할 첫 번째 WPF 애플리케이션인 경우 *콜드 부팅* 시간은 10초 이상일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-227">If an XBAP is the first WPF application to load, the *cold start* time can be ten seconds or more.</span></span> <span data-ttu-id="0fd0e-228">이는 진행률 페이지가 WPF에 의해 렌더링되고 애플리케이션을 표시하기 위해 CLR 및 WPF가 모두 콜드 부팅되어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-228">This is because the progress page is rendered by WPF, and both the CLR and WPF must be cold-started to display the application.</span></span>

 <span data-ttu-id="0fd0e-229">.NET Framework 3.5 s p 1 부터는 배포 주기의 초기에 관리 되지 않는 진행률 페이지를 표시 하 여 XBAP 콜드 시작 시간이 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-229">Starting in .NET Framework 3.5 SP1, XBAP cold-start time is mitigated by displaying an unmanaged progress page early in the deployment cycle.</span></span> <span data-ttu-id="0fd0e-230">진행률 페이지는 원시 호스팅 코드에 의해 표시되고 HTML로 렌더링되기 때문에 거의 애플리케이션이 시작된 직후에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-230">The progress page appears almost immediately after the application is started, because it is displayed by native hosting code and rendered in HTML.</span></span>

 <span data-ttu-id="0fd0e-231">또한 ClickOnce 다운로드 순서의 동시성이 향상 되어 시작 시간이 최대 10%까지 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-231">In addition, improved concurrency of the ClickOnce download sequence improves start time by up to ten percent.</span></span> <span data-ttu-id="0fd0e-232">ClickOnce에서 매니페스트를 다운로드 하 고 유효성을 검사 한 후에는 응용 프로그램 다운로드가 시작 되 고 진행률 표시줄이 업데이트 되기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0e-232">After ClickOnce downloads and validates manifests, the application download starts, and the progress bar starts to update.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fd0e-233">참조</span><span class="sxs-lookup"><span data-stu-id="0fd0e-233">See also</span></span>

- [<span data-ttu-id="0fd0e-234">Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 애플리케이션 디버깅</span><span class="sxs-lookup"><span data-stu-id="0fd0e-234">Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>](configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)
- [<span data-ttu-id="0fd0e-235">WPF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="0fd0e-235">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
