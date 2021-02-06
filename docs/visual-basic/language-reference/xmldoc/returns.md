---
description: 다음에 대해 자세히 알아보세요. <returns> (Visual Basic)
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: ba5f1e231502a67e86ffbb92cf8868c3aecb05d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640383"
---
# <a name="returns-visual-basic"></a>\<returns>(Visual Basic)

속성 또는 함수의 반환 값을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>매개 변수  

 `description`  
 반환 값에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  

 `<returns>`메서드의 태그를 사용 하 여 반환 값을 설명 합니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 `<returns>` 함수가 반환 하는 항목을 설명 `DoesRecordExist` 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
