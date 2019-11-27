---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 1cbac2162bd39cdc8af9a55dfd6e2f90bc40b08a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354319"
---
# <a name="code-visual-basic"></a>\<코드 > (Visual Basic)
텍스트가 여러 줄의 코드 임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>매개 변수  
 `content`  
 코드로 표시할 텍스트입니다.  
  
## <a name="remarks"></a>설명  
 `<code>` 태그를 사용 하 여 여러 줄을 코드로 표시 합니다. 설명 내의 텍스트가 코드로 표시되도록 지정하려면 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md)를 사용합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 \<code > 태그를 사용 하 여 `ID` 필드 사용에 대 한 예제 코드를 포함 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>참고자료

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
