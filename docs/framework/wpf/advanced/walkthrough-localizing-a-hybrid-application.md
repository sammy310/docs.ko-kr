---
title: '연습: 하이브리드 애플리케이션 지역화'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 01530d4ae9779934948bbaff60fbbd392de6e701
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007130"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="b1772-102">연습: 하이브리드 애플리케이션 지역화</span><span class="sxs-lookup"><span data-stu-id="b1772-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="b1772-103">이 연습에서는 지역화 하는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 의 요소를 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-기반 하이브리드 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="b1772-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="b1772-105">만들기는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 호스트 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

-   <span data-ttu-id="b1772-106">지역화 가능한 콘텐츠 추가.</span><span class="sxs-lookup"><span data-stu-id="b1772-106">Adding localizable content.</span></span>

-   <span data-ttu-id="b1772-107">지역화 사용.</span><span class="sxs-lookup"><span data-stu-id="b1772-107">Enabling localization.</span></span>

-   <span data-ttu-id="b1772-108">리소스 식별자 할당.</span><span class="sxs-lookup"><span data-stu-id="b1772-108">Assigning resource identifiers.</span></span>

-   <span data-ttu-id="b1772-109">LocBaml 도구를 사용하여 위성 어셈블리 생성.</span><span class="sxs-lookup"><span data-stu-id="b1772-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="b1772-110">이 연습에 설명 된 작업의 전체 코드 목록은 참조 하세요 [하이브리드 응용 프로그램 샘플을 지역화](https://go.microsoft.com/fwlink/?LinkID=160015)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="b1772-111">위의 작업을 완료하면 지역화된 하이브리드 애플리케이션이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1772-112">전제 조건</span><span class="sxs-lookup"><span data-stu-id="b1772-112">Prerequisites</span></span>

<span data-ttu-id="b1772-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="b1772-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b1772-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="b1772-115">Windows Forms 호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b1772-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="b1772-116">첫 번째 단계를 만들 때 합니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램 프로젝트를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화는 콘텐츠로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="b1772-117">호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b1772-117">To create the host project</span></span>

