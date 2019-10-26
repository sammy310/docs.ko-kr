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
# <a name="descendants-xelement-dynamic-property"></a><span data-ttu-id="b3bb5-102">Descendants(XElement 동적 속성)</span><span class="sxs-lookup"><span data-stu-id="b3bb5-102">Descendants (XElement dynamic property)</span></span>

<span data-ttu-id="b3bb5-103">지정한 확장된 이름과 일치하는 현재 요소의 하위 요소를 모두 검색하는 데 사용되는 인덱서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3bb5-103">Gets an indexer used to retrieve all the descendant elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3bb5-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3bb5-104">Syntax</span></span>

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="b3bb5-105">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="b3bb5-105">Property value/return value</span></span>

<span data-ttu-id="b3bb5-106">`IEnumerable<XElement> Item(String expandedName)` 형식의 인덱서입니다.</span><span class="sxs-lookup"><span data-stu-id="b3bb5-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="b3bb5-107">이 인덱서는 지정된 하위 요소의 확장된 이름을 사용하여 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 컬렉션에서 일치하는 자식 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bb5-107">This indexer takes the expanded name of the specified descendant elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3bb5-108">주의</span><span class="sxs-lookup"><span data-stu-id="b3bb5-108">Remarks</span></span>

<span data-ttu-id="b3bb5-109">이 속성은 <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XContainer> 메서드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bb5-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="b3bb5-110">반환된 컬렉션의 요소는 XML 소스 문서 순서로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3bb5-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="b3bb5-111">이 속성은 지연된 실행을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3bb5-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3bb5-112">참조</span><span class="sxs-lookup"><span data-stu-id="b3bb5-112">See also</span></span>

- [<span data-ttu-id="b3bb5-113">XElement 클래스 동적 속성</span><span class="sxs-lookup"><span data-stu-id="b3bb5-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="b3bb5-114">요소</span><span class="sxs-lookup"><span data-stu-id="b3bb5-114">Elements</span></span>](elements-xelement-dynamic-property.md)
