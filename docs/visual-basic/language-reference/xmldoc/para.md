---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524732"
---
# <a name="para-visual-basic"></a>\<para > (Visual Basic)
내용이 단락 형식으로 지정 되도록 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>매개 변수  
 `content`  
 단락의 텍스트입니다.  
  
## <a name="remarks"></a>주의  
 @No__t_0 태그는 [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), \<returns [>](../../../visual-basic/language-reference/xmldoc/returns.md)등의 태그 내에서 사용 하기 위한 것 이며 텍스트에 구조를 추가할 수 있습니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<para>` 태그를 사용 하 여 `UpdateRecord` 메서드의 설명 섹션을 두 단락으로 분할 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
