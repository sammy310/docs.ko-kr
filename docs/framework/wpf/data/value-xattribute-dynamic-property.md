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
# <a name="value-xattribute-dynamic-property"></a><span data-ttu-id="8e2e4-102">Value(XAttribute 동적 속성)</span><span class="sxs-lookup"><span data-stu-id="8e2e4-102">Value (XAttribute dynamic property)</span></span>

<span data-ttu-id="8e2e4-103">XML 특성의 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2e4-103">Gets or sets the value of the XML attribute.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e2e4-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e2e4-104">Syntax</span></span>

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="8e2e4-105">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="8e2e4-105">Property value/return value</span></span>

<span data-ttu-id="8e2e4-106">이 특성의 값이 들어 있는 <xref:System.String>입니다.</span><span class="sxs-lookup"><span data-stu-id="8e2e4-106">A <xref:System.String> containing the value of this attribute.</span></span>

## <a name="exceptions"></a><span data-ttu-id="8e2e4-107">예외</span><span class="sxs-lookup"><span data-stu-id="8e2e4-107">Exceptions</span></span>

|<span data-ttu-id="8e2e4-108">예외 형식</span><span class="sxs-lookup"><span data-stu-id="8e2e4-108">Exception type</span></span>|<span data-ttu-id="8e2e4-109">조건</span><span class="sxs-lookup"><span data-stu-id="8e2e4-109">Condition</span></span>|
| - |---------------|
|<xref:System.ArgumentNullException>|<span data-ttu-id="8e2e4-110">설정 시 `value`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="8e2e4-110">When setting, the `value` is `null`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8e2e4-111">주의</span><span class="sxs-lookup"><span data-stu-id="8e2e4-111">Remarks</span></span>

<span data-ttu-id="8e2e4-112">이 속성은 <xref:System.Xml.Linq.XAttribute.Value%2A> 클래스의 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 속성과 동일하지만 이 동적 속성은 변경 알림도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2e4-112">This property is equivalent to the <xref:System.Xml.Linq.XAttribute.Value%2A> property of the <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> class, but this dynamic property also supports change notifications.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e2e4-113">참조</span><span class="sxs-lookup"><span data-stu-id="8e2e4-113">See also</span></span>

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [<span data-ttu-id="8e2e4-114">XAttribute 클래스 동적 속성</span><span class="sxs-lookup"><span data-stu-id="8e2e4-114">XAttribute class dynamic properties</span></span>](value-xattribute-dynamic-property.md)
- [<span data-ttu-id="8e2e4-115">특성</span><span class="sxs-lookup"><span data-stu-id="8e2e4-115">Attribute</span></span>](attribute-xelement-dynamic-property.md)
