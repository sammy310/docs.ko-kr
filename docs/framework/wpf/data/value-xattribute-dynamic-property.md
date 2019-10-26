---
title: Value(XAttribute 동적 속성)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.openlocfilehash: 32c15a89a976b5f9af12f040c43e724a25357ead
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920977"
---
# <a name="value-xattribute-dynamic-property"></a>Value(XAttribute 동적 속성)

XML 특성의 값을 가져오거나 설정합니다.

## <a name="syntax"></a>구문

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>속성 값/반환 값

이 특성의 값이 들어 있는 <xref:System.String>입니다.

## <a name="exceptions"></a>예외

|예외 형식|조건|
| - |---------------|
|<xref:System.ArgumentNullException>|설정 시 `value`가 `null`인 경우|

## <a name="remarks"></a>주의

이 속성은 <xref:System.Xml.Linq.XAttribute.Value%2A> 클래스의 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 속성과 동일하지만 이 동적 속성은 변경 알림도 지원합니다.

## <a name="see-also"></a>참조

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [XAttribute 클래스 동적 속성](value-xattribute-dynamic-property.md)
- [특성](attribute-xelement-dynamic-property.md)
