---
title: / 연산자
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: e9400b50a84522f87a9a2ea4cd05b479d7a4538e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371170"
---
# <a name="-operator-visual-basic"></a>/ 연산자(Visual Basic)
두 숫자를 나누고 부동 소수점 결과를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a>부분  
 `expression1`  
 필수 요소. 임의의 숫자 식입니다.  
  
 `expression2`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="supported-types"></a>지원 형식  
 부호 없는 형식 및 부동 소수점 형식 및를 포함 하는 모든 숫자 형식 `Decimal` 입니다.  
  
## <a name="result"></a>결과  
 그 결과는 `expression1` 나머지를 포함 하 여로 나눈 전체 몫입니다 `expression2` .  
  
 [\ 연산자 (Visual Basic)](integer-division-operator.md) 는 나머지를 삭제 하는 정수 몫을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 결과의 데이터 형식은 피연산자의 형식에 따라 달라 집니다. 다음 표에서는 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.  
  
|피연산자 데이터 형식|Result 데이터 형식|  
|------------------------|----------------------|  
|두 식은 모두 정수 데이터 형식 ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))입니다.|`Double`|  
|한 식은 [단일](../data-types/single-data-type.md) 데이터 형식이 고 다른 하나는 [Double](../data-types/double-data-type.md) 이 아닙니다.|`Single`|  
|한 식은 [Decimal](../data-types/decimal-data-type.md) 데이터 형식이 고 다른 하나는 [단일](../data-types/single-data-type.md) 또는 [Double](../data-types/double-data-type.md) 이 아닙니다.|`Decimal`|  
|두 식이 모두 [Double](../data-types/double-data-type.md) 데이터 형식입니다.|`Double`|  
  
 나누기를 수행 하기 전에 정수 계열 숫자 식이로 확장 됩니다 `Double` . 정수 계열 데이터 형식에 결과를 할당 하는 경우 Visual Basic 결과를 해당 형식으로 변환 하려고 시도 합니다 `Double` . 결과가 해당 형식에 맞지 않는 경우 예외를 throw 할 수 있습니다. 특히이 도움말 페이지의 "0으로 나누기 시도"를 참조 하십시오.  
  
 `expression1`또는가 `expression2` [Nothing](../nothing.md)으로 계산 되 면 0으로 처리 됩니다.  
  
## <a name="attempted-division-by-zero"></a>0으로 나누기 시도  
 가 `expression2` 0으로 계산 되는 경우 `/` 연산자는 피연산자 데이터 형식에 따라 다르게 동작 합니다. 다음 표에서는 가능한 동작을 보여 줍니다.  
  
|피연산자 데이터 형식|`expression2`가 0 인 경우의 동작|  
|------------------------|---------------------------------------|  
|부동 소수점 ( `Single` 또는 `Double` )|<xref:System.Double.PositiveInfinity>가 0 인 경우 infinity (또는 <xref:System.Double.NegativeInfinity> ) 또는 <xref:System.Double.NaN> (숫자가 아님) `expression1` 을 반환 합니다.|  
|`Decimal`|되거나<xref:System.DivideByZeroException>|  
|정수 (부호 있음 또는 부호 없음)|<xref:System.OverflowException>정수 계열 형식 <xref:System.Double.PositiveInfinity> 에서, 또는를 사용할 수 없으므로 정수 계열 형식으로 다시 변환 하려고 시도 했습니다. <xref:System.Double.NegativeInfinity><xref:System.Double.NaN>|  
  
> [!NOTE]
> `/`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 연산자를 사용 `/` 하 여 부동 소수점 나누기를 수행 합니다. 결과는 두 피연산자의 몫입니다.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 위의 예제에서 식은 2.5 및 3.333333의 값을 반환 합니다. `Double`두 피연산자가 모두 정수 상수인 경우에도 결과는 항상 부동 소수점 ()입니다.  
  
## <a name="see-also"></a>참고 항목

- [/= 연산자 (Visual Basic)](floating-point-division-assignment-operator.md)
- [\ 연산자 (Visual Basic)](integer-division-operator.md)
- [연산자 결과의 데이터 형식](data-types-of-operator-results.md)
- [산술 연산자](arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
