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
# <a name="linq-to-xml-annotations"></a>LINQ to XML 주석

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 주석을 사용하여 임의의 형식에 대한 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있습니다.

<xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>와 같은 XML 구성 요소에 주석을 추가하려면 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 메서드를 호출합니다. 형식별로 주석을 검색할 수 있습니다.

주석은 XML infoset의 일부가 아니므로 직렬화되거나 역직렬화되지 않습니다.

## <a name="methods"></a>메서드

주석 작업을 할 때 다음 메서드를 사용할 수 있습니다.

|메서드|Description|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<xref:System.Xml.Linq.XObject>의 주석 목록에 개체를 추가합니다.|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|지정된 형식의 첫 번째 주석 개체를 <xref:System.Xml.Linq.XObject>에서 가져옵니다.|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<xref:System.Xml.Linq.XObject>에 대한 지정된 형식의 주석 컬렉션을 가져옵니다.|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|지정된 형식의 주석을 <xref:System.Xml.Linq.XObject>에서 제거합니다.|
