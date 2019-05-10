---
title: Visual Basic에서의 연산자 우선 순위
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 95505fd593881ff27418c69550952d072b4e3949
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628867"
---
# <a name="operator-precedence-in-visual-basic"></a>Visual Basic에서의 연산자 우선 순위
각 파트 평가 되 고 호출 하는 미리 결정 된 순서 대로 확인 식에서 여러 작업 발생 *연산자 우선 순위*합니다.  
  
## <a name="precedence-rules"></a>우선 순위 규칙  
 식에서 연산자는 둘 이상의 범주에서에 포함 하는 경우 다음 규칙에 따라 계산 됩니다.  
  
- 산술 연산 및 연결 연산자는 다음 섹션에 설명 된 우선 순위를 있고 모든 비교, 논리 보다 높은 우선 순위 및 비트 연산자입니다.  
  
- 모든 비교 연산자는 동등한 우선 순위 및 논리 및 비트 연산자 보다 높은 우선 순위를 갖지만 산술 및 연결 연산자 보다 우선 순위가 모든 경우  
  
- 논리 및 비트 연산자는 다음 섹션에 설명 된 우선 순위를 있고 모든 산술 연산, 연결 및 비교 연산자 보다 우선 순위가 낮습니다.  
  
- 우선 순위가 같은 연산자는 왼쪽에서 오른쪽으로 계산 됩니다 식에서 나타나는 순서입니다.  
  
## <a name="precedence-order"></a>우선 순위  
 연산자 우선 순위 순서로 평가 됩니다.  
  
### <a name="await-operator"></a>Await 연산자  
 Await  
  
### <a name="arithmetic-and-concatenation-operators"></a>산술 연산 및 연결 연산자  
 지 수 (`^`)  
  
 단항 id 및 부정 연산자 (`+`, `–`)  
  
 곱하기와 부동 소수점 나누기 (`*`, `/`)  
  
 정수 나누기 (`\`)  
  
 모듈러스 산술 (`Mod`)  
  
 더하기 및 빼기 (`+`, `–`)  
  
 문자열 연결 (`&`)  
  
 산술 비트 시프트 (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>비교 연산자  
 모든 비교 연산자 (`=`, `<>`, `<`, `<=`, `>`를 `>=`, `Is`를 `IsNot`를 `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>논리 및 비트 연산자  
 부정 (`Not`)  
  
 함께 (`And`, `AndAlso`)  
  
 포함 논리합 (`Or`, `OrElse`)  
  
 배타적 논리합 (`Xor`)  
  
### <a name="comments"></a>설명  
 `=` 연산자는 같음 비교 연산자만, 대입 연산자가 없습니다.  
  
 문자열 연결 연산자 (`&`) 산술 연산자, 되지 않지만 산술 연산자를 사용 하 여 그룹화는 우선 순위에서입니다.  
  
 합니다 `Is` 고 `IsNot` 연산자는 개체 참조 비교 연산자입니다. 두 개체의 값을 비교 하지 않습니다. 이러한 두 개의 개체 변수가 같은 개체 인스턴스를 참조 하는지 여부 확인에이 옵션을 확인 합니다.  
  
## <a name="associativity"></a>associativity  
 우선 순위가 같은 연산자는 곱하기 및 나누기, 예를 들어 식에서 함께 표시 되 면 컴파일러도 왼쪽에서 오른쪽으로 각 작업을 평가 합니다. 다음은 이에 대한 예입니다.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 첫 번째 식이 96 나누기 / 8 (12 결과) 및 다음 나누기 12 / 결과 3 4입니다. 에 대 한 작업으로 계산 하므로 `n1` 왼쪽에서 오른쪽으로 평가 때 동일한 순서에 대 한 명시적으로 표시 됩니다 `n2`합니다. 둘 다 `n1` 고 `n2` 의 결과는 3입니다. 반면, `n3` 괄호 8을 평가 하는 컴파일러가 있으므로 결과는 48에 / 4 첫 번째입니다.  
  
 이 동작으로 인해 연산자 있다고 *왼쪽 결합형* Visual Basic의 합니다.  
  
## <a name="overriding-precedence-and-associativity"></a>재정의 우선 순위 및 결합성  
 다른 사용자가 하기 전에 평가할 식의 일부를 적용할 괄호를 사용할 수 있습니다. 이 우선 순위 순서와 왼쪽된 결합성 재정의할 수 있습니다. Visual Basic에는 항상 외부 보다 먼저 괄호로 묶이지 연산을 수행 합니다. 그러나 괄호 안에서 유지 일반 우선 순위와 결합성 괄호 안에서 괄호를 사용 하지 않는 한 합니다. 다음은 이에 대한 예입니다.  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a>참고자료

- [= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Like 연산자](../../../visual-basic/language-reference/operators/like-operator.md)
- [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Await 연산자](../../../visual-basic/language-reference/operators/await-operator.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
