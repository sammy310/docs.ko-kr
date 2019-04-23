---
title: '방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 애플리케이션 아이콘 추가'
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
ms.openlocfilehash: 52c18b959361079aac6b95dc5d4584bf464a306a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304521"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="ec2d5-102">방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 애플리케이션 아이콘 추가</span><span class="sxs-lookup"><span data-stu-id="ec2d5-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="ec2d5-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> 구성 요소 작업 표시줄의 상태 알림 영역에 단일 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="ec2d5-104">여러 상태 영역에 여러 개의 아이콘을 표시 하려면 해야 <xref:System.Windows.Forms.NotifyIcon> 폼의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="ec2d5-105">컨트롤에 대해 표시 되는 아이콘을 설정 하려면 사용 된 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="ec2d5-106">코드를 작성할 수도 있습니다는 <xref:System.Windows.Forms.NotifyIcon.DoubleClick> 이벤트 처리기 아이콘을 두 번 클릭할 때 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="ec2d5-107">예를 들어, 표시 아이콘으로 표시 하는 백그라운드 프로세스를 구성 하려면 사용자에 대 한 대화 상자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec2d5-108"><xref:System.Windows.Forms.NotifyIcon> 구성 요소를 사용자에 게 경고 작업 또는 이벤트를 발생 하는 알림 용도로 사용 또는 일종의 상태가 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="ec2d5-109">응용 프로그램을 사용 하 여 표준 상호 작용에 대 한 메뉴, 도구 모음 및 기타 사용자 인터페이스 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="ec2d5-110">아이콘을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ec2d5-110">To set the icon</span></span>  
  
1. <span data-ttu-id="ec2d5-111">값을 할당 합니다 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="ec2d5-112">값 형식 이어야 합니다 `System.Drawing.Icon` .ico 파일에서 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="ec2d5-113">줄임표 단추를 클릭 하거나 코드에서 아이콘 파일을 지정할 수 있습니다 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성에는  **속성** 후에 파일을 선택 하는 **오픈** 나타나는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2. <span data-ttu-id="ec2d5-114"><xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="ec2d5-115">설정 된 <xref:System.Windows.Forms.NotifyIcon.Text%2A> 속성을 적절 한 도구 설명 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="ec2d5-116">다음 코드 예제는 아이콘의 위치 설정 된 경로 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="ec2d5-117">이 폴더는 Windows 운영 체제를 실행 하는 대부분의 컴퓨터에 포함 되도록 알 수 없으므로이 위치가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="ec2d5-118">또한이 위치를 선택 합니다. 최소한의 시스템 액세스 수준 가진 사용자가 안전 하 게 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="ec2d5-119">다음 예제에서는 사용 하 여 폼을 <xref:System.Windows.Forms.NotifyIcon> 이미 추가 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="ec2d5-120">명명 된 아이콘 파일에 있어야 `Icon.ico`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2d5-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec2d5-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec2d5-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="ec2d5-122">방법: Windows Forms NotifyIcon 구성 요소를 사용 하 여 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="ec2d5-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="ec2d5-123">NotifyIcon 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ec2d5-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="ec2d5-124">NotifyIcon 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="ec2d5-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
