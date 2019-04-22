---
title: '&amp; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: dd85363447e9b405241d608550d9484b4760a739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817281"
---
# <a name="amp-operator-visual-basic"></a>&amp; 연산자 (Visual Basic)
두 식의 문자열 연결을 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `String` 또는 `Object` 변수입니다.  
  
 `expression1`  
 필수 요소. 데이터 형식으로 확대 되는 식을 `String`합니다.  
  
 `expression2`  
 필수 요소. 데이터 형식으로 확대 되는 식을 `String`합니다.  
  
## <a name="remarks"></a>설명  
 데이터 형식이 `expression1` 또는 `expression2` 아닙니다 `String` 로 확대 변환 하지만 `String`, 변환할 `String`합니다. 하는 경우 데이터 형식 중 하나는 변환할 `String`, 컴파일러는 오류를 생성 합니다.  
  
 데이터 형식이 `result` 는 `String`합니다. 하나 또는 둘 다 식으로 계산 되 면 [아무](../../../visual-basic/language-reference/nothing.md) 의 값 또는 <xref:System.DBNull.Value?displayProperty=nameWithType>의 값을 사용 하 여 문자열로 처리 되는 ""입니다.  
  
> [!NOTE]
>  합니다 `&` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
> [!NOTE]
>  앰퍼샌드 (&) 문자로 사용할 수도 있습니다 형식으로 변수를 식별 하려면 `Long`합니다. 자세한 내용은 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `&` 문자열을 연결 하는 연산자입니다. 결과 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>참고자료

- [&= 연산자](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 연결 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
