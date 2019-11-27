---
title: <list>
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: db5c571d2f2c59419c886f6596f4e4dbd30d7baf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352319"
---
# <a name="list-visual-basic"></a>\<목록 > (Visual Basic)
목록 또는 테이블을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
## <a name="parameters"></a>매개 변수  
 `type`  
 목록의 유형입니다. 글머리 기호 목록에 대 한 "글머리 기호", 숫자 목록의 경우 "숫자" 또는 두 열 테이블의 경우 "table" 이어야 합니다.  
  
 `term`  
 `type` "table" 인 경우에만 사용 됩니다. 정의 하는 용어로 설명 태그에 정의 되어 있습니다.  
  
 `description`  
 `type` "글머리 기호" 또는 "숫자" 인 경우 `type`가 "table" 인 경우 `description`은 목록에 있는 항목이 며 `term`에 대 한 정의 `description`입니다.  
  
## <a name="remarks"></a>설명  
 `<listheader>` 블록은 테이블 또는 정의 목록의 머리글을 정의 합니다. 테이블을 정의할 때 제목에 `term`에 대 한 항목만 제공 하면 됩니다.  
  
 목록의 각 항목은 `<item>` 블록을 사용 하 여 지정 됩니다. 정의 목록을 만들 때 `term`와 `description`를 모두 지정 해야 합니다. 그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우에는 `description`에 대 한 항목만 제공 하면 됩니다.  
  
 목록 또는 테이블에는 필요한 만큼의 `<item>` 블록이 있을 수 있습니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<list>` 태그를 사용 하 여 설명 섹션에서 글머리 기호 목록을 정의 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>참고자료

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
