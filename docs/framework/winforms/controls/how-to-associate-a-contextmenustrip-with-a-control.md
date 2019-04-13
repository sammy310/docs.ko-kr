---
title: '방법: 컨트롤에 ContextMenuStrip 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 5fe880a44afdbd79116541809972d1456aefb9c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323247"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>방법: 컨트롤에 ContextMenuStrip 연결
컨트롤 및 바로 가기 메뉴를 만든 후 다음 절차를 따라 사용자가 컨트롤을 마우스 오른쪽 단추로 클릭할 때 지정된 바로 가기 메뉴를 표시합니다. 이러한 절차에서는 <xref:System.Windows.Forms.ContextMenuStrip>을 Windows Form 및 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 연결합니다.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>ContextMenuStrip을 Windows Form과 연결하려면  
  
1. <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>ContextMenuStrip을 ToolStrip 컨트롤과 연결하려면  
  
1. 컨트롤의 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 Windows Form 및 <xref:System.Windows.Forms.ToolStrip>을 만들고 다른 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤을 각각에 연결합니다.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [방법: ContextMenuStrip에 메뉴 항목 추가](how-to-add-menu-items-to-a-contextmenustrip.md)
- [ContextMenuStrip 컨트롤](contextmenustrip-control.md)
