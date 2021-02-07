---
description: 다음에 대해 자세히 알아보세요. <para> (Visual Basic)
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 51dd9ff300d980b4c0576566cad5d17375889ba1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740771"
---
# <a name="para-visual-basic"></a>\<para>(Visual Basic)

내용이 단락 형식으로 지정 되도록 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>매개 변수  

 `content`  
 단락의 텍스트입니다.  
  
## <a name="remarks"></a>설명  

 `<para>` 태그는 [\<summary>](summary.md), [\<remarks>](remarks.md) 또는 [\<returns>](returns.md) 같은 태그 내에 사용되어 텍스트에 구조를 추가할 수 있게 합니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 `<para>` 하 여 메서드의 설명 섹션을 `UpdateRecord` 두 단락으로 분할 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](index.md)
