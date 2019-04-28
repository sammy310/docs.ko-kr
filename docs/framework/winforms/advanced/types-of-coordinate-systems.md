---
title: 좌표계 형식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 765df4bcd3cef83e624ad8b11676696b95f7d035
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792367"
---
# <a name="types-of-coordinate-systems"></a>좌표계 형식
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 세 가지 좌표 공간을 사용 하 여: 전역, 페이지 및 장치입니다. 세계 좌표 좌표 특정 그래픽 월드를 모델링 하는 데 사용 되며.NET Framework의 메서드에 전달 합니다. 페이지 좌표 양식이 나 컨트롤 같은 그리기 화면을 사용 하는 좌표계를 가리킵니다. 장치 좌표는 화면이 나 용지 같이 항목이 그려지는 실제 장치에서 사용 된 좌표입니다. 호출이 이루어지면 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`에 전달 하는 지점 합니다 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드-`(0, 0)` 및 `(160, 80)`-세계 좌표 공간에 합니다. 전에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 화면에서 선을 그리려면, 좌표 변환의 시퀀스를 통과 합니다. 월드 변형을 호출 하는 하나의 변환 세계 좌표를 페이지 좌표로 변환 하는 페이지 변환을 통해 다른 변환 페이지 좌표 장치 좌표에 있습니다.  
  
## <a name="transforms-and-coordinate-systems"></a>변환 및 좌표계  
 원점은 왼쪽 위 모퉁이 사용 하지 않고 클라이언트 영역의 본문에는 좌표계를 사용 한다고 가정 합니다. 예를 들어, 원본 클라이언트 영역의 왼쪽된 가장자리에서 100 픽셀인 클라이언트 영역의 위쪽에서 50 픽셀 이어야 한다고 가정해 보십시오. 다음 그림에서는 이러한 좌표 시스템을 보여 줍니다.  
  
 ![좌표계](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 호출을 수행 하면 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, 다음 그림에 표시 된 줄을 가져옵니다.  
  
 ![좌표계](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 세 가지 좌표 공간에서 선의 끝점 좌표는 다음과 같습니다.  
  
|||  
|-|-|  
|전 세계|(0, 0)를 (160, 80)|  
|페이지|(100, 50)를 (260, 130)|  
|디바이스|(100, 50)를 (260, 130)|  
  
 페이지 좌표 공간을 사용 하는 참고; 클라이언트 영역의 왼쪽 위 모퉁이 원점 이 항상 사용 됩니다. 측정 단위를 픽셀 이기 때문에 장치 좌표는 페이지 좌표와 같은 note도 합니다. 측정 단위를 픽셀 (예를 들어, 인치) 이외의 값으로 설정한 경우 장치 좌표 다 페이지 좌표를 수 됩니다.  
  
 영역 좌표를 페이지 좌표로 매핑하, 세계 변환에 저장 된 합니다 <xref:System.Drawing.Graphics.Transform%2A> 의 속성을 <xref:System.Drawing.Graphics> 클래스. 앞의 예에서 월드의 x 방향의 100 단위 및 y 방향의 50 단위입니다. 월드 변형을 설정 하는 다음 예제는 <xref:System.Drawing.Graphics> 개체 및을 사용 하 여 <xref:System.Drawing.Graphics> 위의 그림에 표시 된 줄을 그릴 개체:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 페이지 변형 장치 좌표로 페이지 좌표를 매핑합니다. 합니다 <xref:System.Drawing.Graphics> 클래스를 제공 합니다 <xref:System.Drawing.Graphics.PageUnit%2A> 및 <xref:System.Drawing.Graphics.PageScale%2A> 페이지 변환 조작에 대 한 속성입니다. <xref:System.Drawing.Graphics> 클래스에서는 두 개의 읽기 전용 속성 <xref:System.Drawing.Graphics.DpiX%2A> 및 <xref:System.Drawing.Graphics.DpiY%2A>, 가로 및 세로 인치당 디스플레이 장치의 검사 합니다.  
  
 사용할 수는 <xref:System.Drawing.Graphics.PageUnit%2A> 의 속성을 <xref:System.Drawing.Graphics> 픽셀 이외의 측정 단위를 지정 하는 클래스입니다.  
  
> [!NOTE]
>  설정할 수 없습니다는 <xref:System.Drawing.Graphics.PageUnit%2A> 속성을 <xref:System.Drawing.GraphicsUnit.World>처럼 하지 물리적 단위 이며 예외가 발생 합니다.  
  
 다음 예제에서 선을 그립니다 (0, 0)를 (2, 1) 점 (2, 1) 인 2 인치 오른쪽 및 아래쪽 1 인치 지점 (0, 0)에서:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  펜을 생성 하는 경우 펜 굵기를 지정 하지 않으면, 앞의 예제 1 인치 와이드 선을 그립니다. 두 번째 인수에 펜 너비를 지정할 수는 <xref:System.Drawing.Pen> 생성자:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 디스플레이 장치에는 가로 방향 인치당 96 도트와 세로 방향 인치당 96 도트를 가정 하는 경우 앞의 예제에서 선의 끝점 좌표는 다음과 세 좌표 공간에서:  
  
|||  
|-|-|  
|전 세계|(0, 0)를 (2, 1)|  
|페이지|(0, 0)를 (2, 1)|  
|디바이스|(0, 0에 (192, 96)|  
  
 클라이언트 영역의 왼쪽 위 모퉁이에서 세계 좌표 공간의 원본 이기 때문에 페이지 좌표는 전 세계 좌표와 같은 note 합니다.  
  
 다양 한 효과 달성 하기 위해 월드 및 페이지 변형을 결합할 수 있습니다. 예를 들어 인치를 측정 단위로 사용 하려는 하 고 클라이언트 영역 및 1/2 인치 클라이언트 영역의 위쪽에서 왼쪽된 가장자리 로부터 2 인치 좌표 시스템의 원본입니다. 다음 예제에서는 설정의 월드 및 페이지 변형을 <xref:System.Drawing.Graphics> 개체 및 선을 그립니다 (0, 0)를 (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 다음 그림은 줄 및 좌표계를 나타냅니다.  
  
 ![좌표계](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 디스플레이 장치에는 가로 방향 인치당 96 도트와 세로 방향 인치당 96 도트를 가정 하는 경우 앞의 예제에서 선의 끝점 좌표는 다음과 세 좌표 공간에서:  
  
|||  
|-|-|  
|전 세계|(0, 0)를 (2, 1)|  
|페이지|(2, 0.5)를 (4, 1.5)|  
|디바이스|(192, 48)를 (384, 144)|  
  
## <a name="see-also"></a>참고자료

- [좌표계 및 변형](coordinate-systems-and-transformations.md)
- [매트릭스에 의한 변형 표시](matrix-representation-of-transformations.md)