1. <span data-ttu-id="b1772-118">만들기는 **WPF 앱** 라는 프로젝트 `LocalizingWpfInWf`합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="b1772-119">(**파일** > **새** > **프로젝트** > **Visual C#** 또는 **Visual Basic**   >  **클래식 바탕 화면** > **WPF 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="b1772-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="b1772-120">추가 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 라는 요소가 `SimpleControl` 프로젝트에.</span><span class="sxs-lookup"><span data-stu-id="b1772-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="b1772-121">사용 된 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을는 `SimpleControl` 요소를 폼에 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="b1772-122">자세한 내용은 [연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="b1772-123">지역화 가능한 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="b1772-123">Adding Localizable Content</span></span>

<span data-ttu-id="b1772-124">다음을 추가 합니다는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이블 컨트롤 및 설정의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 콘텐츠를 지역화할 수 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="b1772-125">지역화 가능한 콘텐츠를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b1772-125">To add localizable content</span></span>

1. <span data-ttu-id="b1772-126">**솔루션 탐색기**를 두 번 클릭 **SimpleControl.xaml** 에서 열려는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="b1772-127">내용을 설정 합니다 <xref:System.Windows.Controls.Button> 다음 코드를 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="b1772-128">**솔루션 탐색기**를 두 번 클릭 **Form1** Windows Forms 디자이너에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="b1772-129">엽니다는 **도구 상자** 두 번 클릭 하 고 **레이블** 양식에 레이블 컨트롤을 추가 하려면.</span><span class="sxs-lookup"><span data-stu-id="b1772-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="b1772-130"><xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hello"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="b1772-131">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="b1772-132">모두를 `SimpleControl` 요소와 레이블 컨트롤에 텍스트 표시 **"Hello"** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="b1772-133">지역화 사용</span><span class="sxs-lookup"><span data-stu-id="b1772-133">Enabling Localization</span></span>

<span data-ttu-id="b1772-134">Windows Forms 디자이너에서는 위성 어셈블리에서 지역화를 사용하도록 설정하기 위한 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="b1772-135">지역화를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="b1772-135">To enable localization</span></span>

1. <span data-ttu-id="b1772-136">**솔루션 탐색기**를 두 번 클릭 **Form1.cs** Windows Forms 디자이너에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b1772-137">에 **속성** 창에서 폼의 값을 설정 **Localizable** 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="b1772-138">에 **속성** 창에서 값을 설정 합니다 **언어** 속성을 **스페인어 (스페인)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="b1772-139">Windows Forms 디자이너에서 레이블 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="b1772-140">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `"Hola"`입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="b1772-141">Form1.es-ES.resx라는 새 리소스 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="b1772-142">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Form1.cs** 누릅니다 **코드 보기** 하 여 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="b1772-143">다음 코드를 복사 합니다 `Form1` 생성자를 호출 하기 전에 `InitializeComponent`입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="b1772-144">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf** 누릅니다 **프로젝트 언로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="b1772-145">프로젝트 이름을 이라고 **(사용 불가)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="b1772-146">마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf**, 클릭 **LocalizingWpfInWf.csproj 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="b1772-147">프로젝트 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="b1772-148">다음 줄을 첫 번째 복사 `PropertyGroup` 프로젝트 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="b1772-149">프로젝트 파일을 저장하고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="b1772-150">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf** 누릅니다 **프로젝트 다시 로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="b1772-151">리소스 식별자 할당</span><span class="sxs-lookup"><span data-stu-id="b1772-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="b1772-152">리소스 식별자를 사용하여 리소스 어셈블리에 지역화 가능한 콘텐츠를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="b1772-153">지정 하면 MsBuild.exe 응용 프로그램에서 리소스 식별자를 자동으로 할당 된 `updateuid` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="b1772-154">리소스 식별자를 할당하려면</span><span class="sxs-lookup"><span data-stu-id="b1772-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="b1772-155">시작 메뉴에서 Visual Studio 용 개발자 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="b1772-156">다음 명령을 사용하여 지역화 가능한 콘텐츠에 리소스 식별자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="b1772-157">**솔루션 탐색기**를 두 번 클릭 **SimpleControl.xaml** 하 여 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="b1772-158">확인할 수 있습니다는 `msbuild` 명령에 추가 된 `Uid` 모든 요소에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="b1772-159">따라서 리소스 식별자 할당을 통해 지역화가 용이해집니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="b1772-160">키를 눌러 **F6** 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="b1772-161">LocBaml을 사용하여 위성 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="b1772-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="b1772-162">지역화 된 콘텐츠는 리소스 전용에 저장 됩니다 *위성 어셈블리*합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="b1772-163">명령줄 도구 LocBaml.exe를 사용 하 여에 대 한 지역화 된 어셈블리를 생성 하기에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="b1772-164">위성 어셈블리를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="b1772-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="b1772-165">LocBaml.exe를 프로젝트의 obj\Debug 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="b1772-166">자세한 내용은 [응용 프로그램 지역화](how-to-localize-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="b1772-167">[명령 프롬프트] 창에서 다음 명령을 사용하여 리소스 문자열을 임시 파일로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="b1772-168">Visual Studio 또는 다른 텍스트 편집기를 사용 하 여 temp.csv 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="b1772-169">문자열 대체 `"Hello"` 스페인어 번역 인를 사용 하 여 `"Hola"`입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="b1772-170">temp.csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="b1772-171">다음 명령을 사용하여 지역화된 리소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-171">Use the following command to generate the localized resource file.</span></span>

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="b1772-172">LocalizingWpfInWf.g.es-ES.resources 파일이 obj\Debug 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="b1772-173">다음 명령을 사용하여 지역화된 위성 어셈블리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-173">Use the following command to build the localized satellite assembly.</span></span>

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="b1772-174">LocalizingWpfInWf.resources.dll 파일이 obj\Debug 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="b1772-175">LocalizingWpfInWf.resources.dll 파일을 프로젝트의 bin\Debug\es-ES 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="b1772-176">기존 파일을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-176">Replace the existing file.</span></span>

8. <span data-ttu-id="b1772-177">프로젝트의 bin\Debug 폴더에 있는 LocalizingWpfInWf.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="b1772-178">애플리케이션을 다시 빌드하지 마세요. 다시 빌드하면 위성 어셈블리가 덮어 쓰입니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="b1772-179">애플리케이션에서 영어 문자열 대신 지역화된 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b1772-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1772-180">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1772-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b1772-181">응용 프로그램 지역화</span><span class="sxs-lookup"><span data-stu-id="b1772-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="b1772-182">[연습: Windows Forms 지역화](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1772-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="b1772-183">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="b1772-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
