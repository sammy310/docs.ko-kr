---
description: '자세히 알아보기: XML Value 속성 (Visual Basic)'
title: XML 값 속성
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 49762c1fcc0059472a5be11726aa344a001807ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768768"
---
# <a name="xml-value-property-visual-basic"></a>XML Value 속성(Visual Basic)

개체 컬렉션의 첫 번째 요소 값에 대 한 액세스를 제공 <xref:System.Xml.Linq.XElement> 합니다.

## <a name="syntax"></a>Syntax

```vb
object.Value
```

## <a name="parts"></a>부분

|용어|정의|  
|---|---|  
|`object`|필수 요소. <xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.|  

## <a name="return-value"></a>Return Value

 `String`컬렉션의 첫 번째 요소 값을 포함 하는 이거나, `Nothing` 컬렉션이 비어 있는 경우입니다.

## <a name="remarks"></a>설명

 <xref:System.Xml.Linq.XElement.Value%2A>속성을 사용 하면 개체 컬렉션의 첫 번째 요소 값에 쉽게 액세스할 수 <xref:System.Xml.Linq.XElement> 있습니다. 이 속성은 먼저 컬렉션에 하나 이상의 개체가 포함 되어 있는지 여부를 확인 합니다. 컬렉션이 비어 있으면이 속성은를 반환 `Nothing` 합니다. 그렇지 않으면이 속성은 <xref:System.Xml.Linq.XElement.Value%2A> 컬렉션에 있는 첫 번째 요소의 속성 값을 반환 합니다.

> [!NOTE]
> ' ' 식별자를 사용 하 여 XML 특성의 값에 액세스 하는 경우 \@ 특성 값이로 반환 되 `String` 고 속성을 명시적으로 지정할 필요가 없습니다 <xref:System.Xml.Linq.XAttribute.Value%2A> .

 컬렉션의 다른 요소에 액세스 하려면 XML 확장 인덱서 속성을 사용 하면 됩니다. 자세한 내용은 [확장 인덱서 속성](extension-indexer-property.md)을 참조 하세요.

## <a name="inheritance"></a>상속

 대부분의 사용자는를 구현할 필요가 없으므로 <xref:System.Collections.Generic.IEnumerable%601> 이 섹션을 무시할 수 있습니다.

 속성은을 <xref:System.Xml.Linq.XElement.Value%2A> 구현 하는 형식에 대 한 확장 속성입니다 `IEnumerable(Of XElement)` . 이 확장 속성의 바인딩은 확장 메서드의 바인딩과 유사 합니다. 형식이 인터페이스 중 하나를 구현 하 고 이름이 "Value" 인 속성을 정의 하는 경우 해당 속성은 확장 속성 보다 우선 합니다. 즉,을 <xref:System.Xml.Linq.XElement.Value%2A> 구현 하는 클래스에서 새 속성을 정의 하 여이 속성을 재정의할 수 있습니다 `IEnumerable(Of XElement)` .

## <a name="example"></a>예제

 다음 예제에서는 속성을 사용 하 여 <xref:System.Xml.Linq.XElement.Value%2A> 개체 컬렉션의 첫 번째 노드에 액세스 하는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> . 이 예제에서는 자식 축 속성을 사용 하 여 개체에 있는 라는 모든 자식 노드의 컬렉션을 가져옵니다 `phone` `contact` .

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 이 코드의 텍스트는 다음과 같습니다.

 `Phone number: 206-555-0144`

## <a name="example"></a>예제

 다음 예제에서는 개체의 컬렉션에서 XML 특성의 값을 가져오는 방법을 보여 줍니다 <xref:System.Xml.Linq.XAttribute> . 이 예에서는 특성 축 속성을 사용 하 여 `type` 모든 요소에 대 한 특성 값을 표시 합니다 `phone` .

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 이 코드의 텍스트는 다음과 같습니다.

 ```console
 home
 work
```

## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [XML 축 속성](index.md)
- [XML 리터럴](../xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../programming-guide/language-features/xml/creating-xml.md)
- [확장명 메서드](../../programming-guide/language-features/procedures/extension-methods.md)
- [확장명 인덱서 속성](extension-indexer-property.md)
- [XML Child Axis Property](xml-child-axis-property.md)
- [XML Attribute Axis Property](xml-attribute-axis-property.md)
