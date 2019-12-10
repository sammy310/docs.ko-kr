---
title: '방법: Windows Forms ListView 컨트롤에 삽입 표시 나타내기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: 62d105dc3c0b9aabc3699c12259e1624ac31a3a0
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960434"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤에 삽입 표시 나타내기
<xref:System.Windows.Forms.ListView> 컨트롤에 있는 삽입 표시는 끌어온 항목이 삽입되는 지점을 사용자에게 표시합니다. 사용자가 다른 두 항목 사이의 지점으로 항목을 끌면 삽입 표시가 항목의 새 예상 위치를 보여 줍니다.  
  
 다음 이미지에서는 삽입 표시를 보여 줍니다.  
  
 ![ListView 삽입 표시를 보여 주는 스크린샷](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")  
  
 다음 코드 예제에서는 이 기능을 사용하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [ListView 컨트롤](listview-control-windows-forms.md)
- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [연습: Windows Forms에서 끌어서 놓기 작업 수행](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
