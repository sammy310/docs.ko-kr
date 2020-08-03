---
title: 요소, 특성 및 노드를 XML 트리에 추가(C#)
description: 요소, 특성, 주석, 처리 명령 및 텍스트와 같은 내용을 기존 XML 트리에 추가하는 메서드에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 78a84401494e2d4280799632fa42dc95574e3e10
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105558"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="4045d-103">요소, 특성 및 노드를 XML 트리에 추가(C#)</span><span class="sxs-lookup"><span data-stu-id="4045d-103">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="4045d-104">내용(요소, 특성, 주석, 처리 명령, 텍스트 및 CDATA)을 기존 XML 트리에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-104">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="4045d-105">내용을 추가하는 메서드</span><span class="sxs-lookup"><span data-stu-id="4045d-105">Methods for Adding Content</span></span>  
 <span data-ttu-id="4045d-106">다음 메서드는 자식 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-106">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="4045d-107">메서드</span><span class="sxs-lookup"><span data-stu-id="4045d-107">Method</span></span>|<span data-ttu-id="4045d-108">Description</span><span class="sxs-lookup"><span data-stu-id="4045d-108">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="4045d-109"><xref:System.Xml.Linq.XContainer>의 자식 내용 끝 부분에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-109">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="4045d-110"><xref:System.Xml.Linq.XContainer>의 자식 내용 시작 부분에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-110">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="4045d-111">다음 메서드는 <xref:System.Xml.Linq.XNode>의 형제 노드로 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-111">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="4045d-112">유효한 형제 내용을 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XText>와 같은 다른 형식의 노드에 추가할 수 있지만, 형제 내용을 추가할 가장 일반적인 노드는 <xref:System.Xml.Linq.XComment>입니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-112">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="4045d-113">메서드</span><span class="sxs-lookup"><span data-stu-id="4045d-113">Method</span></span>|<span data-ttu-id="4045d-114">Description</span><span class="sxs-lookup"><span data-stu-id="4045d-114">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="4045d-115"><xref:System.Xml.Linq.XNode> 뒤에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-115">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="4045d-116"><xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-116">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4045d-117">예제</span><span class="sxs-lookup"><span data-stu-id="4045d-117">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="4045d-118">설명</span><span class="sxs-lookup"><span data-stu-id="4045d-118">Description</span></span>  
 <span data-ttu-id="4045d-119">다음 예제에서는 두 가지 XML 트리를 만든 다음 두 트리 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-119">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4045d-120">코드</span><span class="sxs-lookup"><span data-stu-id="4045d-120">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="4045d-121">주석</span><span class="sxs-lookup"><span data-stu-id="4045d-121">Comments</span></span>  
 <span data-ttu-id="4045d-122">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4045d-122">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  