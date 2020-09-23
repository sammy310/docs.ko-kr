---
title: XML에 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 8ffe6d5ed368aee6d6984ec6ab28c8832921a3f8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080181"
---
# <a name="accessing-xml-in-visual-basic"></a>Visual Basic에서 XML에 액세스

Visual Basic는 구조에 액세스 하 고 탐색 하기 위한 XML 축 속성을 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다. 이러한 속성은 XML 이름을 지정 하 여 요소 및 특성에 액세스할 수 있도록 특수 구문을 사용 합니다.  
  
 다음 표에서는 Visual Basic의 XML 요소와 특성에 액세스할 수 있게 해 주는 언어 기능을 보여 줍니다.  
  
### <a name="xml-axis-properties"></a>XML 축 속성  
  
|속성 설명|예제|설명|  
|--------------------------|-------------|-----------------|  
|*child 축*|`contact.<phone>`|`phone`요소의 자식 요소인 모든 요소를 가져옵니다 `contact` .|  
|*특성 축*|`phone.@type`|요소의 모든 `type` 특성을 가져옵니다 `phone` .|  
|*descendant 축*|`contacts...<name>`|발생 한 `name` `contacts` 계층의 깊이에 관계 없이 요소의 모든 요소를 가져옵니다.|  
|*확장 인덱서*|`contacts...<name>(0)`|시퀀스에서 첫 번째 요소를 가져옵니다 `name` .|  
|*value*|`contacts...<name>.Value`|시퀀스에서 첫 번째 개체의 문자열 표현을 가져오거나, 시퀀스가 비어 있는 경우에는입니다 `Nothing` .|  
  
## <a name="in-this-section"></a>섹션 내용  

 [방법: XML 하위 요소에 액세스](how-to-access-xml-descendant-elements.md)  
 하위 축 속성을 사용 하 여 지정 된 이름을 가진 모든 XML 요소에 액세스 하 고 지정 된 XML 요소에 포함 된 모든 XML 요소에 액세스 하는 방법을 보여 줍니다.  
  
 [방법: XML 자식 요소에 액세스](how-to-access-xml-child-elements.md)  
 자식 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 자식 요소에 액세스 하는 방법을 보여 줍니다.  
  
 [방법: XML 특성에 액세스](how-to-access-xml-attributes.md)  
 특성 축 속성을 사용 하 여 XML 요소에 지정 된 이름의 모든 XML 특성에 액세스 하는 방법을 보여 줍니다.  
  
 [방법: XML 네임스페이스 접두사 선언 및 사용](how-to-declare-and-use-xml-namespace-prefixes.md)  
 XML 네임 스페이스 접두사를 선언 하 고이 접두사를 사용 하 여 XML 요소를 만들고 액세스 하는 방법을 보여 줍니다.  
  
## <a name="related-sections"></a>관련 섹션  

 [XML 축 속성](../../../language-reference/xml-axis/index.md)  
 다양 한 XML 액세스 속성을 설명 하는 섹션에 대 한 링크를 제공 합니다.  
  
 [Visual Basic의 LINQ to XML 개요](overview-of-linq-to-xml.md)  
 Visual Basic에서를 사용 하는 방법을 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.  
  
 [Visual Basic에서 XML 만들기](creating-xml.md)  
 Visual Basic에서 XML 리터럴을 사용 하는 방법을 소개 합니다.  
  
 [Visual Basic에서 XML 조작](manipulating-xml.md)  
 Visual Basic에서 XML을 로드 하 고 수정 하는 방법에 대 한 링크를 제공 합니다.  
  
 [XML](index.md)  
 Visual Basic에서를 사용 하는 방법을 설명 하는 섹션에 대 한 링크를 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.
