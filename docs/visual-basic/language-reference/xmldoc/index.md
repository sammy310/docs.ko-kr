---
title: 문서 주석에 대한 권장 XML 태그(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
  - vb.XmlDocComment
helpviewer_keywords:
  - 'tags, XML'
  - 'XML comments, recommended tags [Visual Basic]'
  - 'comments, recommended XML tags'
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>문서 주석에 대한 권장 XML 태그(Visual Basic)
Visual Basic 컴파일러는 XML 파일에 코드에서 문서 주석을 처리할 수 있습니다. 설명서에 XML 파일을 처리 하는 데 추가 도구를 사용할 수 있습니다.  
  
 XML 주석 형식 등의 코드 구문에는 사용할 수 및 멤버를 입력 합니다. 부분 형식에 대 한 형식의 파트가 하나만 포함할 수 XML 주석, 있지만 해당 멤버의 주석 처리에 대 한 제한은 없습니다.  
  
> [!NOTE]
>  네임 스페이스에 문서 주석은 적용할 수 없습니다. 이유는 하나의 네임 스페이스에는 여러 어셈블리에 걸쳐 있을 수 있으며 일부 어셈블리를 동시에 로드할 필요가입니다.  
  
 컴파일러는 유효한 XML 태그를 모두 처리 합니다. 다음 태그가 사용자 설명서에서 자주 사용 되는 기능을 제공 합니다.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> 컴파일러에서 구문을 확인 합니다.)  
  
> [!NOTE]
>  문서 주석의 텍스트에 꺾쇠 괄호를 하려는 경우 사용할 `&lt;` 고 `&gt;`입니다. 예를 들어, 문자열 `"&lt;text in angle brackets&gt;"` 으로 표시 됩니다 `<text in angle brackets>`합니다.  
  
## <a name="see-also"></a>참고자료

- [코드를 XML로 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
