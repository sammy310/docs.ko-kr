---
title: '방법: Windows Forms에서 개체 계층화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: 8d0abbf0f71ac176d17261a0ae863938c575bdaf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311664"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>방법: Windows Forms에서 개체 계층화
복잡 한 사용자 인터페이스를 만들거나 여러 문서 MDI (인터페이스) 폼을 사용할 때 더 복잡 한 UI (사용자 인터페이스) 자식 폼 및 컨트롤 계층 하려는 경우가 많습니다. 이동 컨트롤 및 windows 그룹의 컨텍스트 내에서 한 추적을 z 순서 조작할 수 있습니다. *Z 순서* 폼의 z 축 (깊이)에 따라 폼에서 컨트롤의 시각적 계층 됩니다. Z-순서의 맨 위에 있는 창에는 다른 모든 windows 겹칩니다. 다른 모든 windows 겹치는 z-순서의 맨 아래에 있는 창입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-layer-controls-at-design-time"></a>디자인 타임에 컨트롤 계층  
  
1. 계층에 있는 컨트롤을 선택 합니다.  
  
2. 에 **형식** 메뉴에서 **순서**를 클릭 하 고 **앞으로 가져오기** 또는 **맨 뒤로 보내기**합니다.  
  
### <a name="to-layer-controls-programmatically"></a>컨트롤을 프로그래밍 방식으로 계층화  
  
-   사용 된 <xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 컨트롤의 z 순서를 조작 하는 메서드.  
  
     예를 들어 경우는 <xref:System.Windows.Forms.TextBox> 제어 `txtFirstName`는 아래 다른 제어 및 하려면 위쪽에 다음 코드를 사용:  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Windows Forms에서 지 원하는 *컨트롤 포함*합니다. 컨트롤 포함은 여러 다양 한 등을 포함 하는 컨트롤 내에서 컨트롤을 배치 <xref:System.Windows.Forms.RadioButton> 내에서 제어를 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 그런 다음 포함 하는 컨트롤 내에서 컨트롤을 넣을 수 있습니다. 그 안에 포함 되므로 컨트롤을 이동 그룹 상자를 이동 합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
