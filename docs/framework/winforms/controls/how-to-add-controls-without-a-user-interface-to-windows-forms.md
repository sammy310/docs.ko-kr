---
title: 사용자 인터페이스 없이 컨트롤 추가
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
ms.openlocfilehash: 43f13b4f009fcd6e5d82fa2c00113a77d48877b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744749"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="2c38c-102">방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2c38c-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="2c38c-103">비시각적 컨트롤 (또는 구성 요소)은 응용 프로그램에 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="2c38c-104">다른 컨트롤과 달리 구성 요소는 사용자에 대 한 사용자 인터페이스를 제공 하지 않으므로 Windows Forms 디자이너 화면에 표시 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="2c38c-105">구성 요소가 폼에 추가 되 면 Windows Forms 디자이너 모든 구성 요소가 표시 되는 폼의 아래쪽에 크기 조정 가능한 트레이가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="2c38c-106">구성 요소 트레이에 컨트롤이 추가 되 면 구성 요소를 선택 하 고 폼의 다른 컨트롤과 마찬가지로 해당 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="2c38c-107">Windows Form에 구성 요소 추가</span><span class="sxs-lookup"><span data-stu-id="2c38c-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="2c38c-108">Visual Studio에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="2c38c-109">자세한 내용은 [방법: 디자이너에서 Windows Forms 표시](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c38c-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="2c38c-110">**도구 상자**에서 구성 요소를 클릭 하 여 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="2c38c-111">구성 요소가 구성 요소 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="2c38c-112">또한 런타임에 구성 요소를 폼에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="2c38c-113">이는 특히 사용자 인터페이스가 있는 컨트롤과 달리 구성 요소에 시각적 식이 없기 때문에 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="2c38c-114">아래 예제에서는 런타임에 <xref:System.Windows.Forms.Timer> 구성 요소가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="2c38c-115">Visual Studio에는 다양 한 타이머가 포함 되어 있습니다 .이 경우에는 Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="2c38c-116">Visual Studio의 다양 한 타이머에 대 한 자세한 내용은 [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c38c-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="2c38c-117">구성 요소에는 구성 요소가 효과적으로 작동 하기 위해 설정 해야 하는 컨트롤별 속성이 포함 되어 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="2c38c-118">아래 <xref:System.Windows.Forms.Timer> 구성 요소의 경우 `Interval` 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="2c38c-119">프로젝트에 구성 요소를 추가 하는 경우 해당 구성 요소에 필요한 속성을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="2c38c-120">프로그래밍 방식으로 Windows Form에 구성 요소 추가</span><span class="sxs-lookup"><span data-stu-id="2c38c-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="2c38c-121">코드에서 <xref:System.Windows.Forms.Timer> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="2c38c-122">`Interval` 속성을 설정 하 여 타이머의 틱 간 시간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="2c38c-123">구성 요소에 필요한 다른 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="2c38c-124">다음 코드에서는 `Interval` 속성 집합을 사용 하 여 <xref:System.Windows.Forms.Timer>을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

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
    > <span data-ttu-id="2c38c-125">악의적인 UserControl을 참조 하 여 네트워크를 통해 로컬 컴퓨터에 보안 위험을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="2c38c-126">악의적인 사용자가 손상 된 사용자 지정 컨트롤을 만든 다음 실수로 프로젝트에 추가 하는 경우에만이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c38c-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c38c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c38c-127">See also</span></span>

- [<span data-ttu-id="2c38c-128">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2c38c-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="2c38c-129">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2c38c-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="2c38c-130">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2c38c-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="2c38c-131">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="2c38c-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="2c38c-132">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="2c38c-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="2c38c-133">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2c38c-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="2c38c-134">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2c38c-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
