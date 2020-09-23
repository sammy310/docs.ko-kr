---
title: '방법: 문자열에 있는 문자에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 4ea37c4393a8ece5513327b22c6c0ba4b027c781
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059186"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>방법: Visual Basic에서 문자열 안의 문자에 액세스

이 예제에서는 속성을 사용 하 여 <xref:System.String.Chars%2A> 문자열의 지정 된 위치에 있는 문자에 액세스 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  

 문자열의 문자에 대 한 데이터와 문자열 내에서 해당 문자의 위치에 대 한 데이터를 포함 하는 것이 유용한 경우도 있습니다. 문자열은 문자 (인스턴스) 배열로 간주할 수 있으며 `Char` , 속성을 통해 해당 문자의 인덱스를 참조 하 여 특정 문자를 검색할 수 있습니다 <xref:System.String.Chars%2A> .  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 `index`속성의 매개 변수는 <xref:System.String.Chars%2A> 0부터 시작 합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  

 <xref:System.String.Chars%2A>속성은 지정 된 위치에 있는 문자를 반환 합니다. 그러나 일부 유니코드 문자는 둘 이상의 문자로 나타낼 수 있습니다. 유니코드 문자로 작업 하는 방법에 대 한 자세한 내용은 [방법: 문자열을 문자 배열로 변환](how-to-convert-a-string-to-an-array-of-characters.md)을 참조 하세요.  
  
 <xref:System.String.Chars%2A> <xref:System.IndexOutOfRangeException> `index` 매개 변수가 문자열의 길이 보다 크거나 같거나 0 보다 작은 경우 속성은 예외를 throw 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.String.Chars%2A>
- [방법: 문자열을 문자 배열로 변환](how-to-convert-a-string-to-an-array-of-characters.md)
- [Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환](converting-between-strings-and-other-data-types.md)
- [문자열](index.md)
