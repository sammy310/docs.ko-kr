---
title: <paramref>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 85171bd8deeb5f54c4560bb8b2339107bb8d8c68
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524715"
---
# <a name="paramref-visual-basic"></a>\<paramref > (Visual Basic)
단어를 매개 변수로 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a>매개 변수  
 `name`  
 참조할 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.  
  
## <a name="remarks"></a>주의  
 @No__t_0 태그는 단어가 매개 변수 임을 나타내는 방법을 제공 합니다. XML 파일을 처리 하 여이 매개 변수를 일종의 형식으로 지정할 수 있습니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<paramref>` 태그를 사용 하 여 `id` 매개 변수를 참조 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
