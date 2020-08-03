---
title: LINQ to XML 주석
description: LINQ to XML에서 주석을 사용하여 임의의 형식에 대한 임의의 개체를 XML 트리의 XML 구성 요소와 연결하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: e7da666139c10b26de37816693202d96498f52d8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165569"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="ff34d-103">LINQ to XML 주석</span><span class="sxs-lookup"><span data-stu-id="ff34d-103">LINQ to XML Annotations</span></span>

<span data-ttu-id="ff34d-104">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 주석을 사용하여 임의의 형식에 대한 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-104">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="ff34d-105"><xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>와 같은 XML 구성 요소에 주석을 추가하려면 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-105">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="ff34d-106">형식별로 주석을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-106">You retrieve annotations by type.</span></span>

<span data-ttu-id="ff34d-107">주석은 XML infoset의 일부가 아니므로 직렬화되거나 역직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-107">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="ff34d-108">메서드</span><span class="sxs-lookup"><span data-stu-id="ff34d-108">Methods</span></span>

<span data-ttu-id="ff34d-109">주석 작업을 할 때 다음 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-109">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="ff34d-110">메서드</span><span class="sxs-lookup"><span data-stu-id="ff34d-110">Method</span></span>|<span data-ttu-id="ff34d-111">Description</span><span class="sxs-lookup"><span data-stu-id="ff34d-111">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="ff34d-112"><xref:System.Xml.Linq.XObject>의 주석 목록에 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="ff34d-113">지정된 형식의 첫 번째 주석 개체를 <xref:System.Xml.Linq.XObject>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-113">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="ff34d-114"><xref:System.Xml.Linq.XObject>에 대한 지정된 형식의 주석 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-114">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="ff34d-115">지정된 형식의 주석을 <xref:System.Xml.Linq.XObject>에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ff34d-115">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
