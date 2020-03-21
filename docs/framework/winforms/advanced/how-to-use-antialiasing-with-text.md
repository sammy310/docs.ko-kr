---
title: '방법: 텍스트에 앤티 앨리어싱 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182481"
---
# <a name="how-to-use-antialiasing-with-text"></a>방법: 텍스트에 앤티 앨리어싱 사용
*안티앨리어싱은* 그려진 그래픽과 텍스트의 들쭉날쭉한 가장자리를 스무딩하여 모양이나 가독성을 향상시키는 것을 말합니다. 관리되는 GDI+ 클래스를 사용하면 고품질의 안티 앨리어시드 텍스트와 낮은 품질의 텍스트를 렌더링할 수 있습니다. 일반적으로 고품질 렌더링은 낮은 품질의 렌더링보다 처리 시간이 더 오래 걸립니다. 텍스트 품질 수준을 설정하려면 <xref:System.Drawing.Graphics.TextRenderingHint%2A> <xref:System.Drawing.Text.TextRenderingHint> 열거형 <xref:System.Drawing.Graphics> 요소 중 하나에 의한 속성을 설정합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 두 가지 품질 설정으로 텍스트를 그립니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 다음 그림에서는 예제 코드의 출력을 보여 주며 있습니다.  
  
 ![두 가지 품질 설정이 다른 텍스트를 표시하는 스크린샷입니다.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 코드 예제는 Windows Forms에서 사용하도록 설계되었으며 의 매개 <xref:System.Windows.Forms.PaintEventHandler>변수인 이 요구사항입니다. <xref:System.Windows.Forms.PaintEventArgs> `e`  
  
## <a name="see-also"></a>참고 항목

- [글꼴 및 텍스트 사용](using-fonts-and-text.md)
