---
title: System.Xml 사용법
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 07828219f2e17be925d060fa3bb33a9209ecb62b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291671"
---
# <a name="systemxml-usage"></a>System.Xml 사용법
이 섹션에서는 <xref:System.Xml?displayProperty=nameWithType> XML 데이터를 나타내는 데 사용할 수 있는 네임 스페이스에 있는 여러 형식의 사용에 대해 설명 합니다.

 ❌<xref:System.Xml.XmlNode> <xref:System.Xml.XmlDocument> XML 데이터를 표시 하는 데 또는를 사용 하지 마십시오. <xref:System.Xml.XPath.IXPathNavigable>대신,, 또는 하위 형식의 인스턴스를 사용 <xref:System.Xml.XmlReader> <xref:System.Xml.XmlWriter> <xref:System.Xml.Linq.XNode> 합니다. `XmlNode`및 `XmlDocument` 는 공용 api에서 노출 하도록 설계 되지 않았습니다.

 ✔️는 `XmlReader` , `IXPathNavigable` 또는의 하위 형식을 `XNode` XML을 허용 하거나 반환 하는 멤버의 입력 또는 출력으로 사용 합니다.

 , 또는 대신 이러한 추상화를 사용 `XmlDocument` `XmlNode` <xref:System.Xml.XPath.XPathDocument> 합니다 .이는 메모리 내 XML 문서의 특정 구현에서 메서드를 분리, 또는를 노출 하는 가상 xml 데이터 원본에 대 한 작업을 수행할 수 있기 때문입니다 `XNode` `XmlReader` <xref:System.Xml.XPath.XPathNavigator> .

 ❌`XmlDocument`기본 개체 모델 또는 데이터 원본의 XML 뷰를 나타내는 형식을 만들려면 하위 클래스를 사용 하지 마십시오.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [사용 지침](usage-guidelines.md)
