---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873033"
---
# <a name="code-visual-basic"></a>\<code>(Visual Basic)

텍스트가 여러 줄의 코드 임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>매개 변수  

 `content`  
 코드로 표시할 텍스트입니다.  
  
## <a name="remarks"></a>설명  

 태그를 사용 `<code>` 하 여 여러 줄을 코드로 표시 합니다. [\<c>](c.md)설명 내의 텍스트를 코드로 표시 해야 함을 나타내는 데 사용 합니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 \<code> 필드를 사용 하는 예제 코드를 포함 합니다 `ID` .  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
