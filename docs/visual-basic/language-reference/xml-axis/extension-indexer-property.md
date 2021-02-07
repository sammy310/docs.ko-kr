---
description: '자세한 정보: 확장 인덱서 속성 (Visual Basic)'
title: 확장명 인덱서 속성
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: ec165836f739db9a74ea266ebba32be5bb42cca6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700327"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="946ba-103">확장 인덱서 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="946ba-103">Extension Indexer Property (Visual Basic)</span></span>

<span data-ttu-id="946ba-104">컬렉션의 개별 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-104">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="946ba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="946ba-105">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="946ba-106">부분</span><span class="sxs-lookup"><span data-stu-id="946ba-106">Parts</span></span>  
  
|<span data-ttu-id="946ba-107">용어</span><span class="sxs-lookup"><span data-stu-id="946ba-107">Term</span></span>|<span data-ttu-id="946ba-108">정의</span><span class="sxs-lookup"><span data-stu-id="946ba-108">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="946ba-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="946ba-109">Required.</span></span> <span data-ttu-id="946ba-110">쿼리 가능한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-110">A queryable collection.</span></span> <span data-ttu-id="946ba-111">즉, 또는을 구현 하는 컬렉션입니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="946ba-111">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="946ba-112">(</span><span class="sxs-lookup"><span data-stu-id="946ba-112">(</span></span>|<span data-ttu-id="946ba-113">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-113">Required.</span></span> <span data-ttu-id="946ba-114">인덱서 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-114">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="946ba-115">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-115">Required.</span></span> <span data-ttu-id="946ba-116">컬렉션 요소의 0부터 시작 하는 위치를 지정 하는 정수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-116">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="946ba-117">)</span><span class="sxs-lookup"><span data-stu-id="946ba-117">)</span></span>|<span data-ttu-id="946ba-118">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-118">Required.</span></span> <span data-ttu-id="946ba-119">인덱서 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-119">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="946ba-120">Return Value</span><span class="sxs-lookup"><span data-stu-id="946ba-120">Return Value</span></span>  

 <span data-ttu-id="946ba-121">컬렉션의 지정 된 위치에 있는 개체 이거나, `Nothing` 인덱스가 범위를 벗어난 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-121">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="946ba-122">설명</span><span class="sxs-lookup"><span data-stu-id="946ba-122">Remarks</span></span>  

 <span data-ttu-id="946ba-123">확장 인덱서 속성을 사용 하 여 컬렉션의 개별 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-123">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="946ba-124">이 인덱서 속성은 일반적으로 XML 축 속성의 출력에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-124">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="946ba-125">XML 자식 및 XML 하위 축 속성은 <xref:System.Xml.Linq.XElement> 개체 또는 특성 값의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-125">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="946ba-126">Visual Basic 컴파일러는 확장 인덱서 속성을 메서드에 대 한 호출로 변환 합니다 `ElementAtOrDefault` .</span><span class="sxs-lookup"><span data-stu-id="946ba-126">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="946ba-127">배열 인덱서와 달리 `ElementAtOrDefault` 이 메서드는 `Nothing` 인덱스가 범위를 벗어난 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-127">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="946ba-128">이 동작은 컬렉션의 요소 수를 쉽게 확인할 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-128">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="946ba-129">이 인덱서 속성은 또는을 구현 하는 컬렉션에 대 한 확장 속성과 같습니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> . 컬렉션에 인덱서가 나 기본 속성이 없는 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-129">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="946ba-130">또는 개체 컬렉션의 첫 번째 요소 값에 액세스 하려면 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> XML 속성을 사용 하면 `Value` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-130">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="946ba-131">자세한 내용은 [XML Value 속성](xml-value-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="946ba-131">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="946ba-132">예제</span><span class="sxs-lookup"><span data-stu-id="946ba-132">Example</span></span>  

 <span data-ttu-id="946ba-133">다음 예제에서는 확장 인덱서를 사용 하 여 개체 컬렉션의 두 번째 자식 노드에 액세스 하는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="946ba-133">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="946ba-134">컬렉션은 개체의 이라는 모든 자식 요소를 가져오는 자식 축 속성을 사용 하 여 액세스 됩니다 `phone` `contact` .</span><span class="sxs-lookup"><span data-stu-id="946ba-134">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="946ba-135">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="946ba-135">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="946ba-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="946ba-136">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="946ba-137">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="946ba-137">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="946ba-138">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="946ba-138">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="946ba-139">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="946ba-139">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="946ba-140">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="946ba-140">XML Value Property</span></span>](xml-value-property.md)
