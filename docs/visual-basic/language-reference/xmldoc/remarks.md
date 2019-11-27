---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352255"
---
# <a name="remarks-visual-basic"></a>\<설명 > (Visual Basic)
멤버의 설명 섹션을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>매개 변수  
 `description`  
 멤버에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 `<remarks>` 태그를 사용 하 여 형식에 대 한 정보를 추가 하 고 [\<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md)지정 된 정보를 보충 합니다.  
  
 이 정보는 개체 브라우저 표시 됩니다. 개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<remarks>` 태그를 사용 하 여 `UpdateRecord` 메서드가 수행 하는 작업을 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고자료

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
