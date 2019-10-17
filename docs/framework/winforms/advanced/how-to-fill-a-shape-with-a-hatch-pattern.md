---
title: '방법: 빗살 무늬로 도형 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320067"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>방법: 빗살 무늬로 도형 채우기
빗살 무늬 패턴은 배경에 대해 하나, 배경으로 패턴을 형성 하는 선에 대 한 두 가지 색으로 만들어집니다. 폐쇄형 셰이프를 빗살 무늬 패턴으로 채우려면 <xref:System.Drawing.Drawing2D.HatchBrush> 개체를 사용 합니다. 다음 예제에서는 빗살 무늬 패턴으로 타원을 채우는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 @No__t_0 생성자는 빗살 무늬 스타일, 해치 선 색 및 배경의 색의 세 가지 인수를 사용 합니다. 빗살 무늬 스타일 인수는 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형의 모든 값일 수 있습니다. @No__t_0 열거형에는 요소가 50 개 이상 있습니다. 이러한 요소 중 몇 가지는 다음 목록에 나와 있습니다.  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 다음 그림에서는 채워진 타원을 보여 줍니다.  
  
  ![해치 패턴으로 채워진 타원이 표시 되는 모양에 대 한 스크린샷](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.  
  
## <a name="see-also"></a>참조

- [브러시를 사용하여 도형 채우기](using-a-brush-to-fill-shapes.md)
