---
title: NotifyIcon 구성 요소를 사용 하 여 작업 표시줄에 응용 프로그램 아이콘 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746254"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="d6e29-102">방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 애플리케이션 아이콘 추가</span><span class="sxs-lookup"><span data-stu-id="d6e29-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>

<span data-ttu-id="d6e29-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 작업 표시줄의 상태 알림 영역에 단일 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="d6e29-104">상태 영역에 여러 개의 아이콘을 표시 하려면 폼에 여러 개의 <xref:System.Windows.Forms.NotifyIcon> 구성 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="d6e29-105">컨트롤에 대해 표시 되는 아이콘을 설정 하려면 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="d6e29-106">사용자가 아이콘을 두 번 클릭할 때 발생 하도록 <xref:System.Windows.Forms.NotifyIcon.DoubleClick> 이벤트 처리기에 코드를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="d6e29-107">예를 들어 사용자가 아이콘이 나타내는 배경 프로세스를 구성 하는 데 사용할 수 있는 대화 상자가 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>

> [!NOTE]
> <span data-ttu-id="d6e29-108"><xref:System.Windows.Forms.NotifyIcon> 구성 요소는 알림 목적 으로만 사용 되며, 사용자에 게 작업 또는 이벤트가 발생 했거나 일부 정렬 상태가 변경 되었음을 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="d6e29-109">응용 프로그램과의 표준 상호 작용을 위해 메뉴, 도구 모음 및 기타 사용자 인터페이스 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>

### <a name="to-set-the-icon"></a><span data-ttu-id="d6e29-110">아이콘을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d6e29-110">To set the icon</span></span>

1. <span data-ttu-id="d6e29-111"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="d6e29-112">값은 `System.Drawing.Icon` 형식 이어야 하며 .ico 파일에서 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="d6e29-113">**속성** 창의 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성 옆에 있는 줄임표 단추 (...)를 코드에서 지정 하거나 줄임표![단추 (...](./media/visual-studio-ellipsis-button.png)속성 창)를 클릭 하 고 표시 되는 **열기** 대화 상자에서 파일을 선택 하 여 코드에서 아이콘 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-113">You can specify the icon file in code or by clicking the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>

2. <span data-ttu-id="d6e29-114"><xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>

3. <span data-ttu-id="d6e29-115"><xref:System.Windows.Forms.NotifyIcon.Text%2A> 속성을 적절 한 도구 설명 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>

     <span data-ttu-id="d6e29-116">다음 코드 예제에서 아이콘의 위치에 설정 된 경로는 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="d6e29-117">이 위치는 Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더가 포함 된다고 가정할 수 있으므로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="d6e29-118">이 위치를 선택 하면 최소한의 시스템 액세스 수준을 가진 사용자도 응용 프로그램을 안전 하 게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="d6e29-119">다음 예제에는 <xref:System.Windows.Forms.NotifyIcon> 컨트롤이 이미 추가 된 양식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="d6e29-120">또한 `Icon.ico`이라는 아이콘 파일이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e29-120">It also requires an icon file named `Icon.ico`.</span></span>

    ```vb
    ' You should replace the bold icon in the sample below
    ' with an icon of your own choosing.
    NotifyIcon1.Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Icon.ico")
    NotifyIcon1.Visible = True
    NotifyIcon1.Text = "Antivirus program"
    ```

    ```csharp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    // Note the escape character used (@) when specifying the path.
    notifyIcon1.Icon =
       new System.Drawing.Icon (System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Icon.ico");
    notifyIcon1.Visible = true;
    notifyIcon1.Text = "Antivirus program";
    ```

    ```cpp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    notifyIcon1->Icon = gcnew
       System::Drawing::Icon(String::Concat
       (System::Environment::GetFolderPath
       (System::Environment::SpecialFolder::Personal),
       "\\Icon.ico"));
    notifyIcon1->Visible = true;
    notifyIcon1->Text = "Antivirus program";
    ```

## <a name="see-also"></a><span data-ttu-id="d6e29-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6e29-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="d6e29-122">방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="d6e29-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="d6e29-123">NotifyIcon 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d6e29-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="d6e29-124">NotifyIcon 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="d6e29-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
