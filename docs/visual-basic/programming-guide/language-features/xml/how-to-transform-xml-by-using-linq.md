---
title: '방법: LINQ를 사용하여 XML 변형'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: dab394ec45567589e002b5d2ac76ec19fb0f76c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374884"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 XML 변환(Visual Basic)

[Xml 리터럴을](../../../language-reference/xml-literals/index.md) 사용 하면 한 소스에서 xml을 쉽게 읽고 새 xml 형식으로 변환할 수 있습니다. LINQ 쿼리를 사용 하 여 변형할 콘텐츠를 검색 하거나 기존 문서의 내용을 새 XML 형식으로 변경할 수 있습니다.

이 항목의 예제에서는 XML 소스 문서에서 HTML로 콘텐츠를 변환 하 여 브라우저에서 볼 수 있도록 합니다.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a>XML 문서를 변환 하려면

1. Visual Studio에서 **콘솔 응용 프로그램** 프로젝트 템플릿에 새 Visual Basic 프로젝트를 만듭니다.

2. 프로젝트에서 만든 module1.vb .vb 파일을 두 번 클릭 하 여 Visual Basic 코드를 수정 합니다. 모듈의에 다음 코드를 추가 합니다 `Sub Main` `Module1` . 이 코드는 원본 XML 문서를 개체로 만듭니다 <xref:System.Xml.Linq.XDocument> .

    ```vb
    Dim catalog =
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
              Get the expert insights, practical code samples,
              and best practices you need
              to advance your expertise with <technology>Visual
              Basic .NET</technology>.
              Learn how to create faster, more reliable applications
              based on professional,
              pragmatic guidance by today's top <audience>developers</audience>.
            </Description>
          </Book>
        </Catalog>
    ```

     [방법: 파일, 문자열 또는 스트림에서 XML 로드](how-to-load-xml-from-a-file-string-or-stream.md)

3. 소스 XML 문서를 만드는 코드 뒤에 다음 코드를 추가 하 여 개체에서 모든 요소를 검색 하 \<Book> 고 HTML 문서로 변환 합니다. \<Book>요소 목록은 변환 된 HTML을 포함 하는 개체의 컬렉션을 반환 하는 LINQ 쿼리를 사용 하 여 만듭니다 <xref:System.Xml.Linq.XElement> . 포함 식을 사용 하 여 소스 문서의 값을 새 XML 형식으로 저장할 수 있습니다.

     결과 HTML 문서는 메서드를 사용 하 여 파일에 기록 됩니다 <xref:System.Xml.Linq.XElement.Save%2A> .

    ```vb
    Dim htmlOutput =
      <html>
        <body>
          <%= From book In catalog.<Catalog>.<Book>
              Select <div>
                       <h1><%= book.<Title>.Value %></h1>
                       <h3><%= "By " & book.<Author>.Value %></h3>
                        <h3><%= "Price = " & book.<Price>.Value %></h3>
                        <h2>Description</h2>
                        <%= TransformDescription(book.<Description>(0)) %>
                        <hr/>
                      </div> %>
        </body>
      </html>

    htmlOutput.Save("BookDescription.html")
    ```

4. 이후 `Sub Main` `Module1` 에서 새 메서드 ()를 추가 `Sub` 하 여 노드를 \<Description> 지정 된 HTML 형식으로 변환 합니다. 이 메서드는 이전 단계에서 코드에 의해 호출 되며 요소의 형식을 유지 하는 데 사용 됩니다 \<Description> .

     이 메서드는 요소의 하위 요소를 \<Description> HTML로 바꿉니다. `ReplaceWith`메서드는 하위 요소의 위치를 유지 하는 데 사용 됩니다. 요소의 변환 된 내용이 \<Description> HTML 단락 () 요소에 포함 되어 \<p> 있습니다. <xref:System.Xml.Linq.XContainer.Nodes%2A>속성은 요소의 변환 된 콘텐츠를 검색 하는 데 사용 됩니다 \<Description> . 이렇게 하면 하위 요소가 변환 된 내용에 포함 됩니다.

     뒤에 다음 코드를 `Sub Main` 추가 `Module1` 합니다.

    ```vb
    Public Function TransformDescription(ByVal desc As XElement) As XElement

      ' Replace <technology> elements with <b>.
      Dim content = (From element In desc...<technology>).ToList()

      If content.Count > 0 Then
        For i = 0 To content.Count - 1
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)
        Next
      End If

      ' Replace <audience> elements with <i>.
      content = (From element In desc...<audience>).ToList()

      If content.Count > 0 Then
        For i = 0 To content.Count - 1
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)
        Next
      End If

      ' Return the updated contents of the <Description> element.
      Return <p><%= desc.Nodes %></p>
    End Function
    ```

5. 변경 내용을 저장합니다.

6. F5 키를 눌러 코드를 실행 합니다. 저장 된 결과 문서는 다음과 유사 합니다.

    ```html
    <?xml version="1.0"?>
    <html>
      <body>
        <div>
          <h1>XML Developer's Guide</h1>
          <h3>By Garghentini, Davide</h3>
          <h3>Price = 44.95</h3>
          <h2>Description</h2>
          <p>
            An in-depth look at creating applications
            with <b>XML</b>. For
            <i>beginners</i> or
            <i>advanced</i> developers.
          </p>
          <hr />
        </div>
        <div>
          <h1>Developing Applications with Visual Basic .NET</h1>
          <h3>By Spencer, Phil</h3>
          <h3>Price = 45.95</h3>
          <h2>Description</h2>
          <p>
            Get the expert insights, practical code
            samples, and best practices you need
            to advance your expertise with <b>Visual
            Basic .NET</b>. Learn how to create faster,
            more reliable applications based on
            professional, pragmatic guidance by today's
            top <i>developers</i>.
          </p>
          <hr />
        </div>
      </body>
    </html>
    ```

## <a name="see-also"></a>참고 항목

- [XML 리터럴](../../../language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 조작](manipulating-xml.md)
- [XML](index.md)
- [방법: 파일, 문자열 또는 스트림에서 XML 로드](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Visual Basic의 LINQ 소개](../linq/introduction-to-linq.md)
