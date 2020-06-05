---
title: '방법: XML 리터럴 수정'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: a2ac2e9802d4c8ab522bb430d15cce5616430437
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374903"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>방법: XML 리터럴 수정(Visual Basic)

Visual Basic은 XML 리터럴을 수정할 수 있는 편리한 방법을 제공 합니다. 요소와 특성을 추가 하거나 삭제할 수 있으며 기존 요소를 새 XML 요소로 바꿀 수도 있습니다. 이 항목에서는 기존 XML 리터럴을 수정 하는 방법에 대 한 몇 가지 예를 제공 합니다.

### <a name="to-modify-the-value-of-an-xml-literal"></a>XML 리터럴의 값을 수정 하려면

1. XML 리터럴의 값을 수정 하려면 XML 리터럴에 대 한 참조를 가져오고 `Value` 속성을 원하는 값으로 설정 합니다.

    다음 코드 예제에서는 \<Price> XML 문서에 있는 모든 요소의 값을 업데이트 합니다.

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.

    원본 XML:

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

    수정 된 XML:

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
    > `Value`속성은 컬렉션의 첫 번째 XML 요소를 참조 합니다. 컬렉션에 이름이 같은 요소가 둘 이상 있는 경우 속성을 설정 하면 `Value` 컬렉션의 첫 번째 요소에만 영향을 줍니다.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>XML 리터럴에 특성을 추가 하려면

1. XML 리터럴에 특성을 추가 하려면 먼저 XML 리터럴에 대 한 참조를 가져옵니다. 그런 다음 새 XML 특성 축 속성을 추가 하 여 특성을 추가할 수 있습니다. <xref:System.Xml.Linq.XAttribute>메서드를 사용 하 여 새 개체를 XML 리터럴에 추가할 수도 있습니다 <xref:System.Xml.Linq.XContainer.Add%2A> . 다음 예에서는 두 옵션을 모두 보여 줍니다.

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.

    원본 XML:

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

    수정 된 XML:

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

    XML 특성 축 속성에 대 한 자세한 내용은 [Xml 특성 축 속성](../../../language-reference/xml-axis/xml-attribute-axis-property.md)을 참조 하세요.

### <a name="to-add-an-element-to-an-xml-literal"></a>XML 리터럴에 요소를 추가 하려면

1. XML 리터럴에 요소를 추가 하려면 먼저 XML 리터럴에 대 한 참조를 가져옵니다. 그런 다음 <xref:System.Xml.Linq.XElement> 메서드를 사용 하 여 새 개체를 요소의 마지막 하위 요소로 추가할 수 있습니다 <xref:System.Xml.Linq.XContainer.Add%2A> . <xref:System.Xml.Linq.XElement>메서드를 사용 하 여 새 개체를 첫 번째 하위 요소로 추가할 수 있습니다 <xref:System.Xml.Linq.XContainer.AddFirst%2A> .

    다른 하위 요소를 기준으로 특정 위치에 새 요소를 추가 하려면 먼저 인접 하위 요소에 대 한 참조를 가져옵니다. 그런 다음 <xref:System.Xml.Linq.XElement> 메서드를 사용 하 여 인접 한 하위 요소 앞에 새 개체를 추가할 수 있습니다 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> . <xref:System.Xml.Linq.XElement>메서드를 사용 하 여 인접 한 하위 요소 뒤에 새 개체를 추가할 수도 있습니다 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> .

    다음 예제에서는 이러한 각 기술에 대 한 예제를 보여 줍니다.

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.

    원본 XML:

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

    수정 된 XML:

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>XML 리터럴에서 요소나 특성을 제거 하려면

1. XML 리터럴에서 요소나 특성을 제거 하려면 다음 예제와 같이 요소나 특성에 대 한 참조를 가져오고 메서드를 호출 `Remove` 합니다.

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.

    원본 XML:

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

    수정 된 XML:

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

    XML 리터럴에서 모든 요소나 특성을 제거 하려면 XML 리터럴에 대 한 참조를 가져오고 메서드를 호출 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 합니다.

### <a name="to-modify-an-xml-literal"></a>XML 리터럴을 수정 하려면

1. XML 요소의 이름을 변경 하려면 먼저 요소에 대 한 참조를 가져옵니다. 그런 다음 새 <xref:System.Xml.Linq.XElement> 이름을 포함 하는 새 개체를 만들고 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 기존 개체의 메서드에 새 개체를 전달할 수 있습니다 <xref:System.Xml.Linq.XElement> .

    바꾸려는 요소에 유지 해야 하는 하위 요소가 있으면 새 개체의 값을 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XContainer.Nodes%2A> 기존 요소의 속성으로 설정 합니다. 그러면 새 요소의 값이 기존 요소의 내부 XML로 설정 됩니다. 그렇지 않으면 새 요소의 값을 기존 요소의 속성으로 설정할 수 있습니다 `Value` .

    다음 코드 예제에서는 \<Description> 요소를 사용 하 여 모든 요소를 바꿉니다 \<Abstract> . 요소의 콘텐츠는 \<Description> \<Abstract> <xref:System.Xml.Linq.XContainer.Nodes%2A> 개체의 속성을 사용 하 여 새 요소에서 유지 됩니다 \<Description> <xref:System.Xml.Linq.XElement> .

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    다음은이 코드 예제의 샘플 소스 XML 및 수정 된 XML을 보여 줍니다.

    원본 XML:

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

    수정 된 XML:

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

## <a name="see-also"></a>참고 항목

- [Visual Basic에서 XML 조작](manipulating-xml.md)
- [XML](index.md)
- [방법: 파일, 문자열 또는 스트림에서 XML 로드](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Visual Basic의 LINQ 소개](../linq/introduction-to-linq.md)
