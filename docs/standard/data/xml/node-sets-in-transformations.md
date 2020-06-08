---
title: 변환 과정에서 노드 집합의 역할
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
ms.openlocfilehash: 33cbae05cf35904903189ce767090d3d3cca8e4d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288747"
---
# <a name="node-sets-in-transformations"></a><span data-ttu-id="034e9-102">변환 과정에서 노드 집합의 역할</span><span class="sxs-lookup"><span data-stu-id="034e9-102">Node Sets in Transformations</span></span>
<span data-ttu-id="034e9-103">노드 집합은 XPath(XML Path Language) 식에서 반환된 네 가지 기본 데이터 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-103">Node sets are one of four basic data types that are returned from XML Path Language (XPath) expressions.</span></span> <span data-ttu-id="034e9-104">문서 순서로 만들어진 중복되지 않은 노드의 정렬되지 않은 컬렉션에 해당하는 노드 집합은 스타일시트의 변수에 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-104">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="034e9-105"><xref:System.Xml.Xsl.XslTransform> 클래스는 .NET Framework 2.0에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="034e9-106"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="034e9-107">자세한 내용은 [XslCompiledTransform 클래스 사용](using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="034e9-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="034e9-108">노드 집합은 XPath 식에서 반환된 네 가지 기본 데이터 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-108">Node sets are one of four basic data types that are returned from XPath expressions.</span></span> <span data-ttu-id="034e9-109">문서 순서로 만들어진 중복되지 않은 노드의 정렬되지 않은 컬렉션에 해당하는 노드 집합은 스타일시트의 변수에 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-109">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span> <span data-ttu-id="034e9-110">변환에서 `select` 특성에 사용된 XPath 식의 결과로 만들어진 이 노드 집합은 XML DOM(문서 개체 모델)의 노드 집합과 동일한 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-110">This node set, which is a result of an XPath expression used in a `select` attribute in a transformation, has the same behavior as a node set from the XML Document Object Model (DOM).</span></span> <span data-ttu-id="034e9-111">탐색에 <xref:System.Xml.XPath.XPathNodeIterator>를 사용하는 결과 트리 조각과는 달리 [XPathNavigator를 사용하여 노드 집합 탐색](node-set-navigation-using-xpathnavigator.md)에 표시된 메서드 집합을 사용하여 노드 집합을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-111">You can navigate a node set using a set of methods shown in [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md), unlike a result tree fragment or result tree fragment, which uses the <xref:System.Xml.XPath.XPathNodeIterator> for navigation.</span></span>  
  
 <span data-ttu-id="034e9-112">다음 코드 샘플에서는 스타일시트의 `variable` 또는 `parameter` 요소가 노드 집합으로 평가될 때 노드 집합을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="034e9-112">The following code sample shows how to iterate over a node set when a `variable` or `parameter` element in a style sheet evaluates to a node set.</span></span>  
  
## <a name="style-sheet"></a><span data-ttu-id="034e9-113">스타일시트</span><span class="sxs-lookup"><span data-stu-id="034e9-113">Style Sheet</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a><span data-ttu-id="034e9-114">입력</span><span class="sxs-lookup"><span data-stu-id="034e9-114">Input</span></span>  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a><span data-ttu-id="034e9-115">출력</span><span class="sxs-lookup"><span data-stu-id="034e9-115">Output</span></span>  
  
```output  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a><span data-ttu-id="034e9-116">참조</span><span class="sxs-lookup"><span data-stu-id="034e9-116">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="034e9-117">XslTransform 클래스를 사용하여 XSLT 변형</span><span class="sxs-lookup"><span data-stu-id="034e9-117">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="034e9-118">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="034e9-118">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
