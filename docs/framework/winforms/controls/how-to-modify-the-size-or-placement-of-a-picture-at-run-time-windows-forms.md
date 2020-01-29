---
title: '방법: 런타임에 그림의 크기 또는 위치 수정'
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
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736028"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>방법: 런타임에 그림의 크기 또는 위치 수정(Windows Forms)
폼에서 Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용 하는 경우 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 속성을 다음과 같이 설정할 수 있습니다.  
  
- 그림의 왼쪽 위 모퉁이를 컨트롤의 왼쪽 위 모퉁이에 맞춥니다.  
  
- 컨트롤 내의 그림 가운데 맞춤  
  
- 표시 되는 그림에 맞게 컨트롤 크기 조정  
  
- 컨트롤에 맞게 표시 되는 그림 늘이기  
  
 그림을 확장 하는 경우 (특히 비트맵 형식에서) 이미지 품질이 떨어질 수 있습니다. 런타임에 이미지를 그리기 위한 그래픽 명령 목록으로 제공 되는 메타 파일은 비트맵 보다 스트레치에 보다 적합 합니다.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>런타임에 SizeMode 속성을 설정 하려면  
  
1. <xref:System.Windows.Forms.PictureBox.SizeMode%2A>을 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (기본값), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>또는 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>로 설정 합니다. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>은 이미지가 컨트롤의 왼쪽 위 모퉁이에 배치 됨을 의미 합니다. 이미지가 컨트롤 보다 크면 아래쪽 및 오른쪽 가장자리가 잘립니다. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>은 이미지가 컨트롤 내에 가운데 맞춤 되어 있음을 의미 합니다. 이미지가 컨트롤 보다 크면 사진의 외부 가장자리가 잘립니다. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>은 컨트롤 크기가 이미지 크기에 맞게 조정 됨을 의미 합니다. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>은 역방향 이며 이미지의 크기가 컨트롤의 크기로 조정 됨을 의미 합니다.  
  
     아래 예제에서 이미지 위치에 대해 설정 된 경로는 내 문서 폴더입니다. Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 디렉터리가 포함 되어 있다고 가정할 수 있으므로이 작업을 수행 합니다. 또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다. 아래 예제에서는 <xref:System.Windows.Forms.PictureBox> 컨트롤이 이미 추가 된 폼을 가정 합니다.  
  
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
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.PictureBox>
- [방법: 디자이너를 사용하여 그림 로드](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [PictureBox 컨트롤 개요](picturebox-control-overview-windows-forms.md)
- [방법: 런타임에 그림 설정](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 컨트롤](picturebox-control-windows-forms.md)
