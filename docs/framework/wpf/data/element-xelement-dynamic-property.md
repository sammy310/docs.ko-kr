---
title: Element(XElement 동적 속성)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921187"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="ffba5-102">Element(XElement 동적 속성)</span><span class="sxs-lookup"><span data-stu-id="ffba5-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="ffba5-103">지정한 확장된 이름에 해당하는 자식 요소 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffba5-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="ffba5-104">구문</span><span class="sxs-lookup"><span data-stu-id="ffba5-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="ffba5-105">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="ffba5-105">Property value/return value</span></span>

<span data-ttu-id="ffba5-106">`XElement Item(String expandedName)` 형식의 인덱서입니다.</span><span class="sxs-lookup"><span data-stu-id="ffba5-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="ffba5-107">이 인덱서는 확장된 이름 매개 변수를 사용하여 해당하는 <xref:System.Xml.Linq.XElement>를 반환하거나, 지정된 이름을 가진 요소가 없는 경우 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ffba5-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffba5-108">주의</span><span class="sxs-lookup"><span data-stu-id="ffba5-108">Remarks</span></span>

<span data-ttu-id="ffba5-109">이 속성은 <xref:System.Xml.Linq.XContainer.Element%2A> 클래스의 <xref:System.Xml.Linq.XContainer?displayProperty=fullName> 메서드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ffba5-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffba5-110">참조</span><span class="sxs-lookup"><span data-stu-id="ffba5-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="ffba5-111">XElement 클래스 동적 속성</span><span class="sxs-lookup"><span data-stu-id="ffba5-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="ffba5-112">요소</span><span class="sxs-lookup"><span data-stu-id="ffba5-112">Elements</span></span>](elements-xelement-dynamic-property.md)
