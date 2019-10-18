---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524613"
---
# <a name="value-visual-basic"></a>\<value > (Visual Basic)
속성에 대 한 설명을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>매개 변수  
 `property-description`  
 속성에 대한 설명입니다.  
  
## <a name="remarks"></a>주의  
 @No__t_0 태그를 사용 하 여 속성을 설명 합니다. Visual Studio 개발 환경에서 코드 마법사를 사용 하 여 속성을 추가 하는 경우 새 속성에 대 한 [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) 태그를 추가 합니다. 그런 다음 속성이 나타내는 값을 설명 하는 `<value>` 태그를 수동으로 추가 해야 합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<value>` 태그를 사용 하 여 `Counter` 속성에 포함 된 값을 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
