---
title: XML 트리 수정(LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
ms.openlocfilehash: c946052beb612c087d26e312875b7f7950ceadf5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353183"
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>Modifying XML Trees (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]은 XML 트리의 메모리 내 저장소입니다. 소스에서 XML 트리를 로드하거나 XML 트리의 구문을 분석한 후 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 통해 메모리 내 트리를 수정하고 serialize한 다음 파일에 저장하거나 원격 서버에 보낼 수 있습니다.  
  
 메모리 내 트리를 수정하는 경우 <xref:System.Xml.Linq.XContainer.Add%2A>와 같은 특정 메서드를 사용합니다.  
  
 그러나 함수 생성을 사용하여 다른 모양의 새 트리를 생성하는 다른 방법도 있습니다. XML 트리에 수행해야 하는 변경 유형과 트리 크기에 따라 이 방법은 더 강력하고 개발하기 쉬울 수 있습니다. 이 단원의 첫 번째 항목에서는 이러한 두 방법을 비교합니다.  
  
## <a name="in-this-section"></a>단원 내용  
  
|항목|설명|  
|-----------|-----------------|  
|[In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|메모리 내 XML 트리 수정과 함수 생성을 비교합니다.|  
|[Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|요소, 특성 또는 노드를 XML 트리에 추가하는 방법에 대해 설명합니다.|  
|[XML 트리에서 요소, 특성 및 노드 수정](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|기존 요소, 특성 또는 노드를 수정하는 방법에 대해 설명합니다.|  
|[Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|XML 트리에서 요소, 특성 또는 노드를 제거하는 방법에 대해 설명합니다.|  
|[Maintaining Name/Value Pairs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|이름/값 쌍으로 가장 잘 유지되는 애플리케이션 정보(예: 구성 정보 또는 전역 설정)를 유지 관리하는 방법에 대해 설명합니다.|  
|[How to: Change the Namespace for an Entire XML Tree (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|XML 트리를 한 네임스페이스에서 다른 네임스페이스로 이동하는 방법을 보여 줍니다.|  
  
## <a name="see-also"></a>참조

- [Programming Guide (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
