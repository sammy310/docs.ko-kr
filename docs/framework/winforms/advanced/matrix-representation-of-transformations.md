---
title: 변환에 대한 매트릭스 표현
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: ceaad7b4bb5a70a890d261e39bc608becb388c17
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505631"
---
# <a name="matrix-representation-of-transformations"></a>변환에 대한 매트릭스 표현
m × n 행렬은 행 m과 n 열으로 정렬 하는 숫자 집합입니다. 다음 그림에서는 몇 가지 매트릭스를 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 개별 요소를 추가 하 여 동일한 크기의 두 행렬을 추가할 수 있습니다. 다음 그림에서는 행렬 추가의 두 가지 예제를 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 M × n 매트릭스는 n × p 매트릭스를 곱한 수 수 이며 결과 m × p 행렬입니다. 첫 번째 행렬의 열 수가 두 번째 행렬의 행 수와 같아야 합니다. 예를 들어, 4 × 2 행렬 4 × 3 행렬을 생성 하기 위해 2 3 × 매트릭스를 곱할 수입니다.  
  
 벡터로 평면 및 행과 행렬의 열에는 지점을 생각할 수 있습니다. 예를 들어, (2, 5)는 두 가지 구성 요소를 사용 하 여 벡터 및 (3, 7, 1)는 세 가지 구성 요소를 사용 하 여 벡터입니다. 두 벡터의 내적 다음과 같이 정의 됩니다.  
  
 (a, b) • (c, d) = ac + bd  
  
 (a, b, c) • (d, e, f) = ad + be + cf  
  
 내적 예를 들어, (2, 3) 및 (5, 4)는 (2)(5) + (3)(4) = 22입니다. (2, 5, 1)의 내적 및 (4, 3, 1)는 (2)(4) + (5)(3) + (1)(1) = 24입니다. 두 벡터의 내적이 숫자를 다른 벡터를 참고 합니다. 두 벡터 구성 요소의 수가 같은 경우에 내적을 계산할 수 있습니다 note도 합니다.  
  
 A(i, j) 수 있도록 i 번째 행과까지 j 번째 열에는 행렬의 항목 수입니다. 예를 들어 A (3, 2) 세 번째 행과 두 번째 열에는 행렬의 항목입니다. A, B 및 C는 행렬 및 AB 가정 = 3. C의 항목은 다음과 같이 계산 됩니다.  
  
 C(i, j) = (row i of A) • (column j of B)  
  
 다음 그림에서는 행렬 곱셈의 몇 가지 예를 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 1 × 2 행렬으로 평면에 있는 점의 생각 되 면 해당 지점 2 × 2 행렬을 곱하여 변환할 수 있습니다. 다음 그림에서는 점 (2, 1)에 적용 하는 몇 가지 변환을 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 위의 그림 에서처럼 변환을 모두 선형 변환 합니다. 변환와 같은 다른 변환 특정 선형이 아니므로 및 2 × 2 행렬 곱으로 표현할 수 없습니다. 만든다고 시작 지점 (2, 1) 90도 회전, 3 개 단위 x 방향의 변환 및 y 방향으로 4 개 단위 변환 뒤에 행렬 추가 행렬 곱셈을 사용 하 여이 수행할 수 있습니다.  
  
 ![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 번역 (1 2 × 행렬 추가) 뒤에 선형 변환 (2 × 2 행렬에서 곱하기)는 3x3 유사 변형을 라고 합니다. 3x3 유사 변형 행렬 (선형 부분에 대해 하나) 및 변환에 대 한 쌍에 저장 하는 대신 3 × 3 행렬의 변환 전체를 저장 하는 것입니다. 이 작업을 하려면 평면에서 점은 더미 타사 좌표를 사용 하 여 1 × 3 행렬에 저장 되어야 합니다. 일반적인 방법은 1 모든 타사 좌표 수 있도록 하는 것입니다. 예를 들어, 점 (2, 1) 행렬 [1 1 2]로 표시 됩니다. 다음 그림과 3x3 유사 변형 (90도 회전, 3 방향으로에서 단위 x, y 방향으로 4 개 단위 변환) 단일 3 × 3 행렬 곱으로 표현 합니다.  
  
 ![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 앞의 예제에서 점 (2, 1) 점 (2, 6)에 매핑됩니다. 숫자 0, 0, 1 3 × 3 행렬의 세 번째 열에 포함 되도록 note 합니다. 이 항상 3 × 3 행렬 사례의 3x3 유사 변형 됩니다. 중요 한 숫자는 1과 2 열에서 6 개의 숫자입니다. 행렬의 왼쪽 위 2 × 2 부분은 변환의 선형 부분을 나타내고 세 번째 행에서 처음 두 항목은 변환 합니다.  
  
 ![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 GDI +는 3x3 유사 변형에 저장할 수 있습니다는 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다. 나타내는 3x3 유사 변형 매트릭스의 세 번째 열은 항상 때문에 (0, 0, 1)을 생성 하는 경우 처음 두 열에 있는 6 개의 숫자만 지정를 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다. 문이 `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` 앞의 그림에 표시 된 행렬을 생성 합니다.  
  
## <a name="composite-transformations"></a>합성 변형  
 복합 변환에는 뒤에 다른 하나는 변환의 시퀀스입니다. 행렬 및 다음과 같은 변환을 고려 합니다.  
  
|||  
|-|-|  
|행렬|90도 회전|  
|행렬 B|X 방향으로 2 배 확장|  
|행렬 C|Y 방향의 3 단위|  
  
 점 (2, 1)부터 시작 하는 경우-행렬 [1 1 2]로 표시-및 C, 점 (2, 1)에 나열 된 순서로 세 가지 변환 될 예정 후 A, B로 곱합니다.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 대신 복합 변환의 세 부분에서 세 가지 별도 행렬을 저장 하는 보다에 곱할 수 B 및 C 함께 전체 복합 변환을 저장 하는 단일 3 × 3 행렬을 가져옵니다. ABC 가정 = 4. 그런 다음, D를 곱하면 A, B, C 곱하면와 동일한 결과 제공  
  
 [2 1 1]D = [-2 5 1]  
  
 다음 그림에서는 A, B, C 및 D. 행렬을 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 개별 변환 행렬을 곱하여 복합 변환의 매트릭스를 구성할 수는 팩트 관계 변형 시퀀스는 단일에서 저장할 수 있다는 의미 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다.  
  
> [!CAUTION]
>  복합 변환의 순서가 중요 합니다. 일반적으로 회전, 크기 조정을 차례로 다릅니다 변환으로 크기 조정, 회전, 그런 다음 변환 합니다. 마찬가지로 행렬 곱셈의 순서가 중요 합니다. 일반적으로 ABC 아닙니다 백업와 동일 합니다.  
  
 <xref:System.Drawing.Drawing2D.Matrix> 클래스는 복합 변환을 구성 하는 여러 가지 방법을 제공: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>를 <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>를 <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>를 <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, 및 <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>합니다. 다음 예제에서는 먼저 30도 회전 하 고 2 y 방향의 배율을 5 개 단위 x 방향으로 변환 하는 복합 변환의 행렬을 만듭니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 다음 그림에서는 행렬을 보여 줍니다.  
  
 ![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>참고자료

- [좌표계 및 변형](coordinate-systems-and-transformations.md)
- [관리 GDI+에서 변형 사용](using-transformations-in-managed-gdi.md)
