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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141968"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>방법: 런타임에 그림의 크기 또는 위치 수정(Windows Forms)
양식에서 Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용하는 경우 양식의 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 속성을 다음과 같은 것으로 설정할 수 있습니다.  
  
- 그림의 왼쪽 위 모서리를 컨트롤의 왼쪽 위 모서리에 정렬합니다.  
  
- 컨트롤 내그림 가운데  
  
- 표시되는 그림에 맞게 컨트롤 크기를 조정합니다.  
  
- 컨트롤에 맞게 표시되는 모든 그림을 늘립니다.  
  
 그림(특히 비트맵 형식의 그림)을 늘이면 이미지 품질이 저하될 수 있습니다. 런타임에 이미지를 그리기 위한 그래픽 지침 목록인 메타파일은 비트맵보다 스트레칭에 더 적합합니다.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>런타임에 SizeMode 속성을 설정하려면  
  
1. <xref:System.Windows.Forms.PictureBox.SizeMode%2A> <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>(기본값) 또는 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>즉, 이미지가 컨트롤의 왼쪽 위 모서리에 배치됩니다. 이미지가 컨트롤보다 크면 아래쪽 가장자리와 오른쪽 가장자리가 잘립니다. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>이미지가 컨트롤 내에서 가운데에 있음을 의미합니다. 이미지가 컨트롤보다 크면 그림의 외부 가장자리가 잘립니다. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>즉, 컨트롤의 크기가 이미지 크기로 조정됩니다. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>즉, 이미지 의 크기가 컨트롤의 크기에 맞게 조정된다는 의미입니다.  
  
     아래 예제에서 이미지 위치에 대해 설정된 경로는 내 문서 폴더입니다. Windows 운영 체제를 실행하는 대부분의 컴퓨터에 이 디렉터리가 포함된다고 가정할 수 있기 때문에 이 작업을 수행합니다. 또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다. 아래 예제는 컨트롤이 이미 <xref:System.Windows.Forms.PictureBox> 추가된 폼을 가정합니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.PictureBox>
- [How to: Load a Picture Using the Designer](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [PictureBox 컨트롤 개요](picturebox-control-overview-windows-forms.md)
- [방법: 런타임에 그림 설정](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 컨트롤](picturebox-control-windows-forms.md)
