---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: dbd99997fed33c192a2160fb45a739addbae254a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524615"
---
# <a name="typeparam-visual-basic"></a>\<typeparam > (Visual Basic)
형식 매개 변수 이름 및 설명을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>매개 변수  
 `name`  
 형식 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.  
  
 `description`  
 형식 매개 변수에 대 한 설명입니다.  
  
## <a name="remarks"></a>주의  
 제네릭 형식 또는 제네릭 멤버 선언에 대 한 주석에서 `<typeparam>` 태그를 사용 하 여 형식 매개 변수 중 하나를 설명 합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<typeparam>` 태그를 사용 하 여 `id` 매개 변수를 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
