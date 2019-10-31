---
title: '연습: 혼합 애플리케이션 지역화'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: bef296d5de4735780c839af312b5d4fe7eeeb960
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197859"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="24040-102">연습: 혼합 애플리케이션 지역화</span><span class="sxs-lookup"><span data-stu-id="24040-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="24040-103">이 연습에서는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]기반 하이브리드 응용 프로그램에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소를 지역화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="24040-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="24040-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24040-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="24040-105">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 호스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24040-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

- <span data-ttu-id="24040-106">지역화 가능한 콘텐츠 추가.</span><span class="sxs-lookup"><span data-stu-id="24040-106">Adding localizable content.</span></span>

- <span data-ttu-id="24040-107">지역화 사용.</span><span class="sxs-lookup"><span data-stu-id="24040-107">Enabling localization.</span></span>

- <span data-ttu-id="24040-108">리소스 식별자 할당.</span><span class="sxs-lookup"><span data-stu-id="24040-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="24040-109">LocBaml 도구를 사용하여 위성 어셈블리 생성.</span><span class="sxs-lookup"><span data-stu-id="24040-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="24040-110">이 연습에서 설명 하는 작업의 전체 코드 목록은 [하이브리드 응용 프로그램 지역화 샘플](https://go.microsoft.com/fwlink/?LinkID=160015)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24040-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="24040-111">위의 작업을 완료하면 지역화된 하이브리드 애플리케이션이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="24040-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24040-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="24040-112">Prerequisites</span></span>

<span data-ttu-id="24040-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="24040-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="24040-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="24040-115">Windows Forms 호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="24040-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="24040-116">첫 번째 단계는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램 프로젝트를 만들고 지역화할 내용이 포함 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24040-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="24040-117">호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="24040-117">To create the host project</span></span>

1. <span data-ttu-id="24040-118">`LocalizingWpfInWf`이라는 **WPF 앱** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24040-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="24040-119">(**파일** > **새** > **프로젝트** > **Visual C#**  또는 **Visual Basic** > **클래식 데스크톱** > **WPF 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="24040-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="24040-120">`SimpleControl` 이라는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> 요소를 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="24040-121"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용 하 여 폼에 `SimpleControl` 요소를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="24040-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="24040-122">자세한 내용은 [연습: Windows Forms에서 3 차원 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24040-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="24040-123">지역화 가능한 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="24040-123">Adding Localizable Content</span></span>

<span data-ttu-id="24040-124">다음으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이블 컨트롤을 추가 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 콘텐츠를 지역화 가능한 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="24040-125">지역화 가능한 콘텐츠를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="24040-125">To add localizable content</span></span>

1. <span data-ttu-id="24040-126">**솔루션 탐색기**에서 **simplecontrol .xaml** 을 두 번 클릭 하 여 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="24040-127">다음 코드를 사용 하 여 <xref:System.Windows.Controls.Button> 컨트롤의 콘텐츠를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="24040-128">**솔루션 탐색기**에서 **Form1** 을 두 번 클릭 하 여 Windows Forms 디자이너에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="24040-129">**도구 상자** 를 열고 **레이블** 을 두 번 클릭 하 여 레이블 컨트롤을 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="24040-130"><xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hello"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="24040-131">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="24040-132">`SimpleControl` 요소와 레이블 컨트롤 모두 텍스트 **"Hello"** 를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="24040-133">지역화 사용</span><span class="sxs-lookup"><span data-stu-id="24040-133">Enabling Localization</span></span>

<span data-ttu-id="24040-134">Windows Forms 디자이너에서는 위성 어셈블리에서 지역화를 사용하도록 설정하기 위한 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="24040-135">지역화를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="24040-135">To enable localization</span></span>

1. <span data-ttu-id="24040-136">**솔루션 탐색기**에서 **Form1.cs** 를 두 번 클릭 하 여 Windows Forms 디자이너에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="24040-137">**속성** 창에서 폼의 **지역화할** 수 있는 속성 값을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="24040-138">**속성** 창에서 **Language** 속성의 값을 **스페인어 (스페인)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="24040-139">Windows Forms 디자이너에서 레이블 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="24040-140">**속성** 창에서 <xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hola"`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="24040-141">Form1.es-ES.resx라는 새 리소스 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="24040-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="24040-142">**솔루션 탐색기**에서 **Form1.cs** 을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 클릭 하 여 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="24040-143">`InitializeComponent`에 대 한 호출 앞에 `Form1` 생성자에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="24040-144">**솔루션 탐색기**에서 **LocalizingWpfInWf** 을 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 언로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="24040-145">프로젝트 이름에는 **(사용할 수 없음)** 이라는 레이블이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24040-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="24040-146">**LocalizingWpfInWf**를 마우스 오른쪽 단추로 클릭 하 고 **LocalizingWpfInWf 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="24040-147">프로젝트 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="24040-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="24040-148">다음 줄을 프로젝트 파일의 첫 번째 `PropertyGroup`에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="24040-149">프로젝트 파일을 저장하고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="24040-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="24040-150">**솔루션 탐색기**에서 **LocalizingWpfInWf** 을 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 다시 로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="24040-151">리소스 식별자 할당</span><span class="sxs-lookup"><span data-stu-id="24040-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="24040-152">리소스 식별자를 사용하여 리소스 어셈블리에 지역화 가능한 콘텐츠를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24040-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="24040-153">`updateuid` 옵션을 지정 하면 Msbuild.exe 응용 프로그램에서 리소스 식별자를 자동으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="24040-154">리소스 식별자를 할당하려면</span><span class="sxs-lookup"><span data-stu-id="24040-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="24040-155">시작 메뉴에서 Visual Studio에 대 한 개발자 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="24040-156">다음 명령을 사용하여 지역화 가능한 콘텐츠에 리소스 식별자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="24040-157">**솔루션 탐색기**에서 **simplecontrol .xaml** 을 두 번 클릭 하 여 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="24040-158">`msbuild` 명령이 모든 요소에 `Uid` 특성을 추가 하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24040-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="24040-159">따라서 리소스 식별자 할당을 통해 지역화가 용이해집니다.</span><span class="sxs-lookup"><span data-stu-id="24040-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="24040-160">**F6** 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="24040-161">LocBaml을 사용하여 위성 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="24040-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="24040-162">지역화 된 콘텐츠는 리소스 전용 *위성 어셈블리*에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24040-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="24040-163">명령줄 도구인 LocBaml .exe를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에 대 한 지역화 된 어셈블리를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="24040-164">위성 어셈블리를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="24040-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="24040-165">LocBaml.exe를 프로젝트의 obj\Debug 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="24040-166">자세한 내용은 [응용 프로그램 지역화](how-to-localize-an-application.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24040-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="24040-167">[명령 프롬프트] 창에서 다음 명령을 사용하여 리소스 문자열을 임시 파일로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="24040-168">Visual Studio 또는 다른 텍스트 편집기를 사용 하 여 임시 .csv 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24040-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="24040-169">문자열 `"Hello"`를 `"Hola"`스페인어 번역으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="24040-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="24040-170">temp.csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="24040-171">다음 명령을 사용하여 지역화된 리소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="24040-172">LocalizingWpfInWf.g.es-ES.resources 파일이 obj\Debug 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="24040-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="24040-173">다음 명령을 사용하여 지역화된 위성 어셈블리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="24040-174">LocalizingWpfInWf.resources.dll 파일이 obj\Debug 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="24040-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="24040-175">LocalizingWpfInWf.resources.dll 파일을 프로젝트의 bin\Debug\es-ES 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="24040-176">기존 파일을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="24040-176">Replace the existing file.</span></span>

8. <span data-ttu-id="24040-177">프로젝트의 bin\Debug 폴더에 있는 LocalizingWpfInWf.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="24040-178">애플리케이션을 다시 빌드하지 마세요. 다시 빌드하면 위성 어셈블리가 덮어 쓰입니다.</span><span class="sxs-lookup"><span data-stu-id="24040-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="24040-179">애플리케이션에서 영어 문자열 대신 지역화된 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="24040-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="24040-180">참조</span><span class="sxs-lookup"><span data-stu-id="24040-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="24040-181">애플리케이션 지역화</span><span class="sxs-lookup"><span data-stu-id="24040-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="24040-182">[연습: Windows Forms 지역화](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24040-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="24040-183">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="24040-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
