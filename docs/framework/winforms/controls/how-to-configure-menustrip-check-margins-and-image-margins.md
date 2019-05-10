---
title: '방법: MenuStrip 선택 여백 및 이미지 여백 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 5db4b3546b6c15af916d53b1a53c347174f1f30b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643123"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a>방법: MenuStrip 선택 여백 및 이미지 여백 구성
<xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> 및 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> 속성을 다양한 조합으로 설정하여 <xref:System.Windows.Forms.MenuStrip>을 사용자 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ContextMenuStrip> 검사 여백 및 이미지 여백을 설정하고 사용자 지정하는 방법을 보여 줍니다. 절차는 <xref:System.Windows.Forms.ContextMenuStrip> 또는 <xref:System.Windows.Forms.MenuStrip>에서 동일합니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [ToolStrip 컨트롤](toolstrip-control-windows-forms.md)
- [방법: 선택 여백 및 ContextMenuStrip 컨트롤에서 이미지 여백 사용](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
