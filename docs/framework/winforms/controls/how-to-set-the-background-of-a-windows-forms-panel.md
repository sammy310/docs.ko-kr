---
title: 패널 배경 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182104"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>방법: Windows Forms 패널의 배경 설정
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다. 속성은 <xref:System.Windows.Forms.Control.BackColor%2A> 레이블 및 라디오 단추와 같은 포함된 컨트롤의 배경색을 설정합니다. 속성이 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 설정되지 않은 <xref:System.Windows.Forms.Control.BackColor%2A> 경우 선택 영역이 전체 패널을 채웁니다. 속성이 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 설정된 경우 포함된 컨트롤 뒤에 이미지가 표시됩니다.  
  
### <a name="to-set-the-background-programmatically"></a>프로그래밍 방식으로 배경을 설정하려면  
  
1. 패널의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 형식 <xref:System.Drawing.Color?displayProperty=nameWithType>값으로 설정합니다.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. 클래스의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 메서드를 <xref:System.Drawing.Image.FromFile%2A> 사용하여 패널의 <xref:System.Drawing.Image?displayProperty=nameWithType> 속성을 설정합니다.  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel 컨트롤](panel-control-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
