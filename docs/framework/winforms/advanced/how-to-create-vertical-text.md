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
ms.openlocfilehash: b2c26ab220fc9b796c8f8ababdef144847d52698
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710409"
---
# <a name="how-to-create-vertical-text"></a>방법: 세로 텍스트 만들기
사용할 수는 <xref:System.Drawing.StringFormat> 가로로 아닌 세로 텍스트를 그릴지를 지정 하는 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 값을 할당 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 에 <xref:System.Drawing.StringFormat.FormatFlags%2A> 의 속성을 <xref:System.Drawing.StringFormat> 개체입니다. 있는지 <xref:System.Drawing.StringFormat> 개체를 전달 하는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드의 <xref:System.Drawing.Graphics> 클래스입니다. 값 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 멤버인는 <xref:System.Drawing.StringFormatFlags> 열거형입니다.  
  
 다음 그림에서는 세로 텍스트를 보여 줍니다.  
  
 ![글꼴 텍스트](./media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e` 의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.  
  
## <a name="see-also"></a>참고자료
- [방법: GDI 사용 하 여 텍스트 그리기](how-to-draw-text-with-gdi.md)
