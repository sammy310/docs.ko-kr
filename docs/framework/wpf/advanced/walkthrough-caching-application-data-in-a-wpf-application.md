---
title: '연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: d8f37431279cc22b8e9c131f860b5de82f35af2e
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591197"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="80af4-102">연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="80af4-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="80af4-103">캐싱을 사용하면 빠른 액세스를 위해 데이터를 메모리에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="80af4-104">데이터에 다시 액세스할 때 애플리케이션은 원래 소스에서 검색하는 대신 캐시에서 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="80af4-105">이 경우 성능과 확장성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-105">This can improve performance and scalability.</span></span> <span data-ttu-id="80af4-106">또한 캐싱을 사용하면 데이터 소스를 일시적으로 사용할 수 없는 경우에도 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="80af4-107">.NET Framework는.NET Framework 응용 프로그램에서 캐싱을 사용할 수 있도록 하는 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="80af4-108">이러한 클래스에는 <xref:System.Runtime.Caching> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="80af4-109">합니다 <xref:System.Runtime.Caching> 네임 스페이스의 새로운는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="80af4-110">이 네임 스페이스는 캐싱은 모든.NET Framework 응용 프로그램에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="80af4-111">이전 버전의.NET Framework에서는 캐시 된 에서만 사용할 수 있습니다를 <xref:System.Web> 네임 스페이스 및 따라서 ASP.NET 클래스에 대 한 종속성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="80af4-112">이 연습 일부로.NET Framework에서 사용할 수 있는 캐싱 기능을 사용 하는 방법을 보여 줍니다.는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="80af4-113">이 연습에서는 텍스트 파일의 내용을 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="80af4-114">이 연습에서 수행할 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="80af4-115">WPF 응용 프로그램 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="80af4-116">에 대 한 참조를 추가 합니다 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

- <span data-ttu-id="80af4-117">캐시를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-117">Initializing a cache.</span></span>

- <span data-ttu-id="80af4-118">텍스트 파일의 내용을 포함 하는 캐시 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="80af4-119">캐시 엔트리에 대 한 제거 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="80af4-120">캐시 된 파일의 경로 모니터링 하 고 캐시 인스턴스에 대 한 알림 모니터링된 항목을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80af4-121">전제 조건</span><span class="sxs-lookup"><span data-stu-id="80af4-121">Prerequisites</span></span>
 <span data-ttu-id="80af4-122">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="80af4-123">Microsoft Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="80af4-123">Microsoft Visual Studio 2010.</span></span>

- <span data-ttu-id="80af4-124">적은 양의 텍스트를 포함 하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="80af4-125">(텍스트 파일의 내용을 메시지 상자에 표시 됩니다.) 이 연습에 제공 된 코드를 사용 하는 다음 파일을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="80af4-126">그러나 모든 텍스트 파일을 사용할 수 있으며이 연습에서는 코드를 약간 변경.</span><span class="sxs-lookup"><span data-stu-id="80af4-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="80af4-127">WPF 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="80af4-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="80af4-128">WPF 응용 프로그램 프로젝트를 만들어 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="80af4-129">WPF 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="80af4-129">To create a WPF application</span></span>

