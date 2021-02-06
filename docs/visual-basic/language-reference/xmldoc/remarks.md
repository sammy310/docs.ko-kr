---
description: 다음에 대해 자세히 알아보세요. <remarks> (Visual Basic)
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 4b0584abbe85a7ecc73e25dd1f6ec321962b88a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640409"
---
# <a name="remarks-visual-basic"></a>\<remarks>(Visual Basic)

멤버의 설명 섹션을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>매개 변수  

 `description`  
 멤버에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  

 태그를 사용 `<remarks>` 하 여 형식에 대 한 정보를 추가 하 고를 사용 하 여 지정 된 정보를 보충 [\<summary>](summary.md) 합니다.  
  
 이 정보는 개체 브라우저 표시 됩니다. 개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 `<remarks>` 메서드가 수행 하는 작업을 설명 합니다 `UpdateRecord` .  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](index.md)
