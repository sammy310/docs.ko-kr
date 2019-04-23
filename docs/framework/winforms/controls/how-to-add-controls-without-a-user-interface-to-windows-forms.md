---
title: '방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330105"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="ff37d-102">방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ff37d-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="ff37d-103">보이지 않는 컨트롤 (또는 구성 요소)에 응용 프로그램 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="ff37d-104">다른 컨트롤과 달리 구성 요소 사용자에 게 사용자 인터페이스를 제공 하지 않으며 따라서 Windows Forms 디자이너 화면에 표시 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="ff37d-105">구성 요소를 폼에 추가 되 면 Windows Forms 디자이너 구성 요소를 모두 표시 되는 폼의 맨 아래에 크기를 조정할 수 있는 트레이 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="ff37d-106">컨트롤에 구성 요소 트레이에 추가 되 면 구성 요소를 선택 하 고 폼에서 다른 컨트롤과 마찬가지로 해당 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff37d-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ff37d-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ff37d-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff37d-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="ff37d-110">Windows 폼에는 구성 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ff37d-110">To add a component to a Windows Form</span></span>  
  
1. <span data-ttu-id="ff37d-111">폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-111">Open the form.</span></span> <span data-ttu-id="ff37d-112">자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-112">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="ff37d-113">에 **도구 상자**, 구성 요소를 클릭 하 고 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="ff37d-114">구성 요소가 구성 요소 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="ff37d-115">또한 런타임 시 구성 요소를 폼에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="ff37d-116">이것이 일반적인 시나리오에서 특히 없으므로 구성 요소 사용자 인터페이스가 있는 컨트롤과 달리 visual는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="ff37d-117">아래 예제에서는 <xref:System.Windows.Forms.Timer> 구성 요소가 런타임 시 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="ff37d-118">(Visual Studio에는 다른 타이머의 수,이 경우에 Windows Forms를 사용 하 여 <xref:System.Windows.Forms.Timer> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="ff37d-119">Visual Studio에서 다른 타이머에 대 한 자세한 내용은 참조 하세요. [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="ff37d-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ff37d-120">구성 요소는 종종 효율적인 작동을 위해 구성 요소에 대해 설정 해야 하는 컨트롤 관련 속성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="ff37d-121">경우는 <xref:System.Windows.Forms.Timer> 설정한 구성 요소 아래에 `Interval` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="ff37d-122">때는 반드시 프로젝트에 설정 하는 속성을 해당 구성 요소에 필요한 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="ff37d-123">Windows 폼에 프로그래밍 방식으로 구성 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ff37d-123">To add a component to a Windows Form programmatically</span></span>  
  
1. <span data-ttu-id="ff37d-124">인스턴스를 만듭니다는 <xref:System.Windows.Forms.Timer> 코드에서 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2. <span data-ttu-id="ff37d-125">설정 된 `Interval` 타이머의 틱 사이의 시간을 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3. <span data-ttu-id="ff37d-126">구성 요소에 대 한 필요한 기타 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="ff37d-127">다음 코드를 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Timer> 사용 하 여 해당 `Interval` 속성 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ff37d-128">악성 UserControl을 참조 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="ff37d-129">이 악의적인 사용자 실수로 프로젝트에 추가 하 여 사용자가 팔 로우 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff37d-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff37d-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff37d-130">See also</span></span>

- [<span data-ttu-id="ff37d-131">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ff37d-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="ff37d-132">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ff37d-132">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="ff37d-133">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ff37d-133">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="ff37d-134">방법: Windows Forms 간에 컨트롤 복사</span><span class="sxs-lookup"><span data-stu-id="ff37d-134">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="ff37d-135">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="ff37d-135">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="ff37d-136">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="ff37d-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="ff37d-137">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ff37d-137">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="ff37d-138">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ff37d-138">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
