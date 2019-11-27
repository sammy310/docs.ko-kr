---
title: 배열 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349073"
---
# <a name="troubleshooting-arrays-visual-basic"></a>배열 문제 해결(Visual Basic)
이 페이지에서는 배열로 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>컴파일 오류 배열 선언 및 초기화  
 배열의 선언, 생성 및 초기화에 대 한 규칙 있다면 오해에서 컴파일 오류가 발생할 수 있습니다. 오류의 가장 일반적인 원인은 다음과 같습니다.  
  
- 배열 변수 선언에서 차원 길이를 지정한 후 [새 Operator](../../../../visual-basic/language-reference/operators/new-operator.md) 절을 제공 합니다. 다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- 가변 배열의 최상위 배열 보다 많은 차원 길이를 지정 하는 경우 다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- 요소 값을 지정할 때 `New` 키워드를 생략 합니다. 다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- 중괄호 없이 `New` 절 제공 (`{}`) 다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>범위를 벗어난 배열 액세스  
 배열을 초기화 하는 프로세스는 상한을 할당 하 고 각 차원에는 하한값을 할당 합니다. 배열의 요소에 대 한 모든 액세스는 모든 차원에 대해 유효한 인덱스 또는 첨자를 지정 해야 합니다. 인덱스의 하 한이 낮거나 상한 보다 작으면 <xref:System.IndexOutOfRangeException> 예외가 발생 합니다. 컴파일러는 이러한 오류를 검색할 수 없으므로 런타임에 오류가 발생 합니다.  
  
### <a name="determining-bounds"></a>범위 결정  
 다른 구성 요소에서 코드에 배열을 전달 하는 경우 (예: 프로시저 인수) 해당 배열의 크기나 차원의 길이를 알 수 없습니다. 모든 요소에 액세스 하기 전에 항상 배열의 모든 차원에 대 한 상한을 결정 해야 합니다. Visual Basic `New` 절 이외의 방법으로 배열을 만든 경우 하한값은 0이 아닐 수 있으며, 그 하한값을 확인 하는 것이 가장 안전 합니다.  
  
### <a name="specifying-the-dimension"></a>차원 지정  
 다차원 배열의 범위를 결정할 때는 차원을 지정 하는 방법을 주의 해야 합니다. <xref:System.Array.GetLowerBound%2A> 및 <xref:System.Array.GetUpperBound%2A> 메서드의 `dimension` 매개 변수는 0부터 사용 되지만 Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> 및 <xref:Microsoft.VisualBasic.Information.UBound%2A> 함수의 `Rank` 매개 변수는 1부터 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목

- [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [방법: Visual Basic에서 배열 변수 초기화](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
