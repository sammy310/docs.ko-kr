---
description: '자세한 정보: 방법: XML 리터럴 수정 (Visual Basic)'
title: '방법: XML 리터럴 수정'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 23b900c3da5864ac7a91e6c7a43f44a0d4ab1a21
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483614"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="d6bf1-103">방법: XML 리터럴 수정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6bf1-103">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="d6bf1-104">Visual Basic은 XML 리터럴을 수정할 수 있는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-104">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="d6bf1-105">요소와 특성을 추가 하거나 삭제할 수 있으며 기존 요소를 새 XML 요소로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-105">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="d6bf1-106">이 항목에서는 기존 XML 리터럴을 수정 하는 방법에 대 한 몇 가지 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-106">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="d6bf1-107">XML 리터럴의 값을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d6bf1-107">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="d6bf1-108">XML 리터럴의 값을 수정 하려면 XML 리터럴에 대 한 참조를 가져오고 `Value` 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-108">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="d6bf1-109">다음 코드 예제에서는 \<Price> XML 문서에 있는 모든 요소의 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-109">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="d6bf1-110">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-110">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="d6bf1-111">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-111">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="d6bf1-112">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-112">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>47.20</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>48.25</Price>
      </Book>
    </Catalog>
    ```

    > [!NOTE]
    > <span data-ttu-id="d6bf1-113">`Value`속성은 컬렉션의 첫 번째 XML 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-113">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="d6bf1-114">컬렉션에 이름이 같은 요소가 둘 이상 있는 경우 속성을 설정 하면 `Value` 컬렉션의 첫 번째 요소에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-114">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="d6bf1-115">XML 리터럴에 특성을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="d6bf1-115">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="d6bf1-116">XML 리터럴에 특성을 추가 하려면 먼저 XML 리터럴에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-116">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="d6bf1-117">그런 다음 새 XML 특성 축 속성을 추가 하 여 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-117">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="d6bf1-118"><xref:System.Xml.Linq.XAttribute>메서드를 사용 하 여 새 개체를 XML 리터럴에 추가할 수도 있습니다 <xref:System.Xml.Linq.XContainer.Add%2A> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-118">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="d6bf1-119">다음 예에서는 두 옵션을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-119">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="d6bf1-120">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-120">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="d6bf1-121">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-121">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="d6bf1-122">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-122">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="d6bf1-123">XML 특성 축 속성에 대 한 자세한 내용은 [Xml 특성 축 속성](../../../language-reference/xml-axis/xml-attribute-axis-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-123">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="d6bf1-124">XML 리터럴에 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="d6bf1-124">To add an element to an XML literal</span></span>

1. <span data-ttu-id="d6bf1-125">XML 리터럴에 요소를 추가 하려면 먼저 XML 리터럴에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-125">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="d6bf1-126">그런 다음 <xref:System.Xml.Linq.XElement> 메서드를 사용 하 여 새 개체를 요소의 마지막 하위 요소로 추가할 수 있습니다 <xref:System.Xml.Linq.XContainer.Add%2A> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-126">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="d6bf1-127"><xref:System.Xml.Linq.XElement>메서드를 사용 하 여 새 개체를 첫 번째 하위 요소로 추가할 수 있습니다 <xref:System.Xml.Linq.XContainer.AddFirst%2A> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-127">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="d6bf1-128">다른 하위 요소를 기준으로 특정 위치에 새 요소를 추가 하려면 먼저 인접 하위 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-128">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="d6bf1-129">그런 다음 <xref:System.Xml.Linq.XElement> 메서드를 사용 하 여 인접 한 하위 요소 앞에 새 개체를 추가할 수 있습니다 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-129">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="d6bf1-130"><xref:System.Xml.Linq.XElement>메서드를 사용 하 여 인접 한 하위 요소 뒤에 새 개체를 추가할 수도 있습니다 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-130">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="d6bf1-131">다음 예제에서는 이러한 각 기술에 대 한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-131">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="d6bf1-132">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-132">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="d6bf1-133">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-133">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="d6bf1-134">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-134">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331">
        <Publisher>Microsoft Press</Publisher>
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <PublishDate>2005-2-14</PublishDate>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="d6bf1-135">XML 리터럴에서 요소나 특성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d6bf1-135">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="d6bf1-136">XML 리터럴에서 요소나 특성을 제거 하려면 다음 예제와 같이 요소나 특성에 대 한 참조를 가져오고 메서드를 호출 `Remove` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-136">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="d6bf1-137">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-137">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="d6bf1-138">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-138">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

    <span data-ttu-id="d6bf1-139">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-139">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book></Catalog>
    ```

    <span data-ttu-id="d6bf1-140">XML 리터럴에서 모든 요소나 특성을 제거 하려면 XML 리터럴에 대 한 참조를 가져오고 메서드를 호출 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-140">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="d6bf1-141">XML 리터럴을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d6bf1-141">To modify an XML literal</span></span>

1. <span data-ttu-id="d6bf1-142">XML 요소의 이름을 변경 하려면 먼저 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-142">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="d6bf1-143">그런 다음 새 <xref:System.Xml.Linq.XElement> 이름을 포함 하는 새 개체를 만들고 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 기존 개체의 메서드에 새 개체를 전달할 수 있습니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-143">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="d6bf1-144">바꾸려는 요소에 유지 해야 하는 하위 요소가 있으면 새 개체의 값을 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XContainer.Nodes%2A> 기존 요소의 속성으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-144">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="d6bf1-145">그러면 새 요소의 값이 기존 요소의 내부 XML로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-145">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="d6bf1-146">그렇지 않으면 새 요소의 값을 기존 요소의 속성으로 설정할 수 있습니다 `Value` .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-146">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="d6bf1-147">다음 코드 예제에서는 \<Description> 요소를 사용 하 여 모든 요소를 바꿉니다 \<Abstract> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-147">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="d6bf1-148">요소의 콘텐츠는 \<Description> \<Abstract> <xref:System.Xml.Linq.XContainer.Nodes%2A> 개체의 속성을 사용 하 여 새 요소에서 유지 됩니다 \<Description> <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="d6bf1-148">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="d6bf1-149">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6bf1-149">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="d6bf1-150">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-150">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
        <Description>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Description>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <Description>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Description>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="d6bf1-151">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="d6bf1-151">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <MSRP>44.95</MSRP>    <Abstract>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Abstract>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <MSRP>45.95</MSRP>    <Abstract>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Abstract>
      </Book>
    </Catalog>
    ```

## <a name="see-also"></a><span data-ttu-id="d6bf1-152">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d6bf1-152">See also</span></span>

- [<span data-ttu-id="d6bf1-153">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="d6bf1-153">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="d6bf1-154">XML</span><span class="sxs-lookup"><span data-stu-id="d6bf1-154">XML</span></span>](index.md)
- [<span data-ttu-id="d6bf1-155">방법: 파일, 문자열 또는 스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="d6bf1-155">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="d6bf1-156">LINQ</span><span class="sxs-lookup"><span data-stu-id="d6bf1-156">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="d6bf1-157">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="d6bf1-157">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
