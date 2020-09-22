---
title: XML Attribute Axis Property
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
ms.openlocfilehash: 9eddd132b2d4dd6ffbd935a0c8c57a03a3d65435
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869444"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML 특성 축 속성(Visual Basic)

개체의 특성 값 <xref:System.Xml.Linq.XElement> 또는 개체 컬렉션의 첫 번째 요소에 대 한 액세스를 제공 합니다 <xref:System.Xml.Linq.XElement> .  
  
## <a name="syntax"></a>구문  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>부분  

 `object`  
 필수 사항입니다. <xref:System.Xml.Linq.XElement>개체 또는 개체의 컬렉션 <xref:System.Xml.Linq.XElement> 입니다.  
  
 .@  
 필수 사항입니다. 특성 축 속성의 시작을 나타냅니다.  
  
 <  
 선택 사항입니다. 가 Visual Basic의 올바른 식별자가 아닌 경우 특성 이름의 시작을 나타냅니다 `attribute` .  
  
 `attribute`  
 필수 사항입니다. [:] 형식의 액세스할 특성의 이름입니다 `prefix` `name` .  
  
|파트|Description|  
|----------|-----------------|  
|`prefix`|선택 사항입니다. 특성에 대 한 XML 네임 스페이스 접두사입니다. `Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.|  
|`name`|필수 사항입니다. 로컬 특성 이름입니다. [선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.|  
  
 \>  
 선택 사항입니다. 가 Visual Basic의 올바른 식별자가 아닌 경우 특성 이름의 끝을 나타냅니다 `attribute` .  
  
## <a name="return-value"></a>반환 값  

 의 값을 포함 하는 문자열입니다 `attribute` . 특성 이름이 없으면 `Nothing` 이 반환 됩니다.  
  
## <a name="remarks"></a>설명  

 XML 특성 축 속성을 사용 하 여 <xref:System.Xml.Linq.XElement> 개체 또는 개체 컬렉션의 첫 번째 요소에서 이름별로 특성 값에 액세스할 수 있습니다 <xref:System.Xml.Linq.XElement> . 이름으로 특성 값을 검색 하거나, @ identifier 앞에 새 이름을 지정 하 여 요소에 새 특성을 추가할 수 있습니다.  
  
 @ Identifier를 사용 하 여 XML 특성을 참조 하는 경우 특성 값이 문자열로 반환 되 고 속성을 명시적으로 지정할 필요가 없습니다 <xref:System.Xml.Linq.XAttribute.Value%2A> .  
  
 XML 특성에 대 한 명명 규칙은 Visual Basic 식별자에 대 한 명명 규칙과 다릅니다. 올바른 Visual Basic 식별자가 아닌 이름을 가진 XML 특성에 액세스 하려면 이름을 꺾쇠 괄호 ()로 묶습니다 \< and > .  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  

 특성 축 속성의 이름에는 문을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스 접두사만 사용할 수 있습니다 `Imports` . XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다. 자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `type` 라는 xml 요소의 컬렉션에서 라는 xml 특성의 값을 가져오는 방법을 보여 줍니다 `phone` .  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>예제  

 다음 예에서는 xml 요소에 대 한 특성을 XML의 일부로 선언적으로 만들고 개체의 인스턴스에 특성을 추가 하 여 동적으로 만드는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> . `type`특성이 선언적 `owner` 으로 만들어지고 특성이 동적으로 만들어집니다.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>예제  

 다음 예에서는 꺾쇠 괄호 구문을 사용 하 여 `number-type` Visual Basic에서 유효한 식별자가 아닌 이라는 XML 특성의 값을 가져옵니다.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Phone type: work`  
  
## <a name="example"></a>예제  

 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 정규화 된 이름 ""을 사용 하 여 첫 번째 자식 노드에 액세스 `ns:name` 합니다.  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Phone type: home`  
  
## <a name="see-also"></a>참조

- <xref:System.Xml.Linq.XElement>
- [XML 축 속성](index.md)
- [XML 리터럴](../xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../programming-guide/language-features/xml/creating-xml.md)
- [선언된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
