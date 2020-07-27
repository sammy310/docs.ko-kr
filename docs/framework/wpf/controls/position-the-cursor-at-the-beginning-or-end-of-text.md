---
title: '방법: TextBox 컨트롤의 텍스트 시작 또는 끝 위치에 커서 놓기'
description: Windows Presentation Foundation TextBox 컨트롤의 텍스트 내용 시작 부분 또는 끝 부분에 커서를 배치 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: afe8b11d032b5d61fa91cbf324f02cd8415d2ea8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167514"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>방법: TextBox 컨트롤의 텍스트 시작 또는 끝 위치에 커서 놓기
이 예제에서는 컨트롤의 텍스트 내용 시작 부분 또는 끝 부분에 커서를 배치 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드는 컨트롤을 설명 <xref:System.Windows.Controls.TextBox> 하 고 이름을 지정 합니다.  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>예제  
 컨트롤 내용의 시작 부분에 커서를 배치 하려면 <xref:System.Windows.Controls.TextBox> 메서드를 호출 하 <xref:System.Windows.Controls.TextBox.Select%2A> 고 선택 시작 위치를 0으로 지정 하 고 선택 길이를 0으로 지정 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>예제  
 컨트롤 내용의 끝에 커서를 배치 하려면 <xref:System.Windows.Controls.TextBox> 메서드를 호출 하 <xref:System.Windows.Controls.TextBox.Select%2A> 고 선택 시작 위치를 텍스트 내용의 길이와 동일 하 게 지정 하 고 선택 길이를 0으로 지정 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>참고 항목

- [TextBox 개요](textbox-overview.md)
- [RichTextBox 개요](richtextbox-overview.md)
