---
title: 전역 및 지역 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: e4ed103e781cc2e59d62c11f3233357c77b81cb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213755"
---
# <a name="global-and-local-transformations"></a>전역 및 지역 변환
전역 변환은 그린 모든 항목에 적용 되는 변환 된 지정 <xref:System.Drawing.Graphics> 개체입니다. 반면 로컬 변환 하는 그릴 특정 항목에 적용 되는 변환입니다.  
  
## <a name="global-transformations"></a>전역 변형  
 전역 변환을 만들려면 생성 된 <xref:System.Drawing.Graphics> 개체를 조작 합니다 해당 <xref:System.Drawing.Graphics.Transform%2A> 속성. 합니다 <xref:System.Drawing.Graphics.Transform%2A> 속성은을 <xref:System.Drawing.Drawing2D.Matrix> 개체 이므로 관계 변형 시퀀스를 포함할 수 있습니다. 변환에 저장 합니다 <xref:System.Drawing.Graphics.Transform%2A> 속성 월드 라고 합니다. 합니다 <xref:System.Drawing.Graphics> 클래스는 복합 월드 변형을 작성 하는 여러 가지 방법을 제공: <xref:System.Drawing.Graphics.MultiplyTransform%2A>를 <xref:System.Drawing.Graphics.RotateTransform%2A>를 <xref:System.Drawing.Graphics.ScaleTransform%2A>, 및 <xref:System.Drawing.Graphics.TranslateTransform%2A>합니다. 다음 예제에서는 타원을 그립니다: 월드 변형을 후 한 번을 만들기 전에 한 번입니다. 변환을 y 방향의 0.5의 비율로 크기를 조정 50 개 단위 x 방향의 변환 고 30도 회전 합니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 다음 그림은 변환과 관련 된 매트릭스를 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  앞의 예제에서 클라이언트 영역의 왼쪽 위 모퉁이에 있는 좌표계의 원점을 타원이 회전 합니다. 이 자체 center에 대 한 줄임표를 회전 하는 보다 다른 결과 생성 합니다.  
  
## <a name="local-transformations"></a>로컬 변환  
 로컬 변환 그릴 특정 항목에 적용 됩니다. 예를 들어를 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체에는 <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> 해당 경로의 데이터 요소를 변환할 수 있는 방법입니다. 다음 예제에서는 변환이 사용 되지 않은 사각형 및 회전 변환 사용 하 여 경로 그립니다. (있다고 가정 하 고 전 세계 변환이 없습니다.)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 다양 한 결과 달성 하기 위해 로컬 변환 사용 하 여 월드 변형을 결합할 수 있습니다. 예를 들어, 좌표계를 수정 하 고 회전 하 고 새 좌표 시스템에서 그린 개체를 확장할 로컬 변환을 사용 하는 월드 변형을 사용할 수 있습니다.  
  
 클라이언트 영역의 왼쪽된 가장자리에서 해당 원본 200 픽셀 있고 클라이언트 영역의 위쪽에서 150 픽셀 좌표 시스템을 한다고 가정 합니다. 또한 x 축이 오른쪽 및 위쪽을 가리키는 y 축에는 픽셀 수를 측정 단위의 한다고 가정해 보십시오. 기본 좌표계 y 축은 아래쪽에 있으므로 가로 축에서 반사를 수행 해야 합니다. 다음 그림은 이러한 반사는 매트릭스를 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 다음으로, 오른쪽에 200 단위를 이동 및 아래로 150 단위를 수행 해야 하는 것으로 가정 합니다.  
  
 다음 예제에서는 설정의 전역 변환을 설정 하 여 방금 설명한 좌표계는 <xref:System.Drawing.Graphics> 개체입니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 (위 예의 끝에 배치 됨) 다음 코드에는 새 좌표계 원점에서 왼쪽 아래 모퉁이 단일 사각형으로 구성 된 경로 만듭니다. 로컬 변환이 한 번 로컬 변환 사각형을 한 번 채워집니다. 로컬 변형을 30도 회전을 뒤에 2 배 수평적 확장으로 구성 됩니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 다음 그림은 새 좌표계 및 두 개의 사각형을 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>참고자료

- [좌표계 및 변환](coordinate-systems-and-transformations.md)
- [관리형 GDI+에서 변환 사용](using-transformations-in-managed-gdi.md)
