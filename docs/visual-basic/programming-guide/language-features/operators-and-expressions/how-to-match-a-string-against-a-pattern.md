---
title: '방법: (Visual Basic) 패턴에 대해 문자열 비교'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: e5eb6bd5b5e7b2f0c3692c0fa2431a0b8f295299
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649721"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>방법: (Visual Basic) 패턴에 대해 문자열 비교
식을 확인 하려는 경우는 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) 사용 하 여 패턴을 만족 합니다 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)합니다.  
  
 `Like` 두 피연산자를 사용 합니다. 왼쪽된 피연산자가는 문자열 식 및 오른쪽 피연산자가 일치 하는 데 사용할 패턴을 포함 하는 문자열입니다. `Like` 반환 된 `Boolean` 문자열 식 패턴을 충족 하는지 여부를 나타내는 값입니다.  
  
 특정 문자, 와일드 카드 문자를 문자 목록, 또는 문자 범위에 대해 문자열 식의 각 문자를 일치 시킬 수 있습니다. 사양 패턴 문자열에 대 한 위치를 일치 시킬 문자를 문자열 식에서의 위치에 해당 합니다.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>특정 문자에서 문자열 식의 문자를 검색 하려면  
  
- 특정 문자 패턴 문자열에 직접 배치 합니다. 특수 문자를 대괄호로 묶어야 합니다 (`[ ]`). 자세한 내용은 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)합니다.  
  
     다음 예제에서는 테스트 하는지 여부를 `myString` 단일 문자를 정확히 이루어져 `H`합니다.  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>와일드 카드 문자는 문자열 식의 문자를 검색 하려면  
  
- 물음표 (`?`) 패턴 문자열에 있습니다. 이 위치에서 모든 유효한 문자일 성공한 일치 항목을 만듭니다.  
  
     다음 예제에서는 테스트 하는지 여부를 `myString` 단일 문자로 `W` 뒤에 정확히 두 문자의 값입니다.  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>문자 목록에서 문자열 식의 문자를 검색 하려면  
  
- 대괄호 (`[ ]`) 패턴 문자열에 문자의 목록을 저장 하는 대괄호 안에 있습니다. 쉼표 또는 다른 구분 기호를 사용 하 여 문자를 구분 하지 않습니다. 목록에서 단일 문자와 일치 하는 항목 수 있습니다.  
  
     다음 예제에서는 테스트 하는지 여부를 `myString` 뒤에 문자 중 하나만 모든 유효한 문자일 이루어져 `A`, `C`, 또는 `E`.  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     이 일치는 대/소문자 구분 임을 유의 합니다.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>문자 범위에서 문자열 식의 문자를 검색 하려면  
  
- 대괄호 (`[ ]`) 하이픈으로 구분 된 패턴 문자열 및 최저 및 최고 문자 범위를 넣을 대괄호 (`–`). 범위 내 모든 단일 문자를 일치 하는 항목을 만듭니다.  
  
     다음 예제에서는 테스트 하는지 여부를 `myString` 문자로 구성 `num` 뒤에 문자 중 하나만 `i`, `j`, `k`, `l`, `m`, 또는 `n`합니다.  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     이 일치는 대/소문자 구분 임을 유의 합니다.  
  
## <a name="matching-empty-strings"></a>일치 하는 빈 문자열  
 `Like` 시퀀스를 처리 `[]` 길이가 0 인 문자열로 (`""`). 사용할 수 있습니다 `[]` 전체 문자열 식이 비어 있지만 빈 문자열 식의 특정 위치 인지를 테스트 하는 데 사용할 수 없습니다 수 있는지 여부를 테스트 합니다. 사용할 수에 대 한 테스트 해야 하는 빈 위치 옵션 중 하나 이면 `Like` 두 번 이상.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>문자 또는 문자가 없는 목록에서 문자열 식의 문자를 검색 하려면  
  
1. 호출를 `Like` 연산자에 동일한 두 번 문자열 식, 및 중 하나를 사용 하 여 두 호출을 연결 합니다 [또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 또는 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md)합니다.  
  
2. 첫 번째 패턴 문자열에 `Like` 절을 대괄호로 묶은 문자 목록을 포함 (`[ ]`).  
  
3. 두 번째 패턴 문자열에 `Like` 절에 두지 마십시오 임의의 위치에 해당 합니다.  
  
     다음 예제에서는 7 자리 전화 번호를 테스트 `phoneNum` 정확히 3 자리 숫자에 대 한 뒤에 공백, 하이픈 (`–`), 마침표 (`.`), 문자가 없는 전혀 뒤에 정확히 4 자리 숫자입니다.  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a>참고자료

- [비교 연산자](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md)
- [String 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)
