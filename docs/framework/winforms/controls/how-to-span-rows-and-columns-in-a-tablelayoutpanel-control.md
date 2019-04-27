---
title: '방법: TableLayoutPanel 컨트롤에서 행 및 열 확장'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 02db78b07930676235e55e535fb24f6ff618d823
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012973"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>방법: TableLayoutPanel 컨트롤에서 행 및 열 확장
컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 인접 한 행과 열을 확장할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-span-columns-and-rows"></a>열과 행에 걸쳐  
  
1. <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2. 끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 의 왼쪽 위 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.  
  
3. 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 **2**합니다. <xref:System.Windows.Forms.Button> 컨트롤 첫 번째와 두 번째 열으로 확장 합니다.  
  
4. 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 **RowSpan** 속성을 **2**합니다. <xref:System.Windows.Forms.Button> 첫 번째와 두 번째 행을 차지 하는 컨트롤입니다.  
  
5. 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 **1**합니다. <xref:System.Windows.Forms.Button> 컨트롤 첫 번째 열으로 이동 하 고 첫 번째 및 두 번째 행을 차지 합니다.  
  
## <a name="see-also"></a>참고자료

- [TableLayoutPanel 컨트롤](tablelayoutpanel-control-windows-forms.md)
