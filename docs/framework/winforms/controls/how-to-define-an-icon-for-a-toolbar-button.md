---
title: '방법: 도구 모음 단추의 아이콘 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 84c67c7d2584390ba3e48cb83820c65c6bb45d1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182204"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="a66d1-102">방법: 도구 모음 단추의 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="a66d1-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="a66d1-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a66d1-104"><xref:System.Windows.Forms.ToolBar>버튼은 사용자가 쉽게 식별 할 수 있도록 그들 안에 아이콘을 표시 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="a66d1-105">이는 [ImageList 구성 요소에](imagelist-component-windows-forms.md) 이미지를 추가한 다음 <xref:System.Windows.Forms.ImageList> <xref:System.Windows.Forms.ToolBar> 구성 요소를 컨트롤과 연결하여 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="a66d1-106">도구 모음 단추의 아이콘을 프로그래밍 방식으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a66d1-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="a66d1-107">프로시저에서 <xref:System.Windows.Forms.ImageList> 구성 요소와 컨트롤을 <xref:System.Windows.Forms.ToolBar> 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="a66d1-108">동일한 절차에서 구성 요소에 이미지를 <xref:System.Windows.Forms.ImageList> 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="a66d1-109">동일한 절차에서 컨트롤에 <xref:System.Windows.Forms.ImageList> 컨트롤을 <xref:System.Windows.Forms.ToolBar> 할당하고 개별 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 도구 모음 단추의 속성을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="a66d1-110">다음 코드 예제에서 이미지 위치에 대해 설정된 경로는 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a66d1-111">Windows 운영 체제를 실행하는 대부분의 컴퓨터에 이 디렉터리가 포함된다고 가정할 수 있기 때문에 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="a66d1-112">또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a66d1-113">아래 예제는 컨트롤이 이미 <xref:System.Windows.Forms.PictureBox> 추가된 폼을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="a66d1-114">위의 단계에 따라 아래에 표시된 것과 유사한 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a66d1-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a66d1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a66d1-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="a66d1-116">방법: Toolbar 단추의 메뉴 이벤트 트리거</span><span class="sxs-lookup"><span data-stu-id="a66d1-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="a66d1-117">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a66d1-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="a66d1-118">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a66d1-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
