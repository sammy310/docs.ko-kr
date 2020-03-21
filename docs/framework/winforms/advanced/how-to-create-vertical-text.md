---
title: '방법: 세로 텍스트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182554"
---
# <a name="how-to-create-vertical-text"></a>방법: 세로 텍스트 만들기
개체를 <xref:System.Drawing.StringFormat> 사용하여 텍스트를 가로가 아닌 세로로 그릴 수 있도록 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 개체의 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 속성에 <xref:System.Drawing.StringFormat.FormatFlags%2A> 값을 <xref:System.Drawing.StringFormat> 할당합니다. 해당 <xref:System.Drawing.StringFormat> 개체는 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 <xref:System.Drawing.Graphics> 전달됩니다. 값은 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 열거형의 <xref:System.Drawing.StringFormatFlags> 멤버입니다.  
  
 다음 그림에서는 세로 텍스트를 보여 주며 있습니다.
  
 ![세로 글꼴 텍스트를 표시하는 그래픽입니다.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
- 앞의 예제는 Windows Forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> `e` 의 매개 변수인 이 <xref:System.Windows.Forms.PaintEventHandler>요구사항입니다.  
  
## <a name="see-also"></a>참고 항목

- [방법: GDI를 사용하여 텍스트 그리기](how-to-draw-text-with-gdi.md)
