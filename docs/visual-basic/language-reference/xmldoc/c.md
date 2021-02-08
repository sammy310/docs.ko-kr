---
description: '자세한 정보: <c> (Visual Basic)'
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 350a5dbf2dee2911c356a7c76a9bafbab35fd71e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787515"
---
# <a name="c-visual-basic"></a>\<c>(Visual Basic)

설명의 텍스트가 코드 임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---|---|  
|`text`|코드로 표시하려는 텍스트입니다.|  
  
## <a name="remarks"></a>설명  

 `<c>` 태그를 사용하면 설명 내의 텍스트를 코드로 표시해야 함을 지정할 수 있습니다. 여러 줄을 코드로 지정하려면 [\<code>](code.md)를 사용합니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 `<c>` 요약 섹션의 태그를 사용 하 여가 code 임을 표시 합니다 `Counter` .  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](index.md)
