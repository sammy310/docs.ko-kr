---
title: 문자 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: edd1d3a41dd878649aa422256b7858d7bce366e1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346391"
---
# <a name="character-data-types-visual-basic"></a>문자 데이터 형식(Visual Basic)
Visual Basic은 인쇄 가능 하 고 표시할 수 있는 문자를 처리 하는 *문자 데이터 형식을* 제공 합니다. 둘 다 유니코드 문자를 처리 하는 반면 `Char`는 단일 문자를 포함 하 고 `String`는 무한 문자 수를 포함 합니다.  
  
 Visual Basic 데이터 형식에 대 한 병렬 비교를 표시 하는 표는 [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)을 참조 하세요.  
  
## <a name="char-type"></a>Char 형식  
 `Char` 데이터 형식은 단일 2 바이트 (16 비트) 유니코드 문자입니다. 변수가 항상 정확히 하나의 문자를 저장 하는 경우 `Char`로 선언 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 `Char` 또는 `String` 변수에서 사용할 수 있는 각 값은 유니코드 문자 집합의 *코드 포인트*또는 문자 코드입니다. 유니코드 문자에는 기본 ASCII 문자 집합, 다양 한 영문자, 악센트, 통화 기호, 분수, 분음 부호, 수학 및 기술 기호가 포함 됩니다.  
  
> [!NOTE]
> 유니코드 문자 집합은 단일 코드 포인트를 나타내는 2 16 비트 값이 필요한 *서로게이트 쌍*에 대해 d 800 (55296 ~ 55551 decimal)까지 코드 포인트를 예약 합니다. `Char` 변수는 서로게이트 쌍을 포함할 수 없으며, `String`는 이러한 쌍을 보유 하는 데 두 개의 위치를 사용 합니다.  
  
 자세한 내용은 [Char 데이터 형식](../../../../visual-basic/language-reference/data-types/char-data-type.md)을 참조 하세요.  
  
## <a name="string-type"></a>문자열 형식  
 `String` 데이터 형식은 0 개 이상의 2 바이트 (16 비트) 유니코드 문자 시퀀스입니다. 변수에 무한 수의 문자가 포함 될 수 있는 경우 `String`로 선언 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 자세한 내용은 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고자료

- [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Visual Basic 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
