---
title: '방법: Windows Forms DataGridView 컨트롤에 개체 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 02c4f94eddfcf782d7d2323787d9b6a9b18db2d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180260"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a>방법: Windows Forms DataGridView 컨트롤에 개체 바인딩
다음 코드 예제에서는 각 개체가 개별 행으로 표시되도록 개체 컬렉션을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 방법을 보여 줍니다. 이 예제에서는 콤보 상자 드롭다운 목록에 열거형 값이 포함되도록 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>에서 열거형 형식을 가진 속성을 표시하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [방법: 개체에 액세스 바인딩된 Windows Forms DataGridView 행](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
