---
title: <c>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523932"
---
# <a name="c-visual-basic"></a>\<c > (Visual Basic)
설명의 텍스트가 코드 임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---|---|  
|`text`|코드로 표시하려는 텍스트입니다.|  
  
## <a name="remarks"></a>주의  
 @No__t_0 태그는 설명 내의 텍스트를 코드로 표시 하도록 지정 하는 방법을 제공 합니다. 여러 줄을 코드로 지정하려면 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 요약 섹션의 `<c>` 태그를 사용 하 여 `Counter` 코드 임을 표시 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
