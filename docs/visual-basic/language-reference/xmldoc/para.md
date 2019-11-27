---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352309"
---
# <a name="para-visual-basic"></a>\<단락 > (Visual Basic)
내용이 단락 형식으로 지정 되도록 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>매개 변수  
 `content`  
 단락의 텍스트입니다.  
  
## <a name="remarks"></a>주의  
 `<para>` 태그는 [\<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<](../../../visual-basic/language-reference/xmldoc/remarks.md)>\<[반환](../../../visual-basic/language-reference/xmldoc/returns.md)하는 태그 내에서 사용 하기 위한 것 이며 텍스트에 구조를 추가할 수 있습니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<para>` 태그를 사용 하 여 `UpdateRecord` 메서드의 설명 섹션을 두 단락으로 분할 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
