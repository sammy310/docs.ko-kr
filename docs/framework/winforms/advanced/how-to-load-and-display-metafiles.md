---
title: '방법: 메타파일 로드 및 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424814"
---
# <a name="how-to-load-and-display-metafiles"></a>방법: 메타파일 로드 및 표시
<xref:System.Drawing.Image> 클래스에서 상속 되는 <xref:System.Drawing.Imaging.Metafile> 클래스는 벡터 이미지를 기록, 표시 및 검사 하는 메서드를 제공 합니다.  
  
## <a name="example"></a>예제  
 화면에 벡터 이미지 (메타 파일)를 표시 하려면 <xref:System.Drawing.Imaging.Metafile> 개체와 <xref:System.Drawing.Graphics> 개체가 필요 합니다. 파일 (또는 스트림)의 이름을 <xref:System.Drawing.Imaging.Metafile> 생성자에 전달 합니다. <xref:System.Drawing.Imaging.Metafile> 개체를 만든 후에는 해당 <xref:System.Drawing.Imaging.Metafile> 개체를 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 전달 합니다.  
  
 이 예제에서는 EMF (확장 메타 파일) 파일에서 <xref:System.Drawing.Imaging.Metafile> 개체를 만든 다음 (60, 10)의 왼쪽 위 모퉁이가 포함 된 이미지를 그립니다.  
  
 다음 그림에서는 지정 된 위치에 그려진 메타 파일을 보여 줍니다.  
  
 ![이미지 위치를 보여 주는 스크린샷](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 위의 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`필요 합니다.  
  
## <a name="see-also"></a>참조

- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)
