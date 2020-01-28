---
title: '방법: 파일과 연결 된 아이콘 추출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742546"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>방법: Windows Forms에서 파일과 연결된 아이콘 추출
많은 파일에는 연결 된 파일 형식에 대 한 시각적 표현을 제공 하는 아이콘이 포함 되어 있습니다. 예를 들어 Microsoft Word 문서에는 Word 문서로 식별 하는 아이콘이 포함 되어 있습니다. 목록 컨트롤이 나 테이블 컨트롤에 파일을 표시 하는 경우 각 파일 이름 옆에 있는 파일 형식을 나타내는 아이콘을 표시 하는 것이 좋습니다. <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 메서드를 사용 하 여이 작업을 쉽게 수행할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 파일에 연결 된 아이콘을 추출 하 고 <xref:System.Windows.Forms.ListView> 컨트롤에 파일 이름 및 연결 된 아이콘을 표시 하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제를 컴파일하려면 다음을 수행 합니다.  
  
- 위의 코드를 Windows Form에 붙여넣고 폼의 생성자 또는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드에서 `ExtractAssociatedIconExample` 메서드를 호출 합니다.  
  
     양식이 <xref:System.IO> 네임 스페이스를 가져오는지 확인 해야 합니다.  
  
## <a name="see-also"></a>참조

- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
- [ListView 컨트롤](../controls/listview-control-windows-forms.md)
