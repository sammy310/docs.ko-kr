---
title: '방법: ToolStripContainer에서 양식으로 ToolStrip 이동'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 9106a69ea9f28442da6e3270f7cf5abb9374b62d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913659"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>방법: ToolStripContainer에서 양식으로 ToolStrip 이동
이동 하려면 다음 절차는 <xref:System.Windows.Forms.ToolStrip> 개는 <xref:System.Windows.Forms.ToolStripContainer> 폼으로.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>ToolStrip을 폼에 ToolStripContainer 외부로 이동 하려면  
  
1. <xref:System.Windows.Forms.ToolStrip>를 선택합니다.  
  
2. 잘라내기를 <xref:System.Windows.Forms.ToolStrip> CTRL + X를 누르거나 마우스 오른쪽 단추로 클릭 하 여 <xref:System.Windows.Forms.ToolStrip> 선택한 **잘라내기** 상황에 맞는 메뉴에서.  
  
3. 폼을 선택 합니다.  
  
4. 붙여넣기 합니다 <xref:System.Windows.Forms.ToolStrip> 에서 CTRL + V를 누르거나 선택할 **붙여넣기** 에서 합니다 **편집** 메뉴.  
  
5. 설정를 <xref:System.Windows.Forms.ToolStrip.Dock%2A> 의 속성을 <xref:System.Windows.Forms.ToolStrip> 에 **위쪽**합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
