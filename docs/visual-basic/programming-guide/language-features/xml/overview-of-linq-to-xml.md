---
title: Visual Basic의 LINQ to XML 개요
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 91f622b9eecdd1aec8b9361493095e92a851988e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816176"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Visual Basic의 LINQ to XML 개요
Visual Basic에 대 한 지원을 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML 리터럴과 XML 축 속성을 통해. 이 옵션을 사용 하면 Visual Basic 코드에서 XML을 사용 하 여 작업에 대 한 친숙 하 고 편리한 구문을 사용할 수 있습니다. *XML 리터럴* 코드에서 직접 XML을 포함할 수 있도록 합니다. *XML 축 속성* 액세스 자식 노드, 하위 노드 및 XML 리터럴의 특성 수입니다. 자세한 내용은 [XML 리터럴 개요](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) 하 고 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 메모리 내 XML 프로그래밍 API를 활용 하도록 특별히 설계 된 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]합니다. 호출할 수 있지만 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Api를 직접,만 Visual Basic XML 리터럴 선언 및 XML 축 속성에 직접 액세스할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴과 XML 축 속성은 ASP.NET 페이지의 선언적 코드에서 지원 되지 않습니다. Visual Basic XML 기능을 사용 하려면 ASP.NET 응용 프로그램에서 코드 숨김 페이지에 코드를 입력 합니다.  
  
 ![비디오 링크](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") 관련된 비디오 데모를 참조 하세요. [하는 LINQ to XML 시작 하는 방법?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) 하 고 [LINQ to XML 사용 하 여 Excel 스프레드시트 만들기 구성 방법?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml)합니다.  
  
## <a name="creating-xml"></a>XML 만들기  
 Visual Basic에서 XML 트리를 만드는 두 가지가 있습니다. 코드에서 직접 리터럴 XML를 선언할 수 있습니다 하거나 사용할 수 있습니다는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Api 트리를 만들 수 있습니다. 두 프로세스 모두 XML 트리의 최종 구조를 반영 하는 코드를 사용 합니다. 예를 들어, 다음 코드 예제는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 자세한 내용은 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)합니다.  
  
## <a name="accessing-and-navigating-xml"></a>액세스 하 고 XML 탐색  
 Visual Basic XML 축 속성에 액세스 하 고 XML 구조를 탐색을 제공 합니다. 이러한 속성을 사용 하 여 XML 자식 요소 이름을 지정 하 여 XML 요소 및 특성에 액세스할 수 있습니다. 명시적으로 호출할 수 있습니다 또는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 탐색 하 고 특성과 해당 요소를 찾는 방법입니다. 예를 들어, 다음 코드 예제에서는 특성에는 XML 요소의 자식 요소를 가리키는 XML 축 속성을 사용 합니다. 사용 하 여 코드 예제는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 자식 요소를 검색 하 고 효과적인 변환을 수행 하는 XML 요소로 출력 하 여 쿼리 합니다.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 자세한 내용은 [Visual Basic의 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)합니다.  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 Visual Basic을 사용 하면 사용 하 여 전역 XML 네임 스페이스에 대 한 별칭을 지정할 수 있습니다는 `Imports` 문입니다. 다음 예제에서는 사용 하는 방법의 `Imports` 을 XML 네임 스페이스를 가져오기 위한 문:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 XML 축 속성에 액세스 하 고 XML 문서 및 요소에 대 한 XML 리터럴을 선언 하는 경우 XML 네임 스페이스 별칭을 사용할 수 있습니다.  
  
 검색할 수 있습니다는 <xref:System.Xml.Linq.XNamespace> 를 사용 하 여 특정 네임 스페이스 접두사에 대 한 개체를 [GetXmlNamespace 연산자](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)합니다.  
  
 자세한 내용은 [Imports 문 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>XML 리터럴의 XML 네임 스페이스를 사용 하 여  
 다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Xml.Linq.XElement> 전역 네임 스페이스를 사용 하는 개체 `ns`:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Visual Basic 컴파일러는 XML 리터럴의 XML 네임 스페이스를 사용 하는 것에 대 한 XML 표기를 사용 하는 해당 코드에 XML 네임 스페이스 별칭을 포함 하는 변환 된 `xmlns` 특성입니다. 컴파일된 경우 이전 섹션의 예제 코드에서는 기본적으로 동일한 실행 코드를 다음 예제와 같이 생성 합니다.  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>XML 네임 스페이스를 사용 하 여 XML 축 속성  
 XML 리터럴에서 선언 된 XML 네임 스페이스가 XML 축 속성에서 사용 하기 위해 사용할 수 없는 경우 그러나 XML 축 속성을 사용 하 여 전역 네임 스페이스를 사용할 수 있습니다. 로컬 요소 이름과에서 XML 네임 스페이스 접두사를 구분 하려면 콜론을 사용 합니다. 예를 들면 다음과 같습니다.  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>참고자료

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Visual Basic에서 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
