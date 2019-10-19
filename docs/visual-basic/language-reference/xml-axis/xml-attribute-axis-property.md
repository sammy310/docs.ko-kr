---
title: XML 특성 축 속성(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 896081c3dc7ca9e50b4dc4bd87675e957c34b649
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582158"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML 특성 축 속성(Visual Basic)
@No__t_0 개체의 특성 값 이나 <xref:System.Xml.Linq.XElement> 개체 컬렉션의 첫 번째 요소에 대 한 액세스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>요소  
 `object`  
 필수 요소. @No__t_0 개체 또는 <xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.  
  
 .@  
 필수 요소. 특성 축 속성의 시작을 나타냅니다.  
  
 <  
 (선택 사항) @No__t_0 Visual Basic의 올바른 식별자가 아닌 경우 특성 이름의 시작을 나타냅니다.  
  
 `attribute`  
 필수 요소. [@No__t_0:] 형식의 `name` 액세스할 특성의 이름입니다.  
  
|파트|설명|  
|----------|-----------------|  
|`prefix`|(선택 사항) 특성에 대 한 XML 네임 스페이스 접두사입니다. `Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.|  
|`name`|필수 요소. 로컬 특성 이름입니다. [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.|  
  
 \>  
 (선택 사항) @No__t_0 Visual Basic의 올바른 식별자가 아닌 경우 특성 이름의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 @No__t_0의 값을 포함 하는 문자열입니다. 특성 이름이 없으면 `Nothing` 반환 됩니다.  
  
## <a name="remarks"></a>주의  
 XML 특성 축 속성을 사용 하 여 <xref:System.Xml.Linq.XElement> 개체 또는 <xref:System.Xml.Linq.XElement> 개체 컬렉션의 첫 번째 요소에서 이름별로 특성 값에 액세스할 수 있습니다. 이름으로 특성 값을 검색 하거나, @ identifier 앞에 새 이름을 지정 하 여 요소에 새 특성을 추가할 수 있습니다.  
  
 @ Identifier를 사용 하 여 XML 특성을 참조 하는 경우 특성 값이 문자열로 반환 되 고 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 명시적으로 지정할 필요가 없습니다.  
  
 XML 특성에 대 한 명명 규칙은 Visual Basic 식별자에 대 한 명명 규칙과 다릅니다. 올바른 Visual Basic 식별자가 아닌 이름을 가진 XML 특성에 액세스 하려면 이름을 꺾쇠 괄호 (\< 및 >)로 묶습니다.  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 특성 축 속성의 이름은 `Imports` 문을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스 접두사만 사용할 수 있습니다. XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다. 자세한 내용은 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 이름이 `phone` 인 XML 요소의 컬렉션에서 `type` 이라는 XML 특성의 값을 가져오는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>예제  
 다음 예에서는 xml 요소에 대 한 특성을 XML의 일부로 선언적으로 만드는 방법과 <xref:System.Xml.Linq.XElement> 개체의 인스턴스에 특성을 추가 하 여 동적으로 만드는 방법을 보여 줍니다. @No__t_0 특성이 선언적으로 만들어지고 `owner` 특성이 동적으로 만들어집니다.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 꺾쇠 괄호 구문을 사용 하 여 Visual Basic에서 유효한 식별자가 아닌 `number-type` 이라는 XML 특성의 값을 가져옵니다.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Phone type: work`  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 정규화 된 이름 "`ns:name`"을 사용 하 여 첫 번째 자식 노드에 액세스 합니다.  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Phone type: home`  
  
## <a name="see-also"></a>참조

- <xref:System.Xml.Linq.XElement>
- [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
