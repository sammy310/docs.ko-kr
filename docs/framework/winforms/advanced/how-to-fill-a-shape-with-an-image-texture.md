---
title: '방법: 이미지 질감으로 도형 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 099bc9f5359f19439f308f28a6766d470956daea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177322"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>방법: 이미지 질감으로 도형 채우기
사용 하 여 닫힌된 도형 질감으로 채울 수 있습니다 합니다 <xref:System.Drawing.Image> 클래스 및 <xref:System.Drawing.TextureBrush> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 이미지를 사용 하 여 타원을 채웁니다. 코드 생성을 <xref:System.Drawing.Image> 개체를 다음의 주소를 전달 <xref:System.Drawing.Image> 개체에 대 한 인수로 <xref:System.Drawing.TextureBrush.%23ctor%2A> 생성자입니다. 세 번째 문은 이미지를 확장 하 고 네 번째 문을 조정 된 이미지의 반복된 복사본을 사용 하 여 타원을 채웁니다.  
  
 다음 코드에서는 <xref:System.Drawing.TextureBrush.Transform%2A> 속성을 그리기 전에 이미지에 적용 되는 변환이 포함 되어 있습니다. 원본 이미지에는 640 픽셀 너비와 높이는 480 픽셀을 가정 합니다. 변환 75 × 75 가로 및 세로 크기 조정 값을 설정 하 여 이미지를 축소 합니다.  
  
> [!NOTE]
>  다음 예제에서는 이미지 크기 × 75, 75 이며 타원 크기가 150 × 250. 채울 타원 보다 작은 이미지 이므로 타원 이미지를 사용 하 여 바둑판식으로 배열 됩니다. 이미지를 가로 및 세로로 모양의 경계까지 반복 되도록 하는 수단을 바둑판식으로 배열에 도달 했습니다. 바둑판식 배열에 대 한 자세한 내용은 참조 하세요. [방법: 타일 이미지를 사용 하 여 도형을](how-to-tile-a-shape-with-an-image.md)합니다.  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고자료

- [브러시를 사용하여 도형 채우기](using-a-brush-to-fill-shapes.md)
