---
title: '방법: 런타임에 (Windows Forms) 크기 또는 그림의 위치 수정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: 695abf51870ef9164e4543a91b3183e801eee55f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649247"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="136b0-102">방법: 런타임에 (Windows Forms) 크기 또는 그림의 위치 수정</span><span class="sxs-lookup"><span data-stu-id="136b0-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="136b0-103">Windows Forms를 사용 하는 경우 <xref:System.Windows.Forms.PictureBox> 컨트롤을 폼에 설정할 수 있습니다는 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 되도록 속성:</span><span class="sxs-lookup"><span data-stu-id="136b0-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="136b0-104">그림의 왼쪽된 위 모퉁이 컨트롤의 왼쪽된 위 모퉁이 사용 하 여 정렬</span><span class="sxs-lookup"><span data-stu-id="136b0-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="136b0-105">컨트롤 내에서 가운데</span><span class="sxs-lookup"><span data-stu-id="136b0-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="136b0-106">표시 되는 그림에 맞게 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="136b0-107">컨트롤에 맞게 표시 사진을 스트레치합니다</span><span class="sxs-lookup"><span data-stu-id="136b0-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="136b0-108">(특히 비트맵 형식으로 하나) 그림 늘이기 이미지 품질에서 손실을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="136b0-109">메타 파일은 런타임 시 이미지를 그리기 위한 그래픽 명령 목록에는 더 비트맵 보다 스트레치에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="136b0-110">런타임 시 SizeMode 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="136b0-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="136b0-111">설정 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 하 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (기본값), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>를 <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, 또는 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>합니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="136b0-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> 이미지가 컨트롤의 왼쪽 위 모퉁이;에 배치 되는 방법 이미지 컨트롤 보다 큰 경우 아래쪽 및 오른쪽 가장자리가 클리핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="136b0-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> 이미지 컨트롤 내에서 가운데 정렬 되어 있음을 의미 합니다. 이미지 컨트롤 보다 큰 경우 그림의 외부 가장자리가 클리핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="136b0-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 컨트롤의 크기는 이미지의 크기 조정 됩니다 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="136b0-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 반대로, 이며 의미는 이미지의 크기는 컨트롤의 크기를 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="136b0-116">아래 예제에서는 내 문서 폴더는 이미지의 위치에 대 한 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="136b0-117">이렇게 하면 수 없으므로 Windows 운영 체제를 실행 하는 대부분의 컴퓨터는이 디렉터리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="136b0-118">또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="136b0-119">아래 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.PictureBox> 이미 추가 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="136b0-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="136b0-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="136b0-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="136b0-121">방법: 디자이너를 사용 하 여 그림 로드</span><span class="sxs-lookup"><span data-stu-id="136b0-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="136b0-122">PictureBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="136b0-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="136b0-123">방법: 런타임에 그림 설정</span><span class="sxs-lookup"><span data-stu-id="136b0-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="136b0-124">PictureBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="136b0-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
