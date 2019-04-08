---
title: '방법: Visual Basic에서 StringBuilder를 사용 하 여 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834194"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>방법: Visual Basic에서 StringBuilder를 사용 하 여 문자열 만들기
이 예제를 사용 하 여 많은 짧은 문자열에서 긴 문자열을 생성 합니다 <xref:System.Text.StringBuilder> 클래스입니다. 합니다 <xref:System.Text.StringBuilder> 클래스 보다 더 효율적입니다는 `&=` 여러 문자열 연결 연산자.  
  
## <a name="example"></a>예제  
 다음 예에서는 인스턴스에 <xref:System.Text.StringBuilder> 클래스는 해당 인스턴스를 1,000 문자열을 추가 하 고 다음의 문자열 표현을 반환 합니다.  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>참고자료

- [StringBuilder 클래스 사용](../../../../standard/base-types/stringbuilder.md)
- [&= 연산자](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [문자열](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [새 문자열 만들기](../../../../standard/base-types/creating-new.md)
- [문자열 조작](../../../../standard/base-types/manipulating-strings.md)
