---
title: '방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330105"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가
보이지 않는 컨트롤 (또는 구성 요소)에 응용 프로그램 기능을 제공합니다. 다른 컨트롤과 달리 구성 요소 사용자에 게 사용자 인터페이스를 제공 하지 않으며 따라서 Windows Forms 디자이너 화면에 표시 될 필요가 없습니다. 구성 요소를 폼에 추가 되 면 Windows Forms 디자이너 구성 요소를 모두 표시 되는 폼의 맨 아래에 크기를 조정할 수 있는 트레이 표시 합니다. 컨트롤에 구성 요소 트레이에 추가 되 면 구성 요소를 선택 하 고 폼에서 다른 컨트롤과 마찬가지로 해당 속성을 설정할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Windows 폼에는 구성 요소를 추가 하려면  
  
1. 폼을 엽니다. 자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.  
  
2. 에 **도구 상자**, 구성 요소를 클릭 하 고 폼으로 끕니다.  
  
     구성 요소가 구성 요소 트레이에 나타납니다.  
  
 또한 런타임 시 구성 요소를 폼에 추가할 수 있습니다. 이것이 일반적인 시나리오에서 특히 없으므로 구성 요소 사용자 인터페이스가 있는 컨트롤과 달리 visual는 식입니다. 아래 예제에서는 <xref:System.Windows.Forms.Timer> 구성 요소가 런타임 시 추가 됩니다. (Visual Studio에는 다른 타이머의 수,이 경우에 Windows Forms를 사용 하 여 <xref:System.Windows.Forms.Timer> 구성 요소입니다. Visual Studio에서 다른 타이머에 대 한 자세한 내용은 참조 하세요. [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)  
  
> [!CAUTION]
>  구성 요소는 종종 효율적인 작동을 위해 구성 요소에 대해 설정 해야 하는 컨트롤 관련 속성을 가집니다. 경우는 <xref:System.Windows.Forms.Timer> 설정한 구성 요소 아래에 `Interval` 속성입니다. 때는 반드시 프로젝트에 설정 하는 속성을 해당 구성 요소에 필요한 구성 요소를 추가 합니다.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>Windows 폼에 프로그래밍 방식으로 구성 요소를 추가 하려면  
  
1. 인스턴스를 만듭니다는 <xref:System.Windows.Forms.Timer> 코드에서 클래스입니다.  
  
2. 설정 된 `Interval` 타이머의 틱 사이의 시간을 결정 하는 속성입니다.  
  
3. 구성 요소에 대 한 필요한 기타 속성을 구성 합니다.  
  
     다음 코드를 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Timer> 사용 하 여 해당 `Interval` 속성 집합입니다.  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  악성 UserControl을 참조 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다. 이 악의적인 사용자 실수로 프로젝트에 추가 하 여 사용자가 팔 로우 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 이어야 합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
- [방법: Windows Forms에 ActiveX 컨트롤 추가](how-to-add-activex-controls-to-windows-forms.md)
- [방법: Windows Forms 간에 컨트롤 복사](how-to-copy-controls-between-windows-forms.md)
- [Windows Forms에 컨트롤 넣기](putting-controls-on-windows-forms.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
