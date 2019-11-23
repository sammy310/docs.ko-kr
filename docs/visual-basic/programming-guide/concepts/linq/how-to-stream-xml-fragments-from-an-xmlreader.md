---
title: '방법: XmlReader에서 XML 조각 스트리밍'
ms.date: 07/20/2015
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
ms.openlocfilehash: abefc8c6e75ae41c47135a2e89cdb3be6a8e5cd6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346220"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>How to: Stream XML Fragments from an XmlReader (Visual Basic)
큰 XML 파일을 처리해야 하는 경우 전체 XML 트리를 메모리에 로드하는 것이 가능하지 않을 수 있습니다. 이 항목에서는 <xref:System.Xml.XmlReader>를 사용하여 조각을 스트림하는 방법을 보여 줍니다.  
  
 <xref:System.Xml.XmlReader>를 사용하여 <xref:System.Xml.Linq.XElement> 개체를 읽는 가장 효과적인 방법 중 하나는 사용자 지정 축 메서드를 직접 작성하는 것입니다. 일반적으로 축 메서드는 이 항목의 예제에 나와 있는 대로 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>과 같은 컬렉션을 반환합니다. 사용자 지정 축 메서드에서는 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 메서드를 호출하여 XML 조각을 만든 후 `yield return`을 사용하여 컬렉션을 반환합니다. 이것은 사용자 지정 축 메서드에 지연된 실행 의미를 제공합니다.  
  
 <xref:System.Xml.XmlReader> 개체에서 XML 트리를 만드는 경우 <xref:System.Xml.XmlReader>가 요소에 배치되어야 합니다. <xref:System.Xml.Linq.XNode.ReadFrom%2A> 메서드는 요소의 닫는 태그를 읽을 때까지 반환되지 않습니다.  
  
 부분 트리를 만들려는 경우 <xref:System.Xml.XmlReader>를 인스턴스화하고 <xref:System.Xml.Linq.XElement> 트리로 변환할 노드에 판독기를 배치한 다음 <xref:System.Xml.Linq.XElement> 개체를 만들 수 있습니다.  
  
 The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.  
  
 The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.  
  
## <a name="example"></a>예제  
 이 예제에서는 사용자 지정 축 메서드를 만듭니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리를 사용하여 이 메서드를 쿼리할 수 있습니다. 사용자 지정 축 메서드 `StreamRootChildDoc`는 반복되는 `Child` 요소가 있는 문서를 읽도록 특정하게 디자인된 메서드입니다.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim markup = "<Root>" &  
                     "  <Child Key=""01"">" &  
                     "    <GrandChild>aaa</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""02"">" &  
                     "    <GrandChild>bbb</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""03"">" &  
                     "    <GrandChild>ccc</GrandChild>" &  
                     "  </Child>" &  
                     "</Root>"  
  
        Dim grandChildData =  
             From el In New StreamRootChildDoc(New IO.StringReader(markup))  
             Where CInt(el.@Key) > 1  
             Select el.<GrandChild>.Value  
  
        For Each s In grandChildData  
            Console.WriteLine(s)  
        Next  
    End Sub  
End Module  
  
Public Class StreamRootChildDoc  
    Implements IEnumerable(Of XElement)  
  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamChildEnumerator(_stringReader)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamChildEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _reader As Xml.XmlReader  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        While _reader.Read()  
            Select Case _reader.NodeType  
                Case Xml.XmlNodeType.Element  
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)  
                    If el IsNot Nothing Then  
                        _current = el  
                        Return True  
                    End If  
            End Select  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```console  
bbb  
ccc  
```  
  
 이 예제의 소스 문서는 매우 작습니다. `Child` 요소가 수백만 있더라도 이 예제에서는 여전히 작은 메모리 공간만 사용할 것입니다.  
  
## <a name="see-also"></a>참조

- [Walkthrough: Implementing IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)
- [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
