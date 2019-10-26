---
title: Descendants(XElement 동적 속성)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 8d14b0a94d1a2028a56f649a574f157264ba50fa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921181"
---
# <a name="descendants-xelement-dynamic-property"></a>Descendants(XElement 동적 속성)

지정한 확장된 이름과 일치하는 현재 요소의 하위 요소를 모두 검색하는 데 사용되는 인덱서를 가져옵니다.

## <a name="syntax"></a>구문

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>속성 값/반환 값

`IEnumerable<XElement> Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 지정된 하위 요소의 확장된 이름을 사용하여 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 컬렉션에서 일치하는 자식 요소를 반환합니다.

## <a name="remarks"></a>주의

이 속성은 <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XContainer> 메서드와 동일합니다.

반환된 컬렉션의 요소는 XML 소스 문서 순서로 되어 있습니다.

이 속성은 지연된 실행을 사용합니다.

## <a name="see-also"></a>참조

- [XElement 클래스 동적 속성](attribute-xelement-dynamic-property.md)
- [요소](elements-xelement-dynamic-property.md)
