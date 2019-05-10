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
ms.openlocfilehash: 49bf927085d29b60c1d9cf5d61df3894495349db
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210421"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="c2bbc-102">방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="c2bbc-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="c2bbc-103">보이지 않는 컨트롤 (또는 구성 요소)에 응용 프로그램 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="c2bbc-104">다른 컨트롤과 달리 구성 요소 사용자에 게 사용자 인터페이스를 제공 하지 않으며 따라서 Windows Forms 디자이너 화면에 표시 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="c2bbc-105">구성 요소를 폼에 추가 되 면 Windows Forms 디자이너 구성 요소를 모두 표시 되는 폼의 맨 아래에 크기를 조정할 수 있는 트레이 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="c2bbc-106">컨트롤에 구성 요소 트레이에 추가 되 면 구성 요소를 선택 하 고 폼에서 다른 컨트롤과 마찬가지로 해당 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="c2bbc-107">Windows Form에 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="c2bbc-108">Visual Studio에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="c2bbc-109">자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="c2bbc-110">에 **도구 상자**, 구성 요소를 클릭 하 고 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="c2bbc-111">구성 요소가 구성 요소 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="c2bbc-112">또한 런타임 시 구성 요소를 폼에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="c2bbc-113">이것이 일반적인 시나리오에서 특히 없으므로 구성 요소 사용자 인터페이스가 있는 컨트롤과 달리 visual는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="c2bbc-114">아래 예제에서는 <xref:System.Windows.Forms.Timer> 구성 요소가 런타임 시 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="c2bbc-115">(Visual Studio에는 다른 타이머의 수,이 경우에 Windows Forms를 사용 하 여 <xref:System.Windows.Forms.Timer> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="c2bbc-116">Visual Studio에서 다른 타이머에 대 한 자세한 내용은 참조 하세요. [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="c2bbc-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="c2bbc-117">구성 요소는 종종 효율적인 작동을 위해 구성 요소에 대해 설정 해야 하는 컨트롤 관련 속성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="c2bbc-118">경우는 <xref:System.Windows.Forms.Timer> 설정한 구성 요소 아래에 `Interval` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="c2bbc-119">때는 반드시 프로젝트에 설정 하는 속성을 해당 구성 요소에 필요한 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="c2bbc-120">Windows 폼에는 구성 요소를 프로그래밍 방식으로 추가</span><span class="sxs-lookup"><span data-stu-id="c2bbc-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="c2bbc-121">인스턴스를 만듭니다는 <xref:System.Windows.Forms.Timer> 코드에서 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="c2bbc-122">설정 된 `Interval` 타이머의 틱 사이의 시간을 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="c2bbc-123">구성 요소에 대 한 필요한 기타 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="c2bbc-124">다음 코드를 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Timer> 사용 하 여 해당 `Interval` 속성 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

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
    > <span data-ttu-id="c2bbc-125">악성 UserControl을 참조 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="c2bbc-126">이 악의적인 사용자 실수로 프로젝트에 추가 하 여 사용자가 팔 로우 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2bbc-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2bbc-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2bbc-127">See also</span></span>

- [<span data-ttu-id="c2bbc-128">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c2bbc-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="c2bbc-129">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="c2bbc-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="c2bbc-130">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="c2bbc-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="c2bbc-131">방법: Windows Forms 간에 컨트롤 복사</span><span class="sxs-lookup"><span data-stu-id="c2bbc-131">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="c2bbc-132">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="c2bbc-132">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="c2bbc-133">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="c2bbc-133">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="c2bbc-134">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c2bbc-134">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="c2bbc-135">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c2bbc-135">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
