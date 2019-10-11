---
title: '방법: 문자열 구문 분석(C#)'
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 16310e37afec950c372c7b47637986bb0eb399b8
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956617"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="4f9a4-102">방법: 문자열 구문 분석(C#)</span><span class="sxs-lookup"><span data-stu-id="4f9a4-102">How to: Parse a String (C#)</span></span>

<span data-ttu-id="4f9a4-103">이 항목에서는 C#에서 문자열의 구문을 분석하여 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f9a4-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>

## <a name="example"></a><span data-ttu-id="4f9a4-104">예</span><span class="sxs-lookup"><span data-stu-id="4f9a4-104">Example</span></span>

<span data-ttu-id="4f9a4-105">다음 C# 코드에서는 XML 문자열의 구문을 분석하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f9a4-105">The following C# code shows how to parse an XML string:</span></span>

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

<span data-ttu-id="4f9a4-106">루트 `Contacts` 노드에는 두 개의 `Contact` 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9a4-106">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="4f9a4-107">구문 분석된 XML에서 특정 데이터에 액세스하려면 [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) 메서드를 사용합니다. 이 경우에는 루트 `Contacts` 노드의 자식 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9a4-107">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="4f9a4-108">다음 예제에서는 첫 번째 `Contact` 노드를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9a4-108">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a><span data-ttu-id="4f9a4-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f9a4-109">See also</span></span>

- [<span data-ttu-id="4f9a4-110">방법: 특정 특성으로 요소 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="4f9a4-110">How to: Find an Element with a Specific Attribute (C#)</span></span>](how-to-find-an-element-with-a-specific-attribute.md)
