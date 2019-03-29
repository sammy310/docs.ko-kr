---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 47b90a6c513a5808dc0669d2d861de5e16406a34
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634169"
---
# <a name="array-dimensions-in-visual-basic"></a>Array Dimensions in Visual Basic
A *차원* 은 방향 배열 요소의 사양을 변경할 수 있습니다. 해당 월의 각 날짜에 대 한 총 판매량을 보유 하는 배열 이상의 차원을 (해당 월의 일)을 포함 합니다. 총 판매액이 들어 부서에서 월의 각 날짜에는 배열에 두 개의 차원 (부서 번호 및 월의 일). 배열의 차원 수 라고 해당 *순위*합니다.  
  
> [!NOTE]
>  사용할 수는 <xref:System.Array.Rank%2A> 얼마나 많은 차원 배열에 확인 하는 속성입니다.  
  
## <a name="working-with-dimensions"></a>차원 작업  
 제공 하 여 배열의 요소를 지정할 수 있습니다는 *인덱스* 하거나 *첨자* 배열의 각 차원에 대 한 합니다. 요소는 해당 차원에 대 한 가장 높은 인덱스를 인덱스 0에서에서 각 차원에 따라 연속.  
  
 다음 그림에는 개념적 구조의 서로 다른 순위를 사용 하 여 배열 보여 줍니다. 그림의 각 요소에 액세스 하는 인덱스 값을 보여 줍니다. 예를 들어, 2 차원 배열의 두 번째 행의 첫 번째 요소 인덱스를 지정 하 여 액세스할 수 있습니다 `(1, 0)`합니다.  
  
 ![1 차원 배열을 보여 주는 다이어그램입니다.](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![2 차원 배열을 보여 주는 다이어그램입니다.](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![3 차원 배열을 보여 주는 다이어그램입니다.](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a>하나 이상의 차원  
 여러 개의 배열을 하나의 차원만 각 나이 사람의 수와 같은 경우 요소를 지정 하기만 하면은 해당 요소는 카운트를 보유 기간입니다. 따라서 이러한 배열은 하나의 인덱스를 사용합니다. 보유 하는 변수를 선언 하는 다음 예제는 *1 차원 배열* 의 나가 120 사이의 0에 대 한 계산 합니다.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>2 차원  
 일부 배열의 각 건물에 캠퍼스의 각 층에 사무실 수와 같은 2 차원 경우 요소 사양에 건물 번호와 층, 건물 및 층 조합에 대해 카운트를 보유 하는 각 요소를 따라서 이러한 배열은 두 개의 인덱스를 사용합니다. 보유 하는 변수를 선언 하는 다음 예제는 *2 차원 배열을* 0 ~ 40 건물과 층 0 ~ 5에 대 한 office 개수입니다.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 2 차원 배열을 라고 한 *사각형 배열을*합니다.  
  
### <a name="three-dimensions"></a>3 차원  
 몇 가지 배열은 있는 3 차원 공간에서 값과 같은 3 차원입니다. 이러한 배열은 여기서 x, y 및 z 좌표 물리적 공간을 표시 하는 3 개의 인덱스를 사용 합니다. 다음 예제에서는 보유 하는 변수를 선언를 *3 차원 배열* 한 온도가 차원 공간의 다양 한 시점입니다.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>세 개 이상의 차원  
 배열 만큼 32 차원을 포함할 수 있습니다를 이지만 거의 4 개 없습니다.  
  
> [!NOTE]
>  차원 배열에 추가 하면 상당히 신중 하 게 하므로 사용 하 여 다차원 배열의 배열에 필요한 총 저장소 증가 합니다.  
  
## <a name="using-different-dimensions"></a>다른 차원을 사용 하 여  
 현재 월의 모든 날에 대 한 판매 금액을 추적 하려고 한다고 가정 합니다. 다음 예제와 같이 월의 각 날짜에 대 한 항목이 표시 31 요소를 사용 하 여 1 차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 이제 월간 아니라 연도의 매월 뿐만 아니라 매일에 대 한 동일한 정보를 추적 하려고 한다고 가정해 보겠습니다. 다음 예제와 같이 (월)에 대 한 12 행과 (일) 동안 31 개 열이 있는 2 차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 이제 할 가정해 배열에 1 년 이상에 대 한 정보를 저장 합니다. 5 년에 대 한 판매 금액을 추적 하려는 경우 다음 예제와 같이 5 계층, 12 행 및 31 개 열을 사용 하 여 3 차원 배열을 선언할 수 있습니다.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 이때 각 인덱스의 각 차원 최대값으로 0에서 달라 지므로 `salesAmounts` 해당 차원에 필요한 길이 보다 1 작은 값으로 선언 됩니다. 각 새 차원 배열의 크기 증가 또한 note 합니다. 앞의 예제에서 세 가지 크기는 각각 31, 372, 및 1,860 요소입니다.  
  
> [!NOTE]
>  사용 하지 않고 배열을 만들 수 있습니다 합니다 `Dim` 문 또는 `New` 절. 예를 들어, 호출할 수 있습니다는 <xref:System.Array.CreateInstance%2A> 메서드 또는 다른 구성 요소 배열을 전달할 수 코드 이러한 방식으로 생성 합니다. 이러한 배열은 0이 아닌 하한값을 가질 수 있습니다. 사용 하 여 차원에서 최소치 항상 테스트할 수 있습니다 합니다 <xref:System.Array.GetLowerBound%2A> 메서드 또는 `LBound` 함수입니다.  
  
## <a name="see-also"></a>참고자료
- [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [배열 문제 해결](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
