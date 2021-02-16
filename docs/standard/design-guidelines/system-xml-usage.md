---
description: '자세한 정보: System.Xml 사용법'
title: System.Xml 사용법
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 51886c07f0b68bb329c258daa93e809d94839341
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641852"
---
# <a name="systemxml-usage"></a><span data-ttu-id="63b5c-103">System.Xml 사용법</span><span class="sxs-lookup"><span data-stu-id="63b5c-103">System.Xml Usage</span></span>

<span data-ttu-id="63b5c-104">이 섹션에서는 XML 데이터를 나타내는 데 사용할 수 있는 <xref:System.Xml?displayProperty=nameWithType> 네임스페이스에 있는 여러 형식의 사용법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63b5c-104">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="63b5c-105">❌ XML 데이터를 나타내는 데 <xref:System.Xml.XmlNode> 또는 <xref:System.Xml.XmlDocument>를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="63b5c-105">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="63b5c-106"><xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>의 인스턴스 또는 <xref:System.Xml.Linq.XNode>의 하위 형식을 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="63b5c-106">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="63b5c-107">`XmlNode` 및 `XmlDocument`는 퍼블릭 API에 노출되도록 설계되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="63b5c-107">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="63b5c-108">✔️ XML을 허용하거나 반환하는 멤버의 입력 또는 출력으로 `XmlReader`, `IXPathNavigable` 또는 `XNode`의 하위 형식을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="63b5c-108">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="63b5c-109">메모리 내 XML 문서의 특정 구현에서 메서드를 분리하고 `XNode`, `XmlReader` 또는 <xref:System.Xml.XPath.XPathNavigator>를 노출하는 가상 XML 데이터 소스로 작업할 수 있도록 하기 때문에 `XmlDocument`, `XmlNode` 또는 <xref:System.Xml.XPath.XPathDocument> 대신 이러한 추상화를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63b5c-109">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="63b5c-110">❌ 기본 개체 모델이나 데이터 소스의 XML 보기를 나타내는 형식을 만들려면 서브클래스 `XmlDocument`를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="63b5c-110">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="63b5c-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="63b5c-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="63b5c-112">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="63b5c-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="63b5c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63b5c-113">See also</span></span>

- [<span data-ttu-id="63b5c-114">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="63b5c-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="63b5c-115">사용 지침</span><span class="sxs-lookup"><span data-stu-id="63b5c-115">Usage Guidelines</span></span>](usage-guidelines.md)
