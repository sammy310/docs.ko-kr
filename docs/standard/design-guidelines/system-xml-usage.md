---
title: System.Xml 사용법
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 2ecb709684834a8280c841eb8eef4f024481f7a4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743588"
---
# <a name="systemxml-usage"></a>System.Xml 사용법
이 섹션에서는 XML 데이터를 나타내는 데 사용할 수 있는 <xref:System.Xml?displayProperty=nameWithType> 네임 스페이스에 있는 여러 형식의 사용에 대해 설명 합니다.

 ❌ <xref:System.Xml.XmlNode> 또는 <xref:System.Xml.XmlDocument>를 사용 하 여 XML 데이터를 나타내지 않습니다. 대신 <xref:System.Xml.Linq.XNode>의 <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>또는 하위 형식 인스턴스를 사용 하는 것이 좋습니다. `XmlNode` 및 `XmlDocument`는 공용 Api에서 노출 하도록 설계 되지 않았습니다.

 ✔️는 `XNode`의 `XmlReader`, `IXPathNavigable`또는 하위 유형을 XML을 허용 하거나 반환 하는 멤버의 입력 또는 출력으로 사용 합니다.

 `XmlDocument`, `XmlNode`또는 <xref:System.Xml.XPath.XPathDocument>대신 이러한 추상화를 사용 합니다 .이는 메모리 내 XML 문서의 특정 구현에서 메서드를 분리 `XNode`, `XmlReader`또는 <xref:System.Xml.XPath.XPathNavigator>를 노출 하는 가상 XML 데이터 원본으로 작업할 수 있기 때문입니다.

 기본 개체 모델 또는 데이터 원본의 XML 뷰를 나타내는 형식을 만들려면 `XmlDocument` 서브 클래스를 사용 하지 않습니다 ❌ 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
