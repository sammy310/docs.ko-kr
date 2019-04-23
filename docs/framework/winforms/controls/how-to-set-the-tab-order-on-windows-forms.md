---
title: '방법: Windows Forms에서 탭 순서 설정'
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
ms.openlocfilehash: 50f5f91a946aeebc4d82630b25d18d8f8d2ea4be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339907"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>방법: Windows Forms에서 탭 순서 설정
탭 순서는 사용자가 이동 포커스 한 컨트롤에서 다른 탭 키를 눌러 순서가 있습니다. 각 폼 자체 탭 순서를 있습니다. 기본적으로 탭 순서가 컨트롤을 만든 순서와 동일 합니다. 탭 순서 번호는 0부터 시작 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-set-the-tab-order-of-a-control"></a>컨트롤의 탭 순서 설정  
  
1. 에 **뷰** 메뉴에서 클릭 **탭 순서**합니다.  
  
     이렇게 하면 양식의 탭 순서 선택 모드를 활성화 합니다. 숫자 (나타내는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성) 각 컨트롤의 왼쪽 위 모퉁이에 나타납니다.  
  
2. 탭 순서를 설정 하는 순차적으로 컨트롤을 클릭 합니다.  
  
    > [!NOTE]
    >  탭 순서 내에서 컨트롤의 위치는 0 보다 크거나 값으로 설정할 수 있습니다. 값이 중복 될 경우 두 컨트롤의 z 순서 평가 되 고 탭 맨 위에 있는 컨트롤이 처음으로 구성 됩니다. (Z 순서는 폼의 z 축 [수준]을 따라 양식의 컨트롤의 시각적 계층을가 하는 데 사용 합니다. Z 순서 결정 다른 컨트롤 앞에 있는 컨트롤입니다.) Z 순서에 대 한 자세한 내용은 참조 하세요. [Windows Forms에서 개체 계층화](how-to-layer-objects-on-windows-forms.md)합니다.  
  
3. 완료 되 면, 클릭 **탭 순서** 에 **보기** 메뉴 다시 탭 순서 모드를 종료 합니다.  
  
    > [!NOTE]
    >  비활성화 되 고 보이지 않는 컨트롤 뿐만 아니라 컨트롤 포커스를 받을 수 없습니다는 없는 <xref:System.Windows.Forms.Control.TabIndex%2A> 되며 속성 탭 순서에서 제외 합니다. 사용자가 TAB 키를 누르면 대로 이러한 컨트롤은 건너뜁니다.  
  
 또는 사용 하 여 속성 창에서 탭 순서를 설정할 수 있습니다는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성입니다. <xref:System.Windows.Forms.Control.TabIndex%2A> 컨트롤의 속성 탭 순서에서 위치를 결정 합니다. 기본적으로 그린 첫 번째 컨트롤에는 <xref:System.Windows.Forms.Control.TabIndex%2A> 값 0으로 두 번째에는 <xref:System.Windows.Forms.Control.TabIndex%2A> 1, 및 등.  
  
 또한 기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤에 고유한 <xref:System.Windows.Forms.Control.TabIndex%2A> 정수는 값입니다. <xref:System.Windows.Forms.GroupBox> 런타임 시 컨트롤 자체 포커스를 가질 수 없습니다. 따라서 내에 있는 각 컨트롤을 <xref:System.Windows.Forms.GroupBox> 는 고유한 10 진수 <xref:System.Windows.Forms.Control.TabIndex%2A> .0 부터는 값입니다. 기본적으로 <xref:System.Windows.Forms.Control.TabIndex%2A> 의 한 <xref:System.Windows.Forms.GroupBox> 컨트롤 증가, 내에 있는 컨트롤을 적절 하 게 증가 됩니다. 변경한 경우는 <xref:System.Windows.Forms.Control.TabIndex%2A> 값을 5에서 6으로는 <xref:System.Windows.Forms.Control.TabIndex%2A> 해당 그룹의 첫 번째 컨트롤의 값이 6.0 및 등을 자동으로 변경 합니다.  
  
 마지막으로,을 다로 폼의 컨트롤 탭 순서에서 건너뛸 수 있습니다. 일반적으로 TAB을 눌러 연속적으로 실행된 시간 선택에서 탭 순서에서 각 컨트롤입니다. 전원을 켜는 방식으로 <xref:System.Windows.Forms.Control.TabStop%2A> 속성인 가능 컨트롤이 양식의 탭 순서에서 가리킬 수 있습니다.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>탭 순서에서 컨트롤을 제거 하려면  
  
1. 컨트롤의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성을 `false` 속성 창에서.  
  
     컨트롤 <xref:System.Windows.Forms.Control.TabStop%2A> 속성 설정한 `false` 컨트롤 건너뛴 TAB 키를 사용 하 여 컨트롤을 순환 하는 경우에 여전히 탭 순서에서 해당 위치를 유지 합니다.  
  
    > [!NOTE]
    >  라디오 단추 그룹에는 런타임 시 중지 하는 단일 탭을 있습니다. 선택한 단추 (사용 하 여 단추, 해당 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이로 설정 `true`)에 해당 <xref:System.Windows.Forms.Control.TabStop%2A> 속성 자동 설정 됩니다 `true`반면 다른 단추 해당 <xref:System.Windows.Forms.Control.TabStop%2A> 속성이로 설정 `false`합니다. 그룹화에 대 한 자세한 내용은 <xref:System.Windows.Forms.RadioButton> 컨트롤을 참조 하세요 [집합으로 함수에 Windows Forms RadioButton 컨트롤 그룹화](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
