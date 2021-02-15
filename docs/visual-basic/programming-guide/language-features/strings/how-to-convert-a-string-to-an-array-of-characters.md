---
description: '자세한 정보: 방법: 문자열을 Visual Basic의 문자 배열로 변환'
title: '방법: 문자열을 문자 배열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: f85b0801cf013e207eacd70a256a3ed0a8dc7887
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476152"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>방법: Visual Basic에서 문자열을 문자 배열로 변환

문자열의 문자에 대 한 데이터를 포함 하는 것이 유용한 경우도 있습니다. 예를 들어 문자열을 구문 분석 하는 경우에는 문자열 내에서 해당 문자 위치에 대 한 데이터를 포함 합니다. 이 예제에서는 문자열의 메서드를 호출 하 여 문자열의 문자 배열을 가져오는 방법을 보여 줍니다 <xref:System.String.ToCharArray%2A> .  
  
## <a name="example"></a>예  

 이 예제에서는 문자열을 배열로 분할 하는 방법 `Char` 및 문자열을 `String` 유니코드 텍스트 문자 배열로 분할 하는 방법을 보여 줍니다. 이러한 구분의 이유는 유니코드 텍스트 문자를 두 개 이상의 `Char` 문자 (예: 서로게이트 쌍 또는 결합 문자 시퀀스)로 구성할 수 있기 때문입니다. 자세한 내용은 <xref:System.Globalization.TextElementEnumerator> 및 [유니코드 표준](https://www.unicode.org/standard/standard.html)을 참조 하세요.  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>예  

 문자열을 유니코드 텍스트 문자로 분할 하는 것이 더 어렵습니다. 문자열의 시각적 표현에 대 한 정보가 필요한 경우에는이 작업이 필요 합니다. 이 예제에서는 메서드를 사용 하 여 <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> 문자열을 구성 하는 유니코드 텍스트 문자에 대 한 정보를 가져옵니다.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>추가 정보

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [방법: 문자열에 있는 문자에 액세스](how-to-access-characters-in-strings.md)
- [Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환](converting-between-strings-and-other-data-types.md)
- [문자열](index.md)
