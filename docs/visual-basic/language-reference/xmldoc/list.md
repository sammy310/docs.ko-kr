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
ms.openlocfilehash: 900cd8c467a21812d980cffa7e41120ae557704b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872780"
---
# <a name="list-visual-basic"></a>\<list>(Visual Basic)

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
 `type`가 "table" 인 경우에만 사용 됩니다. 정의 하는 용어로 설명 태그에 정의 되어 있습니다.  
  
 `description`  
 `type`가 "bullet" 또는 "number" 인 경우가 `description` "table" 이면 `type` `description` 의 정의입니다 `term` .  
  
## <a name="remarks"></a>설명  

 `<listheader>`블록은 테이블 또는 정의 목록의 머리글을 정의 합니다. 테이블을 정의할 때 제목에에 대 한 항목만 제공 하면 `term` 됩니다.  
  
 목록의 각 항목은 `<item>` 블록을 사용하여 지정됩니다. 정의 목록을 만들 때 및를 모두 지정 해야 합니다 `term` `description` . 그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우에는에 대 한 항목만 제공 하면 `description` 됩니다.  
  
 목록 또는 테이블에 `<item>` 블록을 필요한 개수만큼 포함할 수 있습니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 `<list>` 설명 섹션에서 글머리 기호 목록을 정의 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
