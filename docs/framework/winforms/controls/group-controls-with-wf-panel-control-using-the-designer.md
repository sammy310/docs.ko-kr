---
title: '방법: 디자이너를 사용 하 여 Windows Forms 패널 컨트롤을 사용 하 여 그룹 컨트롤'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: f1aa3b54eb842bb92e4ae2cbb562a11464acac63
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717451"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>방법: 디자이너를 사용 하 여 Windows Forms 패널 컨트롤을 사용 하 여 그룹 컨트롤
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다. 컨트롤을 그룹화 하는 방법은 세 가지가 있습니다. 하나는 시각적으로 관련 된 일반 사용자 인터페이스;에 대 한 폼 요소 그룹화 프로그래밍 방식으로 그룹화 라디오 단추의 예를 들어, 다른 하나는 마지막으로 디자인 타임에 컨트롤을 한 단위로 이동입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-a-group-of-controls"></a>컨트롤의 그룹을 만들려면  
  
1.  끌어서를 <xref:System.Windows.Forms.Panel> 에서 제어 합니다 **Windows Forms** 폼으로 도구 상자 탭입니다.  
  
2.  패널 내부에 각 패널에 다른 컨트롤을 추가 합니다.  
  
     기존 컨트롤에 패널에 포함 하려는 경우에 모든 컨트롤을 선택, 선택 클립보드로 잘라낸 수 있습니다는 <xref:System.Windows.Forms.Panel> 컨트롤 및 패널에 붙여 넣습니다. 패널에 직접를 끌어 올 수도 있습니다.  
  
3.  (선택 사항) 설정 패널에 테두리를 추가 하려는 경우 해당 <xref:System.Windows.Forms.BorderStyle> 속성입니다. 세 가지: <xref:System.Windows.Forms.BorderStyle.Fixed3D>하십시오 <xref:System.Windows.Forms.BorderStyle.FixedSingle>, 및 <xref:System.Windows.Forms.BorderStyle.None>합니다.  
  
## <a name="see-also"></a>참고자료
- [Panel 컨트롤](panel-control-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
- [방법: 패널의 배경 설정](how-to-set-the-background-of-a-windows-forms-panel.md)
