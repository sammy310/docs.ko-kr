---
title: '방법: 파일, 문자열 또는 Stream (Visual Basic)에서 XML 로드'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 2b9da2062068ef25c5df97ef19b1502999ea78ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052536"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>방법: 파일, 문자열 또는 Stream (Visual Basic)에서 XML 로드
만들 수 있습니다 [XML 리터럴을](../../../../visual-basic/language-reference/xml-literals/index.md) 몇 가지 메서드를 사용 하 여 파일, 문자열 또는 스트림에 같은 외부 원본에서 콘텐츠를 사용 하 여 채웁니다. 이러한 메서드는 다음 예제에 표시 됩니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>파일에서 XML을 로드 하지  
  
- 와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 사용 하 여 파일에서 개체를 `Load` 메서드. 이 메서드는 입력으로 파일 경로, 텍스트 스트림 또는 XML 스트림을 걸릴 수 있습니다.  
  
     다음 코드 예제에서는 합니다 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> 채우는 방법은 <xref:System.Xml.Linq.XDocument> 텍스트 파일에서 XML 사용 하 여 개체입니다.  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a>문자열에서 XML을 로드 하지  
  
- 와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체를 문자열에서 사용할 수는 `Parse` 메서드.  
  
     다음 코드 예제에서는 합니다 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> 메서드를는 <xref:System.Xml.Linq.XDocument> 문자열에서 XML 사용 하 여 개체입니다.  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a>스트림에서 XML 로드  
  
- 와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 사용할 수는 스트림에서 개체를 `Load` 메서드 또는 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> 메서드.  
  
 다음 코드 예제에서는 합니다 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 채우는 방법은 <xref:System.Xml.Linq.XDocument> XML 스트림에서 XML 사용 하 여 개체입니다.  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
