---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524688"
---
# <a name="returns-visual-basic"></a>\<returns > (Visual Basic)
속성 또는 함수의 반환 값을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>매개 변수  
 `description`  
 반환 값에 대한 설명입니다.  
  
## <a name="remarks"></a>주의  
 메서드 선언의 주석에서 `<returns>` 태그를 사용 하 여 반환 값을 설명 합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예에서는 `<returns>` 태그를 사용 하 여 `DoesRecordExist` 함수가 반환 하는 항목을 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
