---
description: 자세한 내용은 문서 주석에 대 한 권장 XML 태그 (Visual Basic)를 참조 하세요.
title: 문서 주석에 대 한 권장 XML 태그
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 5d3451d98b66817de143cfbddbcb6121de57ca8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787450"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>문서 주석에 대한 권장 XML 태그(Visual Basic)

Visual Basic 컴파일러는 코드의 문서 주석을 XML 파일로 처리할 수 있습니다. 추가 도구를 사용 하 여 XML 파일을 문서로 처리할 수 있습니다.  
  
 형식 및 형식 멤버와 같은 코드 구문에서 XML 주석을 사용할 수 있습니다. 부분 형식의 경우 해당 멤버를 주석으로 처리 하는 데 제한이 없더라도 형식의 한 부분 에서만 XML 주석을 사용할 수 있습니다.  
  
> [!NOTE]
> 네임 스페이스에는 문서 주석을 적용할 수 없습니다. 그 이유는 한 네임 스페이스가 여러 어셈블리에 걸쳐 있을 수 있고 모든 어셈블리를 동시에 로드 해야 하는 것이 아니라는 것입니다.  
  
 컴파일러는 유효한 XML 인 모든 태그를 처리 합니다. 다음 태그는 사용자 설명서에서 일반적으로 사용 되는 기능을 제공 합니다.  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|[\<exception>](exception.md)<sup>1</sup>|[\<include>](include.md)<sup>1</sup>|[\<list>](list.md)|  
|[\<para>](para.md)|[\<param>](param.md)<sup>1</sup>|[\<paramref>](paramref.md)|  
|[\<permission>](permission.md)<sup>1</sup>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|[\<see>](see.md)<sup>1</sup>|[\<seealso>](seealso.md)<sup>1</sup>|[\<summary>](summary.md)|  
|[\<typeparam>](typeparam.md)<sup>1</sup>|[\<value>](value.md)||  
  
 (<sup>1</sup> 컴파일러는 구문을 확인 합니다.)  
  
> [!NOTE]
> 문서 주석 텍스트에 꺾쇠 괄호가 표시 되도록 하려면 및를 사용 `&lt;` `&gt;` 합니다. 예를 들어 문자열은 `"&lt;text in angle brackets&gt;"` 로 표시 됩니다 `<text in angle brackets>` .  
  
## <a name="see-also"></a>참조

- [코드를 XML로 문서화](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [-doc](../../reference/command-line-compiler/doc.md)
- [방법: XML 설명서 만들기](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
