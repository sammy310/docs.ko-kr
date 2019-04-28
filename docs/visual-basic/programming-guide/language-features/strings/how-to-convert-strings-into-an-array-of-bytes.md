---
title: '방법: Visual Basic에서 바이트 배열을 문자열 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 2fa0b86459e6191d3bd5f884d92b071218b4063a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938309"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>방법: Visual Basic에서 바이트 배열을 문자열 변환
이 항목에는 바이트 배열을 문자열로 변환 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 합니다 <xref:System.Text.Encoding.GetBytes%2A> 메서드는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding 바이트 배열을 문자열로 변환 하는 클래스입니다.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 문자열을 바이트 배열로 변환할 여러 인코딩 옵션 중에서 선택할 수 있습니다.  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII(7비트) 문자 집합에 대한 인코딩을 가져옵니다.  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Big endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하 여 UTF-32 형식에 대 한 인코딩을 가져옵니다.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 형식에 대한 인코딩을 가져옵니다.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 형식에 대한 인코딩을 가져옵니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [방법: Visual Basic의 문자열 바이트 배열로 변환](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
