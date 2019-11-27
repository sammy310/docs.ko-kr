---
title: 확장 인덱서 속성
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352696"
---
# <a name="extension-indexer-property-visual-basic"></a>확장 인덱서 속성(Visual Basic)
컬렉션의 개별 요소에 액세스할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`object`|필수입니다. 쿼리 가능한 컬렉션입니다. 즉, <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>를 구현 하는 컬렉션입니다.|  
|(|필수입니다. 인덱서 속성의 시작을 나타냅니다.|  
|`index`|필수입니다. 컬렉션 요소의 0부터 시작 하는 위치를 지정 하는 정수 식입니다.|  
|)|필수입니다. 인덱서 속성의 끝을 나타냅니다.|  
  
## <a name="return-value"></a>반환 값  
 컬렉션의 지정 된 위치에 있는 개체 이거나, 인덱스가 범위를 벗어난 경우 `Nothing`입니다.  
  
## <a name="remarks"></a>주의  
 확장 인덱서 속성을 사용 하 여 컬렉션의 개별 요소에 액세스할 수 있습니다. 이 인덱서 속성은 일반적으로 XML 축 속성의 출력에 사용 됩니다. XML 자식 및 XML 하위 축 속성은 <xref:System.Xml.Linq.XElement> 개체 또는 특성 값의 컬렉션을 반환 합니다.  
  
 Visual Basic 컴파일러는 확장 인덱서 속성을 `ElementAtOrDefault` 메서드에 대 한 호출로 변환 합니다. 배열 인덱서와 달리 `ElementAtOrDefault` 메서드는 인덱스가 범위를 벗어난 경우 `Nothing`을 반환 합니다. 이 동작은 컬렉션의 요소 수를 쉽게 확인할 수 없는 경우에 유용 합니다.  
  
 이 인덱서 속성은 <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>를 구현 하는 컬렉션에 대 한 확장 속성과 유사 합니다. 즉, 컬렉션에 인덱서가 나 기본 속성이 없는 경우에만 사용 됩니다.  
  
 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute> 개체 컬렉션의 첫 번째 요소 값에 액세스 하려면 XML `Value` 속성을 사용 하면 됩니다. 자세한 내용은 [XML Value 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 확장 인덱서를 사용 하 여 <xref:System.Xml.Linq.XElement> 개체 컬렉션의 두 번째 자식 노드에 액세스 하는 방법을 보여 줍니다. 자식 축 속성을 사용 하 여 컬렉션에 액세스할 수 있으며,이 속성은 `contact` 개체의 `phone` 이라는 모든 자식 요소를 가져옵니다.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XElement>
- [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
