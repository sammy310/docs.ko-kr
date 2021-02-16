---
description: '자세한 정보: 방법: LINQ를 사용 하 여 XML 변환 (Visual Basic)'
title: '방법: LINQ를 사용하여 XML 변형'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 67e6f5f94cd71d960f742b660d3f223137bbd6d4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483640"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="69d19-103">방법: LINQ를 사용하여 XML 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69d19-103">How to: Transform XML by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="69d19-104">[Xml 리터럴을](../../../language-reference/xml-literals/index.md) 사용 하면 한 소스에서 xml을 쉽게 읽고 새 xml 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-104">[XML Literals](../../../language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="69d19-105">LINQ 쿼리를 사용 하 여 변형할 콘텐츠를 검색 하거나 기존 문서의 내용을 새 XML 형식으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-105">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>

<span data-ttu-id="69d19-106">이 항목의 예제에서는 XML 소스 문서에서 HTML로 콘텐츠를 변환 하 여 브라우저에서 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-106">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a><span data-ttu-id="69d19-107">XML 문서를 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="69d19-107">To transform an XML document</span></span>

1. <span data-ttu-id="69d19-108">Visual Studio에서 **콘솔 응용 프로그램** 프로젝트 템플릿에 새 Visual Basic 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-108">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>

2. <span data-ttu-id="69d19-109">프로젝트에서 만든 module1.vb .vb 파일을 두 번 클릭 하 여 Visual Basic 코드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-109">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="69d19-110">모듈의에 다음 코드를 추가 합니다 `Sub Main` `Module1` .</span><span class="sxs-lookup"><span data-stu-id="69d19-110">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="69d19-111">이 코드는 원본 XML 문서를 개체로 만듭니다 <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="69d19-111">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>

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

     <span data-ttu-id="69d19-112">[방법: 파일, 문자열 또는 스트림에서 XML 로드](how-to-load-xml-from-a-file-string-or-stream.md)</span><span class="sxs-lookup"><span data-stu-id="69d19-112">[How to: Load XML from a File, String, or Stream](how-to-load-xml-from-a-file-string-or-stream.md).</span></span>

3. <span data-ttu-id="69d19-113">소스 XML 문서를 만드는 코드 뒤에 다음 코드를 추가 하 여 개체에서 모든 요소를 검색 하 \<Book> 고 HTML 문서로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-113">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="69d19-114">\<Book>요소 목록은 변환 된 HTML을 포함 하는 개체의 컬렉션을 반환 하는 LINQ 쿼리를 사용 하 여 만듭니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="69d19-114">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="69d19-115">포함 식을 사용 하 여 소스 문서의 값을 새 XML 형식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-115">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>

     <span data-ttu-id="69d19-116">결과 HTML 문서는 메서드를 사용 하 여 파일에 기록 됩니다 <xref:System.Xml.Linq.XElement.Save%2A> .</span><span class="sxs-lookup"><span data-stu-id="69d19-116">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>

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

4. <span data-ttu-id="69d19-117">이후 `Sub Main` `Module1` 에서 새 메서드 ()를 추가 `Sub` 하 여 노드를 \<Description> 지정 된 HTML 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-117">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="69d19-118">이 메서드는 이전 단계에서 코드에 의해 호출 되며 요소의 형식을 유지 하는 데 사용 됩니다 \<Description> .</span><span class="sxs-lookup"><span data-stu-id="69d19-118">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>

     <span data-ttu-id="69d19-119">이 메서드는 요소의 하위 요소를 \<Description> HTML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-119">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="69d19-120">`ReplaceWith`메서드는 하위 요소의 위치를 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-120">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="69d19-121">요소의 변환 된 내용이 \<Description> HTML 단락 () 요소에 포함 되어 \<p> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-121">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="69d19-122"><xref:System.Xml.Linq.XContainer.Nodes%2A>속성은 요소의 변환 된 콘텐츠를 검색 하는 데 사용 됩니다 \<Description> .</span><span class="sxs-lookup"><span data-stu-id="69d19-122">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="69d19-123">이렇게 하면 하위 요소가 변환 된 내용에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-123">This ensures that sub-elements are included in the transformed content.</span></span>

     <span data-ttu-id="69d19-124">뒤에 다음 코드를 `Sub Main` 추가 `Module1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-124">Add the following code after `Sub Main` of `Module1`.</span></span>

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

5. <span data-ttu-id="69d19-125">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-125">Save your changes.</span></span>

6. <span data-ttu-id="69d19-126">F5 키를 눌러 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-126">Press F5 to run the code.</span></span> <span data-ttu-id="69d19-127">저장 된 결과 문서는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="69d19-127">The resulting saved document will resemble the following:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="69d19-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="69d19-128">See also</span></span>

- [<span data-ttu-id="69d19-129">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="69d19-129">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="69d19-130">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="69d19-130">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="69d19-131">XML</span><span class="sxs-lookup"><span data-stu-id="69d19-131">XML</span></span>](index.md)
- [<span data-ttu-id="69d19-132">방법: 파일, 문자열 또는 스트림에서 XML 로드</span><span class="sxs-lookup"><span data-stu-id="69d19-132">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="69d19-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="69d19-133">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="69d19-134">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="69d19-134">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
