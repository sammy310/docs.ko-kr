---
title: '방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423732"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정
<xref:System.Drawing.Image> 클래스에서 상속 되는 <xref:System.Drawing.Bitmap> 클래스 및 <xref:System.Drawing.Imaging.ImageAttributes> 클래스는 픽셀 값을 가져오고 설정 하는 기능을 제공 합니다. <xref:System.Drawing.Imaging.ImageAttributes> 클래스를 사용 하 여 전체 이미지에 대 한 알파 값을 수정 하거나 <xref:System.Drawing.Bitmap> 클래스의 <xref:System.Drawing.Bitmap.SetPixel%2A> 메서드를 호출 하 여 개별 픽셀 값을 수정할 수 있습니다.  
  
## <a name="example"></a>예제  
 <xref:System.Drawing.Imaging.ImageAttributes> 클래스에는 렌더링 중에 이미지를 수정 하는 데 사용할 수 있는 많은 속성이 있습니다. 다음 예제에서는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 사용 하 여 모든 알파 값을 80%로 설정 합니다. 이 작업은 색 매트릭스를 초기화 하 고 행렬의 알파 크기 조정 값을 0.8로 설정 하 여 수행 됩니다. 색 매트릭스의 주소는 <xref:System.Drawing.Imaging.ImageAttributes> 개체의 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 메서드에 전달 되 고 <xref:System.Drawing.Imaging.ImageAttributes> 개체는 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 전달 됩니다.  
  
 렌더링 중에 비트맵의 알파 값은 해당 값의 80%로 변환 됩니다. 이렇게 하면 배경으로 혼합 된 이미지가 생성 됩니다. 다음 그림에 나와 있는 것 처럼 비트맵 이미지는 투명 하 게 보입니다. 검정의 검정 줄을 볼 수 있습니다.  
  
 ![행렬을 사용 하는 알파 혼합의 스크린샷](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")  
  
 이미지가 배경의 흰색 부분 위에 있는 경우 이미지가 흰색으로 혼합 되어 있습니다. 이미지가 검은색 선을 교차할 때 이미지는 검정 색과 혼합 되어 있습니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 위의 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`필요 합니다.  
  
## <a name="see-also"></a>참조

- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [선 및 채우기 알파 혼합](alpha-blending-lines-and-fills.md)