1. <span data-ttu-id="80af4-130">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="80af4-131">에 **파일** 메뉴에서 클릭 **새로 만들기**를 클릭 하 고 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="80af4-132">**새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="80af4-133">아래 **설치 된 템플릿**를 사용 하려는 프로그래밍 언어 선택 (**Visual Basic** 또는 **Visual C#**).</span><span class="sxs-lookup"><span data-stu-id="80af4-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="80af4-134">에 **새 프로젝트** 대화 상자에서 **WPF 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="80af4-135">표시 되지 않으면 합니다 **WPF 응용 프로그램** 템플릿을 WPF를 지 원하는.NET Framework의 버전을 대상으로 하는 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="80af4-136">에 **새 프로젝트** 대화 상자에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 목록에서.</span><span class="sxs-lookup"><span data-stu-id="80af4-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5. <span data-ttu-id="80af4-137">에 **이름을** 텍스트 상자에 프로젝트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="80af4-138">예를 들어 입력할 수 있습니다 **WPFCaching**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="80af4-139">**솔루션용 디렉터리 만들기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="80af4-140">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-140">Click **OK**.</span></span>

     <span data-ttu-id="80af4-141">WPF 디자이너에서 엽니다 **디자인** 살펴보고 MainWindow.xaml 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="80af4-142">Visual Studio 만듭니다는 **My Project** 폴더, Application.xaml 파일 및 MainWindow.xaml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="80af4-143">.NET Framework 대상 지정 및 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="80af4-144">기본적으로 WPF 응용 프로그램 대상의 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="80af4-145">사용 하는 <xref:System.Runtime.Caching> WPF 응용 프로그램에서 네임 스페이스를 응용 프로그램 대상으로 해야 합니다는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (하지는 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) 네임 스페이스에 대 한 참조를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="80af4-146">따라서 다음 단계에 대 한 참조를 추가한.NET Framework 대상을 변경 하는 것은 <xref:System.Runtime.Caching> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="80af4-147">Visual C# 프로젝트에 Visual Basic 프로젝트에서 대상.NET 프레임 워크를 변경 하는 절차가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="80af4-148">Visual Basic에서.NET Framework 대상을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="80af4-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="80af4-149">**솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="80af4-150">응용 프로그램에 대 한 속성 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="80af4-151">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="80af4-152">창의 맨 아래에서 클릭 **고급 컴파일 옵션...** .</span><span class="sxs-lookup"><span data-stu-id="80af4-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="80af4-153">합니다 **고급 컴파일러 설정** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="80af4-154">에 **대상 프레임 워크 (모든 구성)** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="80af4-155">(선택 하지 않으면 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="80af4-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5. <span data-ttu-id="80af4-156">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-156">Click **OK**.</span></span>

     <span data-ttu-id="80af4-157">**대상 프레임워크 변경** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="80af4-158">에 **대상 프레임 워크 변경** 대화 상자, 클릭 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="80af4-159">프로젝트 닫히고 후 다시 열립니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="80af4-160">다음이 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="80af4-161">**솔루션 탐색기**프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="80af4-162">선택 된 **.NET** 탭을 선택 `System.Runtime.Caching`를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="80af4-163">Visual C# 프로젝트에서.NET Framework 대상을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="80af4-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="80af4-164">**솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="80af4-165">응용 프로그램에 대 한 속성 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="80af4-166">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="80af4-167">에 **대상 프레임 워크** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="80af4-168">(선택 하지 마세요 **.NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="80af4-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="80af4-169">다음이 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="80af4-170">마우스 오른쪽 단추로 클릭 합니다 **참조가** 폴더 및 클릭 한 다음 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="80af4-171">선택 된 **.NET** 탭을 선택 `System.Runtime.Caching`를 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="80af4-172">WPF 창에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="80af4-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="80af4-173">다음으로 단추 컨트롤을 추가 하 고 단추에 대 한 이벤트 처리기를 만듭니다 `Click` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="80af4-174">나중에 텍스트 파일의 내용을 캐시 되어 표시 단추를 클릭 하면 되도록 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="80af4-175">단추 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="80af4-175">To add a button control</span></span>

1. <span data-ttu-id="80af4-176">**솔루션 탐색기**를 열려는 MainWindow.xaml 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="80af4-177">**도구 상자**아래에 있는 **공용 WPF 컨트롤**을 끌어를 `Button` 컨트롤을 `MainWindow` 창.</span><span class="sxs-lookup"><span data-stu-id="80af4-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="80af4-178">**속성** 창에서 `Content` 의 속성을 `Button` 컨트롤을 **캐시 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="80af4-179">캐시를 초기화 하 고 항목 캐싱</span><span class="sxs-lookup"><span data-stu-id="80af4-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="80af4-180">다음으로, 다음 작업을 수행 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="80af4-181">캐시 클래스의 인스턴스를 만들-즉, 인스턴스화 새 <xref:System.Runtime.Caching.MemoryCache> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="80af4-182">캐시 사용을 <xref:System.Runtime.Caching.HostFileChangeMonitor> 텍스트 파일에 변경 사항을 모니터링 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="80af4-183">텍스트 파일을 읽고 캐시 항목으로 해당 콘텐츠를 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="80af4-184">캐시 된 텍스트 파일의 내용을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="80af4-185">캐시 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="80af4-185">To create the cache object</span></span>

1. <span data-ttu-id="80af4-186">MainWindow.Xaml.vb 또는 MainWindow.xaml.cs 파일에 이벤트 처리기를 만들기 위해 방금 추가한 단추를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="80af4-187">클래스 선언) (이전 파일의 맨 위에 있는 다음 코드를 추가 `Imports` (Visual Basic) 또는 `using` 문 (C#):</span><span class="sxs-lookup"><span data-stu-id="80af4-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="80af4-188">이벤트 처리기에서 캐시 개체를 인스턴스화하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="80af4-189"><xref:System.Runtime.Caching.ObjectCache> 클래스는 메모리 내 개체 캐시를 제공 하는 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="80af4-190">명명 된 캐시 항목의 내용을 다음 코드를 추가 `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="80af4-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="80af4-191">라는 캐시 엔트리가 있는지 여부를 확인 하려면 다음 코드를 추가 `filecontents` 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="80af4-192">지정 된 캐시 엔트리 없으면 텍스트 파일을 읽고 캐시에 캐시 항목으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="80af4-193">에 `if/then` 차단 새로 만들려면 다음 코드를 추가 합니다 <xref:System.Runtime.Caching.CacheItemPolicy> 10 초 후에 캐시 엔트리가 만료 되도록 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="80af4-194">기본값은 없습니다 제거 또는 만료 정보를 제공 하는 경우 <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, 절대 시간에만 기반 만료 되지 않도록 캐시 항목을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="80af4-195">대신, 메모리가 부족 한 경우에 캐시 항목 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="80af4-196">모범 사례로 항상 명시적으로 절대 또는 상대 (sliding) 만료를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="80af4-197">내부는 `if/then` 차단 하 고 다음 이전 단계에서 추가한 코드를 모니터링 하 고 컬렉션에 텍스트 파일의 경로 추가 하려면 원하는 파일 경로의 컬렉션을 만드는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="80af4-198">사용 하려는 텍스트 파일 없으면 `c:\cache\cacheText.txt`, 여기서 텍스트 파일에는 사용 하려는 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="80af4-199">새 추가 하려면 다음 코드를 추가 이전 단계에서 추가한 코드 다음 <xref:System.Runtime.Caching.HostFileChangeMonitor> 캐시 엔트리에 대 한 변경의 컬렉션 개체를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="80af4-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> 개체는 텍스트 파일의 경로 모니터링 하 고 변경 될 경우에 캐시를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="80af4-201">이 예제에서는 파일의 내용을 변경 하는 경우 캐시 엔트리가 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="80af4-202">이전 단계에서 추가한 코드를 다음 텍스트 파일의 내용을 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="80af4-203">날짜 및 시간 타임 스탬프는 캐시 항목이 만료 시기를 확인할 수 있도록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="80af4-204">파일의 콘텐츠를 캐시 개체를 삽입할 다음 코드를 추가 다음 이전 단계에서 추가한 코드는 <xref:System.Runtime.Caching.CacheItem> 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="80af4-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="80af4-205">캐시 항목을 전달 하 여 제거 해야 하는 방법에 대 한 정보를 지정 합니다 <xref:System.Runtime.Caching.CacheItemPolicy> 개체를 매개 변수로 만든입니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="80af4-206">이후에 `if/then` 차단 메시지 상자에 캐시 된 파일의 내용을 표시 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="80af4-207">에 **빌드** 메뉴에서 클릭 **빌드 WPFCaching** 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="80af4-208">WPF 응용 프로그램에서 캐싱 테스트</span><span class="sxs-lookup"><span data-stu-id="80af4-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="80af4-209">이제 응용 프로그램을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="80af4-210">WPF 응용 프로그램에서 캐싱 테스트</span><span class="sxs-lookup"><span data-stu-id="80af4-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="80af4-211">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="80af4-212">`MainWindow` 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="80af4-213">클릭 **캐시 가져올**합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="80af4-214">텍스트 파일에서 캐시 된 콘텐츠를 메시지 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="80af4-215">파일의 타임 스탬프를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="80af4-216">메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="80af4-217">타임 스탬프가 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-217">The timestamp is unchanged.</span></span> <span data-ttu-id="80af4-218">이 캐시 된 콘텐츠가 표시 된 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="80af4-219">10 초 이상 기다렸다가 클릭 **캐시 가져오기** 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="80af4-220">이 이번 새 타임 스탬프로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="80af4-221">이 캐시 항목 만료 하도록 정책을 설정 하 고 새 캐시 된 콘텐츠 표시 되도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="80af4-222">텍스트 편집기에서 만든 텍스트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="80af4-223">변경 내용을 아직 수행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="80af4-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="80af4-224">메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="80af4-225">타임 스탬프를 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="80af4-226">텍스트 파일을 변경 하 고 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="80af4-227">메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="80af4-228">이 메시지 상자 텍스트 파일 및 새 타임 스탬프에서 업데이트 된 콘텐츠를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="80af4-229">이 호스트 파일 변경 모니터의 캐시 엔트리를 제거는 파일을 변경 하는 경우에 즉시 절대 제한 시간 만료 되지 않은 경우에 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="80af4-230">제거 시간 20 초 이상으로 변경 하는 파일의 수에 대 한 더 많은 시간을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="80af4-231">코드 예제</span><span class="sxs-lookup"><span data-stu-id="80af4-231">Code Example</span></span>
 <span data-ttu-id="80af4-232">이 연습을 완료 한 후 방금 만든 프로젝트에 대 한 코드를 다음 예와 비슷하게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80af4-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="80af4-233">참고자료</span><span class="sxs-lookup"><span data-stu-id="80af4-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="80af4-234">.NET Framework 애플리케이션에서 캐시</span><span class="sxs-lookup"><span data-stu-id="80af4-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
