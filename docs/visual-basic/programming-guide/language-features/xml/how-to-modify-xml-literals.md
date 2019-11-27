---
title: '방법: XML 리터럴 수정'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330853"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="af420-102">방법: XML 리터럴 수정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af420-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="af420-103">Visual Basic은 XML 리터럴을 수정할 수 있는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="af420-104">요소와 특성을 추가 하거나 삭제할 수 있으며 기존 요소를 새 XML 요소로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="af420-105">이 항목에서는 기존 XML 리터럴을 수정 하는 방법에 대 한 몇 가지 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="af420-106">XML 리터럴의 값을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="af420-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="af420-107">XML 리터럴의 값을 수정 하려면 XML 리터럴에 대 한 참조를 가져오고 `Value` 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="af420-108">다음 코드 예제에서는 XML 문서에 있는 모든 \<가격 > 요소의 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="af420-109">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="af420-110">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-110">Source XML:</span></span>

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

    <span data-ttu-id="af420-111">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-111">Modified XML:</span></span>

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
    > <span data-ttu-id="af420-112">`Value` 속성은 컬렉션의 첫 번째 XML 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="af420-113">컬렉션에 이름이 같은 요소가 둘 이상 있는 경우 `Value` 속성을 설정 하면 컬렉션의 첫 번째 요소에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="af420-114">XML 리터럴에 특성을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="af420-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="af420-115">XML 리터럴에 특성을 추가 하려면 먼저 XML 리터럴에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af420-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="af420-116">그런 다음 새 XML 특성 축 속성을 추가 하 여 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="af420-117"><xref:System.Xml.Linq.XContainer.Add%2A> 메서드를 사용 하 여 새 <xref:System.Xml.Linq.XAttribute> 개체를 XML 리터럴에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="af420-118">다음 예에서는 두 옵션을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="af420-119">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="af420-120">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-120">Source XML:</span></span>

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

    <span data-ttu-id="af420-121">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-121">Modified XML:</span></span>

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

    <span data-ttu-id="af420-122">XML 특성 축 속성에 대 한 자세한 내용은 [Xml 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af420-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="af420-123">XML 리터럴에 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="af420-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="af420-124">XML 리터럴에 요소를 추가 하려면 먼저 XML 리터럴에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af420-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="af420-125">그런 다음 <xref:System.Xml.Linq.XContainer.Add%2A> 메서드를 사용 하 여 새 <xref:System.Xml.Linq.XElement> 개체를 요소의 마지막 하위 요소로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="af420-126"><xref:System.Xml.Linq.XContainer.AddFirst%2A> 메서드를 사용 하 여 새 <xref:System.Xml.Linq.XElement> 개체를 첫 번째 하위 요소로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="af420-127">다른 하위 요소를 기준으로 특정 위치에 새 요소를 추가 하려면 먼저 인접 하위 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af420-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="af420-128">그런 다음 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> 메서드를 사용 하 여 인접 한 하위 요소 앞에 새 <xref:System.Xml.Linq.XElement> 개체를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="af420-129"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A> 메서드를 사용 하 여 인접 한 하위 요소 뒤에 새 <xref:System.Xml.Linq.XElement> 개체를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="af420-130">다음 예제에서는 이러한 각 기술에 대 한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="af420-131">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="af420-132">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-132">Source XML:</span></span>

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

    <span data-ttu-id="af420-133">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-133">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="af420-134">XML 리터럴에서 요소나 특성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="af420-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="af420-135">XML 리터럴에서 요소나 특성을 제거 하려면 다음 예제와 같이 요소나 특성에 대 한 참조를 가져오고 `Remove` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="af420-136">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="af420-137">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-137">Source XML:</span></span>

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

    <span data-ttu-id="af420-138">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-138">Modified XML:</span></span>

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

    <span data-ttu-id="af420-139">XML 리터럴에서 모든 요소나 특성을 제거 하려면 XML 리터럴에 대 한 참조를 가져오고 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="af420-140">XML 리터럴을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="af420-140">To modify an XML literal</span></span>

1. <span data-ttu-id="af420-141">XML 요소의 이름을 변경 하려면 먼저 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af420-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="af420-142">그런 다음 새 이름을 가진 새 <xref:System.Xml.Linq.XElement> 개체를 만들어 기존 <xref:System.Xml.Linq.XElement> 개체의 <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 메서드에 새 <xref:System.Xml.Linq.XElement> 개체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="af420-143">바꾸려는 요소에 유지 해야 하는 하위 요소가 있으면 새 <xref:System.Xml.Linq.XElement> 개체의 값을 기존 요소의 <xref:System.Xml.Linq.XContainer.Nodes%2A> 속성으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af420-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="af420-144">그러면 새 요소의 값이 기존 요소의 내부 XML로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af420-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="af420-145">그렇지 않으면 새 요소의 값을 기존 요소의 `Value` 속성으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af420-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="af420-146">다음 코드 예제에서는 모든 \<설명 > 요소를 \<추상 > 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="af420-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="af420-147">\<Description > 요소의 내용은 <xref:System.Xml.Linq.XContainer.Nodes%2A> 설명 \<> 개체의 <xref:System.Xml.Linq.XElement> 속성을 사용 하 여 새 \<추상 > 요소에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af420-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="af420-148">다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af420-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="af420-149">원본 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-149">Source XML:</span></span>

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

    <span data-ttu-id="af420-150">수정 된 XML:</span><span class="sxs-lookup"><span data-stu-id="af420-150">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="af420-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af420-151">See also</span></span>

- [<span data-ttu-id="af420-152">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="af420-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="af420-153">XML</span><span class="sxs-lookup"><span data-stu-id="af420-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="af420-154">방법: 파일, 문자열 또는 스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="af420-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="af420-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="af420-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="af420-156">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="af420-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
