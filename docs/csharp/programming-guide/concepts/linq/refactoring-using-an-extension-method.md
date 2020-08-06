---
title: 확장 메서드를 사용하여 리팩터링(C#)
description: 확장 메서드를 사용하여 코드를 리팩터링하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
ms.assetid: c5fc123d-af10-4a2f-b8e4-db921efb2639
ms.openlocfilehash: e786f0e1514156535fd6a6033e37ed8879e99709
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381946"
---
# <a name="refactoring-using-an-extension-method-c"></a><span data-ttu-id="17066-104">확장 메서드를 사용하여 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="17066-104">Refactoring Using an Extension Method (C#)</span></span>
<span data-ttu-id="17066-105">이 예제는 확장 메서드로 구현된 순수 함수를 사용하여 문자열의 연결을 리팩터링하는 방법으로 이전 예제인 [단락의 텍스트 검색(C#)](./retrieving-the-text-of-the-paragraphs.md)을 기반으로 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-105">This example builds on the previous example, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="17066-106">이전 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A> 표준 쿼리 연산자를 사용하여 여러 문자열을 한 문자열로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-106">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="17066-107">그러나 생성되는 쿼리가 더 작고 간단하기 때문에 이 작업을 수행하는 확장 메서드를 작성하는 것이 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-107">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17066-108">예제</span><span class="sxs-lookup"><span data-stu-id="17066-108">Example</span></span>  
 <span data-ttu-id="17066-109">이 예제에서는 WordprocessingML 문서를 처리하여 단락, 각 단락의 스타일 및 각 단락의 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-109">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="17066-110">이 예제는 이 자습서의 이전 예제를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-110">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="17066-111">이 예제에는 `StringConcatenate` 메서드의 오버로드가 여러 개 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-111">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="17066-112">이 예제의 소스 문서 만들기에 대한 지침은 [원본 Office Open XML 문서 만들기(C#)](./creating-the-source-office-open-xml-document.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-112">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="17066-113">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="17066-113">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="17066-114"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-114">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="17066-115">예제</span><span class="sxs-lookup"><span data-stu-id="17066-115">Example</span></span>  
 <span data-ttu-id="17066-116">`StringConcatenate` 메서드의 오버로드는 네 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-116">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="17066-117">한 오버로드는 문자열의 컬렉션을 가져와서 단일 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-117">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="17066-118">다른 오버로드는 원하는 형식의 컬렉션과 컬렉션의 singleton에서 문자열로 프로젝션하는 대리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-118">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="17066-119">나머지 두 오버로드는 구분 기호 문자열을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-119">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="17066-120">다음 코드에서는 네 오버로드를 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-120">The following code uses all four overloads.</span></span>  
  
```csharp  
string[] numbers = { "one", "two", "three" };  
  
Console.WriteLine("{0}", numbers.StringConcatenate());  
Console.WriteLine("{0}", numbers.StringConcatenate(":"));  
  
int[] intNumbers = { 1, 2, 3 };  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString()));  
Console.WriteLine("{0}", intNumbers.StringConcatenate(i => i.ToString(), ":"));  
```  
  
 <span data-ttu-id="17066-121">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-121">This example produces the following output:</span></span>  
  
```output  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="17066-122">예제</span><span class="sxs-lookup"><span data-stu-id="17066-122">Example</span></span>  
 <span data-ttu-id="17066-123">이제 새 확장명 메서드를 활용하기 위해 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-123">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
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
                    Uri styleUri =  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
            }  
        }  
  
        string defaultStyle =  
            (string)(  
                from style in styleDoc.Root.Elements(w + "style")  
                where (string)style.Attribute(w + "type") == "paragraph" &&  
                      (string)style.Attribute(w + "default") == "1"  
                select style  
            ).First().Attribute(w + "styleId");  
  
        // Find all paragraphs in the document.  
        var paragraphs =  
            from para in xDoc  
                         .Root  
                         .Element(w + "body")  
                         .Descendants(w + "p")  
            let styleNode = para  
                            .Elements(w + "pPr")  
                            .Elements(w + "pStyle")  
                            .FirstOrDefault()  
            select new  
            {  
                ParagraphNode = para,  
                StyleName = styleNode != null ?  
                    (string)styleNode.Attribute(w + "val") :  
                    defaultStyle  
            };  
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = para  
                       .ParagraphNode  
                       .Elements(w + "r")  
                       .Elements(w + "t")  
                       .StringConcatenate(e => (string)e)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="17066-124">[원본 Office Open XML 문서 만들기(C#)](./creating-the-source-office-open-xml-document.md)에서 설명하는 문서에 적용할 경우 이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="17066-124">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
 <span data-ttu-id="17066-125">이 리팩터링은 순수 함수로의 리팩터링에 대한 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="17066-125">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="17066-126">다음 항목에서는 순수 함수로의 팩터링 개념에 대해 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="17066-126">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="17066-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="17066-127">Next Steps</span></span>  
 <span data-ttu-id="17066-128">다음 예제에서는 순수 함수를 사용하여 다른 방식으로 이 코드를 리팩터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17066-128">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
- [<span data-ttu-id="17066-129">순수 함수를 사용하여 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="17066-129">Refactoring Using a Pure Function (C#)</span></span>](./refactoring-using-a-pure-function.md)
  
## <a name="see-also"></a><span data-ttu-id="17066-130">참조</span><span class="sxs-lookup"><span data-stu-id="17066-130">See also</span></span>

- [<span data-ttu-id="17066-131">자습서: WordprocessingML 문서에서 내용 조작(C#)</span><span class="sxs-lookup"><span data-stu-id="17066-131">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="17066-132">순수 함수로 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="17066-132">Refactoring Into Pure Functions (C#)</span></span>](./refactoring-into-pure-functions.md)
