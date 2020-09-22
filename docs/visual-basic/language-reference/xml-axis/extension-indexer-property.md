---
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
ms.openlocfilehash: 23417cd982c2ddf06afce69d9b120ae0737fb87d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866118"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="02961-102">확장 인덱서 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02961-102">Extension Indexer Property (Visual Basic)</span></span>

<span data-ttu-id="02961-103">컬렉션의 개별 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="02961-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02961-104">구문</span><span class="sxs-lookup"><span data-stu-id="02961-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="02961-105">부분</span><span class="sxs-lookup"><span data-stu-id="02961-105">Parts</span></span>  
  
|<span data-ttu-id="02961-106">용어</span><span class="sxs-lookup"><span data-stu-id="02961-106">Term</span></span>|<span data-ttu-id="02961-107">정의</span><span class="sxs-lookup"><span data-stu-id="02961-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="02961-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="02961-108">Required.</span></span> <span data-ttu-id="02961-109">쿼리 가능한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="02961-109">A queryable collection.</span></span> <span data-ttu-id="02961-110">즉, 또는을 구현 하는 컬렉션입니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="02961-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="02961-111">(</span><span class="sxs-lookup"><span data-stu-id="02961-111">(</span></span>|<span data-ttu-id="02961-112">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="02961-112">Required.</span></span> <span data-ttu-id="02961-113">인덱서 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02961-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="02961-114">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="02961-114">Required.</span></span> <span data-ttu-id="02961-115">컬렉션 요소의 0부터 시작 하는 위치를 지정 하는 정수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="02961-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="02961-116">)</span><span class="sxs-lookup"><span data-stu-id="02961-116">)</span></span>|<span data-ttu-id="02961-117">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="02961-117">Required.</span></span> <span data-ttu-id="02961-118">인덱서 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02961-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="02961-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="02961-119">Return Value</span></span>  

 <span data-ttu-id="02961-120">컬렉션의 지정 된 위치에 있는 개체 이거나, `Nothing` 인덱스가 범위를 벗어난 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="02961-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02961-121">설명</span><span class="sxs-lookup"><span data-stu-id="02961-121">Remarks</span></span>  

 <span data-ttu-id="02961-122">확장 인덱서 속성을 사용 하 여 컬렉션의 개별 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02961-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="02961-123">이 인덱서 속성은 일반적으로 XML 축 속성의 출력에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02961-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="02961-124">XML 자식 및 XML 하위 축 속성은 <xref:System.Xml.Linq.XElement> 개체 또는 특성 값의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02961-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="02961-125">Visual Basic 컴파일러는 확장 인덱서 속성을 메서드에 대 한 호출로 변환 합니다 `ElementAtOrDefault` .</span><span class="sxs-lookup"><span data-stu-id="02961-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="02961-126">배열 인덱서와 달리 `ElementAtOrDefault` 이 메서드는 `Nothing` 인덱스가 범위를 벗어난 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02961-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="02961-127">이 동작은 컬렉션의 요소 수를 쉽게 확인할 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02961-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="02961-128">이 인덱서 속성은 또는을 구현 하는 컬렉션에 대 한 확장 속성과 같습니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> . 컬렉션에 인덱서가 나 기본 속성이 없는 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02961-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="02961-129">또는 개체 컬렉션의 첫 번째 요소 값에 액세스 하려면 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> XML 속성을 사용 하면 `Value` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02961-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="02961-130">자세한 내용은 [XML Value 속성](xml-value-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02961-130">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02961-131">예제</span><span class="sxs-lookup"><span data-stu-id="02961-131">Example</span></span>  

 <span data-ttu-id="02961-132">다음 예제에서는 확장 인덱서를 사용 하 여 개체 컬렉션의 두 번째 자식 노드에 액세스 하는 방법을 보여 줍니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="02961-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="02961-133">컬렉션은 개체의 이라는 모든 자식 요소를 가져오는 자식 축 속성을 사용 하 여 액세스 됩니다 `phone` `contact` .</span><span class="sxs-lookup"><span data-stu-id="02961-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="02961-134">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="02961-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="02961-135">참조</span><span class="sxs-lookup"><span data-stu-id="02961-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="02961-136">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="02961-136">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="02961-137">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="02961-137">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="02961-138">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="02961-138">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="02961-139">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="02961-139">XML Value Property</span></span>](xml-value-property.md)
