---
title: 폼 테두리 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739572"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>방법: Windows Forms의 테두리 변경
Windows Forms의 모양과 동작을 결정할 때 선택할 수 있는 여러 테두리 스타일이 있습니다. <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 변경하여 폼의 크기 조정 동작을 제어할 수 있습니다. 또한 <xref:System.Windows.Forms.Form.FormBorderStyle%2A>을 설정하면 캡션 표시줄 표시 방식 및 표시되는 단추에 영향을 줍니다. 자세한 내용은 <xref:System.Windows.Forms.FormBorderStyle>을 참조하세요.  
  
 Visual Studio에서는 이 작업이 광범위하게 지원됩니다.  
  
 [방법: 디자이너를 사용 하 여 Windows Forms 테두리 변경](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100))도 참조 하세요.  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Windows Forms의 테두리 스타일을 프로그래밍 방식으로 설정하려면  
  
- <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 원하는 스타일로 설정합니다. 다음 코드 예제에서는 `DlgBx1` 폼의 테두리 스타일을 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>로 설정 합니다.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     또한 [방법: 디자인 타임에 대화 상자 만들기를](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100))참조 하세요.  
  
     또한 선택적 **최소화** 및 **최대화** 단추를 제공 하는 폼에 대 한 테두리 스타일을 선택한 경우 이러한 단추 중 하나 또는 둘 다를 사용할지 여부를 지정할 수 있습니다. 이러한 단추는 사용자 환경을 긴밀히 제어하려는 경우에 유용합니다. **최소화** 및 **최대화** 단추는 기본적으로 사용 하도록 설정 되어 있으며 **속성** 창을 통해 해당 기능을 조작할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [Windows Forms 시작](getting-started-with-windows-forms.md)
