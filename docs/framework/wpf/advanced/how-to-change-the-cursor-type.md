---
title: '방법: 커서 형식 변경'
description: Windows Presentation Foundation의 요소 및 응용 프로그램에 대 한 마우스 포인터 커서를 변경 합니다. 이 예제는 XAML 및 코드 숨김으로 구성 되어 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165970"
---
# <a name="how-to-change-the-cursor-type"></a>방법: 커서 형식 변경
이 예제에서는 <xref:System.Windows.Input.Cursor> 특정 요소 및 응용 프로그램에 대 한 마우스 포인터의를 변경 하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일 및 코드 뒤 파일로 구성 되어 있습니다.  
  
## <a name="example"></a>예제  
 사용자 인터페이스는 <xref:System.Windows.Controls.ComboBox> 원하는을 선택 하 고, 개체 쌍을 선택 하 여 <xref:System.Windows.Input.Cursor> <xref:System.Windows.Controls.RadioButton> 커서 변경이 단일 요소에만 적용 되는지 아니면 전체 응용 프로그램에 적용 되는지, 그리고 <xref:System.Windows.Controls.Border> 새 커서가 적용 된 요소인를 선택 하는로 구성 됩니다.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 다음 코드는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 에서 커서 형식이 변경 될 때 호출 되는 이벤트 처리기를 만듭니다 <xref:System.Windows.Controls.ComboBox> .  Switch 문은 커서 이름을 필터링 하 고 <xref:System.Windows.FrameworkElement.Cursor%2A> <xref:System.Windows.Controls.Border> 이름이 *displayarea*인의 속성을 설정 합니다.  
  
 커서 변경이 "전체 응용 프로그램"으로 설정 된 경우 속성은 <xref:System.Windows.Input.Mouse.OverrideCursor%2A> <xref:System.Windows.FrameworkElement.Cursor%2A> 컨트롤의 속성으로 설정 됩니다 <xref:System.Windows.Controls.Border> .  그러면 전체 응용 프로그램에 대해 커서가 변경 됩니다.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>참고 항목

- [입력 개요](input-overview.md)
