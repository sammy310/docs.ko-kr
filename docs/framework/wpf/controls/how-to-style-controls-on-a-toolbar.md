---
title: '방법: ToolBar 컨트롤의 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 78b9fc505c3c9045a0ca16ddaa1361c90bcc896a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459412"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>방법: ToolBar 컨트롤의 스타일 지정
<xref:System.Windows.Controls.ToolBar> <xref:System.Windows.ResourceKey> 개체를 정의 하 여 <xref:System.Windows.Controls.ToolBar>내에서 컨트롤의 스타일을 지정 합니다.  <xref:System.Windows.Controls.ToolBar>에서 컨트롤의 스타일을 지정 하려면 스타일의 `x:key` 특성을 <xref:System.Windows.Controls.ToolBar>에 정의 된 <xref:System.Windows.ResourceKey>로 설정 합니다.  
  
 <xref:System.Windows.Controls.ToolBar>는 다음과 같은 <xref:System.Windows.ResourceKey> 개체를 정의 합니다.  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.ToolBar>내에서 컨트롤에 대 한 스타일을 정의 합니다.  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>참조

- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
