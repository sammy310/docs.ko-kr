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
ms.openlocfilehash: ba2619354403793aea7ca15d43649da9637079a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744736"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>방법: Windows Forms 패널의 배경 설정
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다. <xref:System.Windows.Forms.Control.BackColor%2A> 속성은 레이블 및 라디오 단추와 같은 포함 된 컨트롤의 배경색을 설정 합니다. <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되지 않은 경우 <xref:System.Windows.Forms.Control.BackColor%2A> 선택이 전체 패널에 채워집니다. <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 된 경우 이미지가 포함 된 컨트롤 뒤에 표시 됩니다.  
  
### <a name="to-set-the-background-programmatically"></a>프로그래밍 방식으로 배경을 설정 하려면  
  
1. 패널의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 <xref:System.Drawing.Color?displayProperty=nameWithType>형식의 값으로 설정 합니다.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <xref:System.Drawing.Image?displayProperty=nameWithType> 클래스의 <xref:System.Drawing.Image.FromFile%2A> 메서드를 사용 하 여 패널의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성을 설정 합니다.  
  
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
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel 컨트롤](panel-control-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
