---
title: '* 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 7038fef4258d190b726a851b26f2a2840ff3c0ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873366"
---
# <a name="-operator-visual-basic"></a>* 연산자(Visual Basic)

두 숫자를 곱합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`number1`|필수 요소. 임의의 숫자 식입니다.|  
|`number2`|필수 요소. 임의의 숫자 식입니다.|  
  
## <a name="result"></a>결과  

 결과는 및의 곱입니다 `number1` `number2` .  
  
## <a name="supported-types"></a>지원 형식  

 부호 없는 형식 및 부동 소수점 형식 및를 포함 하는 모든 숫자 형식 `Decimal` 입니다.  
  
## <a name="remarks"></a>설명  

 결과의 데이터 형식은 피연산자의 형식에 따라 달라 집니다. 다음 표에서는 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.  
  
|피연산자 데이터 형식|Result 데이터 형식|  
|---|---|  
|두 식은 모두 정수 데이터 형식 ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))입니다.|및의 데이터 형식에 적합 한 숫자 데이터 형식 `number1` 입니다 `number2` . [연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.|  
|두 식이 모두 [Decimal](../data-types/decimal-data-type.md) 입니다.|`Decimal`|  
|두 식이 모두 [단일](../data-types/single-data-type.md) 입니다.|`Single`|  
|두 식이 모두 부동 소수점 데이터 형식 ( `Single` 또는 [Double](../data-types/double-data-type.md)) 이지만 둘 다는 아닙니다 `Single` (참고 `Decimal` 는 부동 소수점 데이터 형식이 아님).|`Double`|  
  
 식이 [Nothing](../nothing.md)으로 계산 되 면 0으로 처리 됩니다.  
  
## <a name="overloading"></a>오버로딩  

 `*`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 이 예제에서는 연산자를 사용 `*` 하 여 두 숫자를 곱합니다. 결과는 두 피연산자의 곱입니다.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>참조

- [* = 연산자](multiplication-assignment-operator.md)
- [산술 연산자](arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
