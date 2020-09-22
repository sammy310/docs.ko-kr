---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872700"
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
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
