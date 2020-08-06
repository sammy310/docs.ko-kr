---
title: XML 트리에서 요소, 특성 및 노드 수정
description: 요소, 해당 자식 노드 또는 해당 특성을 수정하는 데 사용할 수 있는 메서드 및 속성에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: bfff882dc57a4f6f4b228563ac923122097d88d0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303168"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="6891b-103">XML 트리에서 요소, 특성 및 노드 수정</span><span class="sxs-lookup"><span data-stu-id="6891b-103">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="6891b-104">다음 표에는 요소, 해당 요소의 자식 요소 또는 특성을 수정하는 데 사용할 수 있는 메서드와 속성이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="6891b-105">다음 메서드는 <xref:System.Xml.Linq.XElement>를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-105">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="6891b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6891b-106">Method</span></span>|<span data-ttu-id="6891b-107">설명</span><span class="sxs-lookup"><span data-stu-id="6891b-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-108">요소를 구문 분석된 XML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-108">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-109">요소의 모든 내용(자식 노드와 특성)을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-109">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-110">요소의 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-110">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-111">요소의 모든 내용(자식 노드와 특성)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-111">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-112">요소의 특성을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-112">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-113">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-113">Sets the value of an attribute.</span></span> <span data-ttu-id="6891b-114">특성이 없으면 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="6891b-115">값이 `null`로 설정되어 있으면 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-115">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-116">자식 요소의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-116">Sets the value of a child element.</span></span> <span data-ttu-id="6891b-117">요소가 없으면 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="6891b-118">값이 `null`로 설정되어 있으면 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-118">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-119">요소의 내용(자식 노드)을 지정된 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-120">요소의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-120">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="6891b-121">다음 메서드는 <xref:System.Xml.Linq.XAttribute>를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="6891b-122">메서드</span><span class="sxs-lookup"><span data-stu-id="6891b-122">Method</span></span>|<span data-ttu-id="6891b-123">설명</span><span class="sxs-lookup"><span data-stu-id="6891b-123">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-124">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-124">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-125">특성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-125">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="6891b-126">다음 메서드는 <xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 포함)를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="6891b-127">메서드</span><span class="sxs-lookup"><span data-stu-id="6891b-127">Method</span></span>|<span data-ttu-id="6891b-128">설명</span><span class="sxs-lookup"><span data-stu-id="6891b-128">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-129">노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-129">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="6891b-130">다음 메서드는 <xref:System.Xml.Linq.XContainer>(<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>)를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="6891b-131">메서드</span><span class="sxs-lookup"><span data-stu-id="6891b-131">Method</span></span>|<span data-ttu-id="6891b-132">설명</span><span class="sxs-lookup"><span data-stu-id="6891b-132">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="6891b-133">자식 노드를 새 내용으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-133">Replaces the children nodes with new content.</span></span>|  
