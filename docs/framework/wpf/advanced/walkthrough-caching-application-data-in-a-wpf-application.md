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
ms.openlocfilehash: 922d91466731b331cc409cc362c4ada2c287916a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715884"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="2d5a9-102">연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="2d5a9-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="2d5a9-103">캐싱을 사용하면 빠른 액세스를 위해 데이터를 메모리에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="2d5a9-104">데이터에 다시 액세스할 때 애플리케이션은 원래 소스에서 검색하는 대신 캐시에서 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="2d5a9-105">이 경우 성능과 확장성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-105">This can improve performance and scalability.</span></span> <span data-ttu-id="2d5a9-106">또한 캐싱을 사용하면 데이터 소스를 일시적으로 사용할 수 없는 경우에도 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="2d5a9-107">.NET Framework는 .NET Framework 응용 프로그램에서 캐싱을 사용할 수 있도록 하는 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="2d5a9-108">이러한 클래스는 <xref:System.Runtime.Caching> 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="2d5a9-109"><xref:System.Runtime.Caching> 네임 스페이스는 .NET Framework 4에 새로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="2d5a9-110">이 네임 스페이스는 모든 .NET Framework 응용 프로그램에서 캐싱을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="2d5a9-111">이전 버전의 .NET Framework에서 캐싱은 <xref:System.Web> 네임 스페이스 에서만 사용할 수 있으므로 ASP.NET 클래스에 대 한 종속성이 필요 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="2d5a9-112">이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 일부로 .NET Framework에서 사용할 수 있는 캐싱 기능을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="2d5a9-113">이 연습에서는 텍스트 파일의 내용을 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="2d5a9-114">이 연습에서 수행할 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="2d5a9-115">WPF 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2d5a9-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="2d5a9-116">.NET Framework 4에 대 한 참조 추가</span><span class="sxs-lookup"><span data-stu-id="2d5a9-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="2d5a9-117">캐시를 초기화 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-117">Initializing a cache.</span></span>

- <span data-ttu-id="2d5a9-118">텍스트 파일의 내용을 포함 하는 캐시 엔트리 추가</span><span class="sxs-lookup"><span data-stu-id="2d5a9-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="2d5a9-119">캐시 엔트리에 대 한 제거 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="2d5a9-120">캐시 된 파일의 경로를 모니터링 하 고 모니터링 되는 항목에 대 한 변경 내용을 캐시 인스턴스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d5a9-121">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="2d5a9-121">Prerequisites</span></span>
 <span data-ttu-id="2d5a9-122">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="2d5a9-123">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="2d5a9-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="2d5a9-124">적은 양의 텍스트를 포함 하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="2d5a9-125">텍스트 파일의 내용은 메시지 상자에 표시 됩니다. 이 연습에서 설명 하는 코드는 사용자가 다음 파일을 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="2d5a9-126">그러나이 연습에서는 모든 텍스트 파일을 사용 하 고 코드를 약간만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="2d5a9-127">WPF 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2d5a9-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="2d5a9-128">먼저 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="2d5a9-129">WPF 애플리케이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="2d5a9-129">To create a WPF application</span></span>

