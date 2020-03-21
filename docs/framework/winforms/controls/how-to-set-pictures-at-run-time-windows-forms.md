---
title: '방법: 런타임에 그림 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182111"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="1126e-102">방법: 런타임에 그림 설정(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1126e-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="1126e-103">Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤에 의해 표시되는 이미지를 프로그래밍 방식으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="1126e-104">프로그래밍 방식으로 그림을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1126e-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="1126e-105">클래스의 <xref:System.Windows.Forms.PictureBox.Image%2A> 메서드를 <xref:System.Drawing.Image.FromFile%2A> 사용 <xref:System.Drawing.Image> 하 여 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="1126e-106">아래 예제에서 이미지 위치에 대해 설정된 경로는 내 문서 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="1126e-107">Windows 운영 체제를 실행하는 대부분의 컴퓨터에 이 디렉터리가 포함된다고 가정할 수 있기 때문에 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="1126e-108">또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="1126e-109">아래 예제는 컨트롤이 이미 <xref:System.Windows.Forms.PictureBox> 추가된 폼을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="1126e-110">그래픽을 지우려면</span><span class="sxs-lookup"><span data-stu-id="1126e-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="1126e-111">먼저 이미지에서 사용 중인 메모리를 해제한 다음 그래픽을 지웁습니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="1126e-112">메모리 관리가 문제가 되면 나중에 가비지 수집이 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="1126e-113">이러한 방식으로 메서드를 <xref:System.Drawing.Image.Dispose%2A> 사용해야 하는 이유에 대한 자세한 내용은 [관리되지 않는 리소스 정리를](../../../standard/garbage-collection/unmanaged.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1126e-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="1126e-114">이 코드는 디자인 타임에 그래픽이 컨트롤에 로드된 경우에도 이미지를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1126e-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1126e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1126e-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1126e-116">PictureBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1126e-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="1126e-117">How to: Load a Picture Using the Designer</span><span class="sxs-lookup"><span data-stu-id="1126e-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="1126e-118">방법: 런타임에 그림의 크기 또는 위치 수정</span><span class="sxs-lookup"><span data-stu-id="1126e-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="1126e-119">PictureBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1126e-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
