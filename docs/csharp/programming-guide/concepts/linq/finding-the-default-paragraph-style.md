---
title: 기본 단락 스타일 찾기(C#)
description: C#에서 LINQ를 사용하여 WordprocessingML 문서를 처리하는 방법을 알아봅니다. 이 예제에서는 문서에 있는 단락의 기본 스타일을 찾습니다.
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: e18bbbdbd5b2627c9ff4c3c3eedd84d7cb166a62
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103824"
---
# <a name="finding-the-default-paragraph-style-c"></a><span data-ttu-id="168b6-104">기본 단락 스타일 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="168b6-104">Finding the Default Paragraph Style (C#)</span></span>
<span data-ttu-id="168b6-105">WordprocessingML 문서에서 정보 조작 자습서의 첫 번째 작업은 문서에 있는 단락의 기본 스타일을 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-105">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="168b6-106">예제</span><span class="sxs-lookup"><span data-stu-id="168b6-106">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="168b6-107">Description</span><span class="sxs-lookup"><span data-stu-id="168b6-107">Description</span></span>  
 <span data-ttu-id="168b6-108">다음 예제에서는 Office Open XML WordprocessingML 문서를 열고 패키지의 문서 및 스타일 부분을 찾은 다음 기본 스타일 이름을 찾는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-108">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="168b6-109">Office Open XML 문서 패키지와 패키지를 구성하는 부분에 대한 자세한 내용은 [Office Open XML WordprocessingML 문서 정보(C#)](./wordprocessingml-document-with-styles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="168b6-109">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (C#)](./wordprocessingml-document-with-styles.md).</span></span>  
  
 <span data-ttu-id="168b6-110">쿼리에서는 값이 "paragraph"인 `w:style` 특성과 값이 "1"인 `w:type` 특성을 가진 `w:default`이라는 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-110">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="168b6-111">이러한 특성을 가진 XML 노드는 하나뿐이기 때문에 쿼리에서는 <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> 연산자를 사용하여 컬렉션을 singleton으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-111">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="168b6-112">그런 다음 이름이 `w:styleId`인 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-112">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="168b6-113">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="168b6-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="168b6-114"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="168b6-115">코드</span><span class="sxs-lookup"><span data-stu-id="168b6-115">Code</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a><span data-ttu-id="168b6-116">주석</span><span class="sxs-lookup"><span data-stu-id="168b6-116">Comments</span></span>  
 <span data-ttu-id="168b6-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-117">This example produces the following output:</span></span>  
  
```output  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="168b6-118">다음 단계</span><span class="sxs-lookup"><span data-stu-id="168b6-118">Next Steps</span></span>  
 <span data-ttu-id="168b6-119">다음 예제에서는 문서의 모든 단락과 단락의 스타일을 찾는 유사한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="168b6-119">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="168b6-120">단락 및 해당 스타일 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="168b6-120">Retrieving the Paragraphs and Their Styles (C#)</span></span>](./retrieving-the-paragraphs-and-their-styles.md)  
