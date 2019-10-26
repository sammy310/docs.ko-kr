---
title: Attribute(XElement 동적 속성)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921205"
---
# <a name="attribute-xelement-dynamic-property"></a>Attribute(XElement 동적 속성)

지정한 확장된 이름에 해당하는 특성 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.

## <a name="syntax"></a>구문

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>속성 값/반환 값

`XAttribute Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 지정된 특성의 확장된 이름을 사용하여 해당하는 <xref:System.Xml.Linq.XAttribute>를 반환하거나 지정된 이름을 가진 특성이 없는 경우 `null`을 반환합니다.

## <a name="remarks"></a>주의

이 속성은 <xref:System.Xml.Linq.XElement.Attribute%2A> 클래스의 <xref:System.Xml.Linq.XElement?displayProperty=fullName> 메서드와 동일합니다.

## <a name="see-also"></a>참조

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [XAttribute 클래스 동적 속성](attribute-xelement-dynamic-property.md)
- [Value](value-xattribute-dynamic-property.md)
