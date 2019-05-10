---
title: '방법: 검색 문자열 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 57a3d9650ad78e1c8580fd46839c9a1cbc7794c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665334"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>방법: 검색 문자열 (Visual Basic)
이 예제에서는 호출을 <xref:System.String.IndexOf%2A> 메서드는 <xref:System.String> 부분 문자열의 첫 번째 발생의 인덱스를 보고 하는 개체입니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- `Imports` 문을 지정 하는 <xref:System> 네임 스페이스입니다. 자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 <xref:System.String.IndexOf%2A> 메서드 맨 처음 발견 되는 부분 문자열의 첫 번째 문자의 위치를 보고 합니다. 인덱스는 0 기반, 즉, 문자열의 첫 번째 문자에는 인덱스가 0입니다.  
  
 경우 <xref:System.String.IndexOf%2A> 부분 문자열을 찾지 못하면-1을 반환 합니다.  
  
 <xref:System.String.IndexOf%2A> 메서드는 대/소문자 구분 및 현재 문화권을 사용 합니다.  
  
 최적의 오류 컨트롤에 대 한 문자열 검색을 묶습니다 하려는 합니다 `Try` 블록을 [시도 하는 중... Catch 하는 중... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 생성 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.String.IndexOf%2A>
- [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [문자열](../../../../visual-basic/programming-guide/language-features/strings/index.md)
