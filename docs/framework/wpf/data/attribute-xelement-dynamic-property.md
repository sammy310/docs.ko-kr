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
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="68e71-102">Attribute(XElement 동적 속성)</span><span class="sxs-lookup"><span data-stu-id="68e71-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="68e71-103">지정한 확장된 이름에 해당하는 특성 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68e71-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="68e71-104">구문</span><span class="sxs-lookup"><span data-stu-id="68e71-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="68e71-105">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="68e71-105">Property value/return value</span></span>

<span data-ttu-id="68e71-106">`XAttribute Item(String expandedName)` 형식의 인덱서입니다.</span><span class="sxs-lookup"><span data-stu-id="68e71-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="68e71-107">이 인덱서는 지정된 특성의 확장된 이름을 사용하여 해당하는 <xref:System.Xml.Linq.XAttribute>를 반환하거나 지정된 이름을 가진 특성이 없는 경우 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="68e71-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="68e71-108">주의</span><span class="sxs-lookup"><span data-stu-id="68e71-108">Remarks</span></span>

<span data-ttu-id="68e71-109">이 속성은 <xref:System.Xml.Linq.XElement.Attribute%2A> 클래스의 <xref:System.Xml.Linq.XElement?displayProperty=fullName> 메서드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="68e71-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="68e71-110">참조</span><span class="sxs-lookup"><span data-stu-id="68e71-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="68e71-111">XAttribute 클래스 동적 속성</span><span class="sxs-lookup"><span data-stu-id="68e71-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="68e71-112">Value</span><span class="sxs-lookup"><span data-stu-id="68e71-112">Value</span></span>](value-xattribute-dynamic-property.md)