1. <span data-ttu-id="2d5a9-130">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="2d5a9-131">**파일** 메뉴에서 **새로 만들기**를 클릭 한 다음 **새 프로젝트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="2d5a9-132">**새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="2d5a9-133">**설치 된 템플릿**에서 사용 하려는 프로그래밍 언어 (**Visual Basic** 또는 **C#시각적 개체**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="2d5a9-134">**새 프로젝트** 대화 상자에서 **WPF 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d5a9-135">**Wpf 응용 프로그램** 템플릿이 표시 되지 않는 경우 wpf를 지 원하는 .NET Framework 버전을 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="2d5a9-136">**새 프로젝트** 대화 상자의 목록에서 .NET Framework 4를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="2d5a9-137">**이름** 텍스트 상자에 프로젝트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="2d5a9-138">예를 들어 **WPFCaching**를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="2d5a9-139">**솔루션용 디렉터리 만들기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="2d5a9-140">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-140">Click **OK**.</span></span>

     <span data-ttu-id="2d5a9-141">WPF 디자이너가 **디자인** 뷰에서 열리고 mainwindow.xaml 파일이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="2d5a9-142">Visual Studio에서 **My Project** 폴더, 응용 프로그램 .xaml 파일 및 mainwindow.xaml 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="2d5a9-143">.NET Framework 대상 지정 및 캐싱 어셈블리에 대 한 참조 추가</span><span class="sxs-lookup"><span data-stu-id="2d5a9-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="2d5a9-144">기본적으로 WPF 응용 프로그램은 .NET Framework 4 클라이언트 프로필을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="2d5a9-145">WPF 응용 프로그램에서 <xref:System.Runtime.Caching> 네임 스페이스를 사용 하려면 응용 프로그램이 .NET Framework 4 (.NET Framework 4 클라이언트 프로필 아님)를 대상으로 해야 하며 네임 스페이스에 대 한 참조를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="2d5a9-146">따라서 다음 단계는 .NET Framework 대상을 변경 하 고 <xref:System.Runtime.Caching> 네임 스페이스에 대 한 참조를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="2d5a9-147">.NET Framework 대상을 변경 하는 절차는 Visual Basic 프로젝트와 Visual C# 프로젝트에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="2d5a9-148">Visual Basic에서 대상 .NET Framework를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="2d5a9-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="2d5a9-149">**솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="2d5a9-150">응용 프로그램에 대 한 속성 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="2d5a9-151">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="2d5a9-152">창 맨 아래에서 **고급 컴파일 옵션 ...** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="2d5a9-153">**고급 컴파일러 설정** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="2d5a9-154">**대상 프레임 워크 (모든 구성)** 목록에서 .NET Framework 4를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="2d5a9-155">.NET Framework 4 클라이언트 프로필을 선택 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="2d5a9-156">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-156">Click **OK**.</span></span>

     <span data-ttu-id="2d5a9-157">**대상 프레임워크 변경** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="2d5a9-158">**대상 프레임 워크 변경** 대화 상자에서 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="2d5a9-159">프로젝트가 닫힌 후 다시 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="2d5a9-160">다음 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="2d5a9-161">**솔루션 탐색기**에서 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="2d5a9-162">**.Net** 탭을 선택 하 고 `System.Runtime.Caching`를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="2d5a9-163">시각적 C# 프로젝트에서 대상 .NET Framework를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="2d5a9-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="2d5a9-164">**솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="2d5a9-165">응용 프로그램에 대 한 속성 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="2d5a9-166">**애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="2d5a9-167">**대상 프레임 워크** 목록에서 .NET Framework 4를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="2d5a9-168">**.NET Framework 4 클라이언트 프로필**을 선택 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="2d5a9-169">다음 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="2d5a9-170">**참조** 폴더를 마우스 오른쪽 단추로 클릭 한 다음 **참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="2d5a9-171">**.Net** 탭을 선택 하 고 `System.Runtime.Caching`를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="2d5a9-172">WPF 창에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="2d5a9-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="2d5a9-173">다음에는 단추 컨트롤을 추가 하 고 단추의 `Click` 이벤트에 대 한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="2d5a9-174">나중에이 단추를 클릭할 때 텍스트 파일의 내용이 캐시 되 고 표시 되는 코드를에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="2d5a9-175">단추 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="2d5a9-175">To add a button control</span></span>

1. <span data-ttu-id="2d5a9-176">**솔루션 탐색기**에서 mainwindow.xaml 파일을 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="2d5a9-177">**도구 상자**의 **공용 WPF 컨트롤**에서 `Button` 컨트롤을 `MainWindow` 창으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="2d5a9-178">**속성** 창에서 `Button` 컨트롤의 `Content` 속성을 설정 하 여 캐시를 **가져옵니다**.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="2d5a9-179">캐시 초기화 및 항목 캐싱</span><span class="sxs-lookup"><span data-stu-id="2d5a9-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="2d5a9-180">다음으로 다음 작업을 수행 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="2d5a9-181">Cache 클래스의 인스턴스를 만듭니다. 즉, 새 <xref:System.Runtime.Caching.MemoryCache> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="2d5a9-182">캐시에서 <xref:System.Runtime.Caching.HostFileChangeMonitor> 개체를 사용 하 여 텍스트 파일의 변경 내용을 모니터링 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="2d5a9-183">텍스트 파일을 읽고 해당 내용을 캐시 항목으로 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="2d5a9-184">캐시 된 텍스트 파일의 내용을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="2d5a9-185">Cache 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2d5a9-185">To create the cache object</span></span>

1. <span data-ttu-id="2d5a9-186">MainWindow.xaml.cs 또는 Mainwindow.xaml 파일에서 이벤트 처리기를 만들기 위해 방금 추가한 단추를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="2d5a9-187">파일의 맨 위에 클래스 선언 앞에 다음 `Imports` (Visual Basic) 또는 `using` (C#) 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="2d5a9-188">이벤트 처리기에서 다음 코드를 추가 하 여 cache 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="2d5a9-189"><xref:System.Runtime.Caching.ObjectCache> 클래스는 메모리 내 개체 캐시를 제공 하는 기본 제공 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="2d5a9-190">`filecontents`라는 캐시 항목의 내용을 읽으려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="2d5a9-191">`filecontents` 라는 캐시 항목이 있는지 확인 하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="2d5a9-192">지정 된 캐시 엔트리가 없으면 텍스트 파일을 읽고 캐시에 캐시 항목으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="2d5a9-193">`if/then` 블록에서 다음 코드를 추가 하 여 10 초 후에 캐시 엔트리가 만료 되도록 지정 하는 새 <xref:System.Runtime.Caching.CacheItemPolicy> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="2d5a9-194">제거 또는 만료 정보를 제공 하지 않는 경우 기본값은 <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>입니다. 즉, 캐시 항목이 절대 시간에 따라 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="2d5a9-195">대신 캐시 항목은 메모리가 부족할 때만 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="2d5a9-196">가장 좋은 방법은 항상 절대 또는 상대 (sliding) 만료를 명시적으로 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="2d5a9-197">`if/then` 블록 내에서 이전 단계에서 추가한 코드 뒤에 다음 코드를 추가 하 여 모니터링 하려는 파일 경로에 대 한 컬렉션을 만들고 텍스트 파일의 경로를 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="2d5a9-198">사용 하려는 텍스트 파일이 `c:\cache\cacheText.txt`되지 않은 경우 텍스트 파일을 사용할 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="2d5a9-199">이전 단계에서 추가한 코드 뒤에 다음 코드를 추가 하 여 캐시 항목에 대 한 변경 모니터 컬렉션에 새 <xref:System.Runtime.Caching.HostFileChangeMonitor> 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="2d5a9-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> 개체는 텍스트 파일의 경로를 모니터링 하 고 변경 내용이 발생 하는 경우 캐시에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="2d5a9-201">이 예에서는 파일의 내용이 변경 되 면 캐시 항목이 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="2d5a9-202">이전 단계에서 추가한 코드 뒤에 다음 코드를 추가 하 여 텍스트 파일의 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="2d5a9-203">캐시 엔트리가 만료 되는 시점을 확인할 수 있도록 날짜 및 시간 타임 스탬프가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="2d5a9-204">이전 단계에서 추가한 코드 뒤에 다음 코드를 추가 하 여 파일 내용을 캐시 개체에 <xref:System.Runtime.Caching.CacheItem> 인스턴스로 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="2d5a9-205">이전에 만든 <xref:System.Runtime.Caching.CacheItemPolicy> 개체를 매개 변수로 전달 하 여 캐시 엔트리를 제거 하는 방법에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="2d5a9-206">`if/then` 블록 후에 다음 코드를 추가 하 여 캐시 된 파일 콘텐츠를 메시지 상자에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="2d5a9-207">**빌드** 메뉴에서 **WPFCaching 빌드** 를 클릭 하 여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="2d5a9-208">WPF 응용 프로그램에서 캐싱 테스트</span><span class="sxs-lookup"><span data-stu-id="2d5a9-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="2d5a9-209">이제 응용 프로그램을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="2d5a9-210">WPF 응용 프로그램에서 캐싱을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="2d5a9-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="2d5a9-211">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="2d5a9-212">`MainWindow` 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="2d5a9-213">**캐시 가져오기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="2d5a9-214">텍스트 파일의 캐시 된 내용이 메시지 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="2d5a9-215">파일의 타임 스탬프를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="2d5a9-216">메시지 상자를 닫고 **캐시 가져오기** 를 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="2d5a9-217">타임 스탬프는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-217">The timestamp is unchanged.</span></span> <span data-ttu-id="2d5a9-218">이는 캐시 된 내용이 표시 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="2d5a9-219">10 초 이상 기다렸다가 **캐시 가져오기** 를 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="2d5a9-220">이번에는 새 타임 스탬프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="2d5a9-221">이는 정책에 의해 캐시 항목이 만료 되 고 새 캐시 된 콘텐츠가 표시 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="2d5a9-222">텍스트 편집기에서 사용자가 만든 텍스트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="2d5a9-223">아직 변경 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="2d5a9-224">메시지 상자를 닫고 **캐시 가져오기** 를 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="2d5a9-225">타임 스탬프를 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="2d5a9-226">텍스트 파일을 변경한 다음 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="2d5a9-227">메시지 상자를 닫고 **캐시 가져오기** 를 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="2d5a9-228">이 메시지 상자에는 텍스트 파일의 업데이트 된 콘텐츠와 새 타임 스탬프가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="2d5a9-229">이는 절대 시간 제한 기간이 만료 되지 않았더라도 파일을 변경 하는 즉시 호스트 파일 변경 모니터가 캐시 항목을 제거 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d5a9-230">파일을 변경 하는 데 더 많은 시간을 허용 하려면 제거 시간을 20 초 이상으로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="2d5a9-231">코드 예제</span><span class="sxs-lookup"><span data-stu-id="2d5a9-231">Code Example</span></span>
 <span data-ttu-id="2d5a9-232">이 연습을 완료 한 후에는 만든 프로젝트에 대 한 코드는 다음 예제와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5a9-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="2d5a9-233">참조</span><span class="sxs-lookup"><span data-stu-id="2d5a9-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="2d5a9-234">.NET Framework 애플리케이션에서 캐시</span><span class="sxs-lookup"><span data-stu-id="2d5a9-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
