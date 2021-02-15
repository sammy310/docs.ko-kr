---
description: '자세히 알아보기: 방법: Char 값의 배열에서 문자열 만들기 (Visual Basic)'
title: '방법: 문자 값의 배열에서 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 67b675f5f02c92b785e374b99f49248d43d12fb4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429834"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>방법: Char 값으로 이루어진 배열로 문자열 만들기(Visual Basic)

이 예에서는 개별 문자에서 "abcd" 문자열을 만듭니다.  
  
## <a name="example"></a>예  

 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a>코드 컴파일  

 이 메서드에는 특별 한 요구 사항이 없습니다.  
  
 작은따옴표 `"a"c` `c` 에서 단일 문자 뒤에 오는 구문은 문자 리터럴을 만드는 데 사용 됩니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  

 문자열에서 Null 문자 (에 해당 `Chr(0)` )를 사용 하면 문자열을 사용 하는 경우 예기치 않은 결과가 발생할 수 있습니다. Null 문자는 문자열에 포함 되지만 null 문자 다음에 나오는 문자는 일부 상황에서 표시 되지 않습니다.  
  
## <a name="see-also"></a>추가 정보

- <xref:System.String>
- [Char 데이터 형식](../../../language-reference/data-types/char-data-type.md)
- [데이터 형식](../data-types/index.md)
