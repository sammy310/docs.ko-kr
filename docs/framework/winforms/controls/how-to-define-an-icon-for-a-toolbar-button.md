---
title: '방법: 도구 모음 단추에 대한 아이콘 정의'
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
ms.openlocfilehash: 2c1c3d8529662c1e1f1a3d28e3853d31f5d940ed
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336510"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="032fb-102">방법: 도구 모음 단추에 대한 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="032fb-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
>  <span data-ttu-id="032fb-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <xref:System.Windows.Forms.ToolBar> <span data-ttu-id="032fb-104">단추는 사용자가 쉽게 식별할 수 있도록 내에 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-104">buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="032fb-105">추가 이미지를 통해 얻을 수는 [ImageList 구성 요소](imagelist-component-windows-forms.md) 구성 요소와 연결 하는 방법의 <xref:System.Windows.Forms.ImageList> 구성 요소는 <xref:System.Windows.Forms.ToolBar> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="032fb-106">도구 모음 단추의 아이콘을 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="032fb-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="032fb-107">프로시저에서 인스턴스화하는 <xref:System.Windows.Forms.ImageList> 구성 요소 및 <xref:System.Windows.Forms.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="032fb-108">동일한 프로시저를 할당 하려면 이미지를 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="032fb-109">동일한 프로시저를 할당 합니다 <xref:System.Windows.Forms.ImageList> 컨트롤을 <xref:System.Windows.Forms.ToolBar> 제어 하 고 할당을 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 개별 도구 모음 단추 속성.</span><span class="sxs-lookup"><span data-stu-id="032fb-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="032fb-110">다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="032fb-111">이렇게 하면 수 없으므로 Windows 운영 체제를 실행 하는 대부분의 컴퓨터는이 디렉터리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="032fb-112">또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="032fb-113">아래 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.PictureBox> 이미 추가 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="032fb-114">위의 단계를 다음 아래 표시 된 것과 유사한 코드가 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="032fb-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="032fb-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="032fb-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="032fb-116">방법: Toolbar 단추에 대한 메뉴 이벤트 트리거</span><span class="sxs-lookup"><span data-stu-id="032fb-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="032fb-117">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="032fb-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="032fb-118">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="032fb-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
