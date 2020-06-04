---
title: EscapeQuote가 True로 설정되어 있으면 큰따옴표가 구분된 필드의 올바른 주석 토큰이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: a66d43d249a12ffa552073866f2e0a1e6d453608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409943"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>EscapeQuote가 True로 설정되어 있으면 큰따옴표가 구분된 필드의 올바른 주석 토큰이 아닙니다.

`TextFieldParser`에 대한 구분 기호로 따옴표가 제공되었지만 `EscapeQuotes` 가 `True`로 설정되어 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `EscapeQuotes`를 `False`로 설정합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [방법: 쉼표로 구분된 텍스트 파일에서 읽기](../../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
