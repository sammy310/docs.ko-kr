---
title: '방법: 에서 맞춤 및 늘이기 컨트롤을 TableLayoutPanel 컨트롤'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: 511ed20e63778b70355d1deb12e4256b4d2e9101
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702921"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>방법: 에서 맞춤 및 늘이기 컨트롤을 TableLayoutPanel 컨트롤
정렬 하는 컨트롤에서 stretch를 <xref:System.Windows.Forms.TableLayoutPanel> 사용 하 여를 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-align-and-stretch-a-control"></a>맞춤 및 늘이기를 제어 하려면  
  
1.  <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2.  끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 의 왼쪽 위 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다. <xref:System.Windows.Forms.Button> 중앙 제어 셀에 배치 됩니다.  
  
3.  값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Left,Right`입니다. <xref:System.Windows.Forms.Button> 컨트롤이 셀의 너비에 맞게 늘어납니다.  
  
4.  값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top,Bottom`입니다. <xref:System.Windows.Forms.Button> 컨트롤이 셀의 높이 맞게 늘어납니다.  
  
5.  값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>입니다. <xref:System.Windows.Forms.Button> 컨트롤이 확장 되어 셀을 채웁니다.  
  
6.  값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.None>입니다. <xref:System.Windows.Forms.Button> 컨트롤 원래 크기를 반환 하 고 셀의 왼쪽 위 모퉁이로 이동 합니다. **Windows Forms 디자이너** 가 설정 된 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Top, Left`입니다.  
  
7.  값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Bottom,Right`입니다. <xref:System.Windows.Forms.Button> 셀의 오른쪽 아래 모퉁이에 컨트롤은 이동 합니다.  
  
8.  값을 설정 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.None>입니다. <xref:System.Windows.Forms.Button> 셀의 가운데에 컨트롤은 이동 합니다.  
  
## <a name="see-also"></a>참고자료
- [TableLayoutPanel 컨트롤](tablelayoutpanel-control-windows-forms.md)
