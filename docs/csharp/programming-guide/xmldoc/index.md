---
title: XML 문서 주석 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: 6405b094ccc50499bfeb4db4522f0ec9b01f68ad
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523488"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="49231-102">XML 문서 주석(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="49231-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="49231-103">Visual C#에서는 주석이 참조하는 코드 블록 바로 앞의 소스 코드의 특별 주석 필드(세 개의 슬래시로 표시)에 XML 요소를 포함하여 코드에 대한 문서를 만들 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="49231-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="49231-104">[-설명서](../../language-reference/compiler-options/doc-compiler-option.md) 옵션을 사용하여 컴파일하는 경우 컴파일러는 소스 코드에서 모든 XML 태그를 검색하고 XML 문서 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="49231-104">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="49231-105">컴파일러에서 생성한 파일을 기반으로 해서 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [DocFX](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49231-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="49231-106">XML 요소를 참조하려면(예를 들어, 함수가 XML 문서 주석에서 설명하려는 특정 XML 요소를 처리하는 경우) 표준 인용 메커니즘(`<` 및 `>`)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49231-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="49231-107">코드 참조(`cref`) 요소에서 제네릭 식별자를 참조하려면 이스케이프 문자(예: `cref="List&lt;T&gt;"`) 또는 괄호(`cref="List{T}"`)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49231-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="49231-108">특별한 경우로, 컴파일러는 제네릭 식별자를 참조할 때 문서 주석을 더 쉽게 작성할 수 있도록 괄호를 꺾쇠 괄호로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="49231-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49231-109">XML 문서 주석은 메타데이터가 아닙니다. 이러한 주석은 컴파일된 어셈블리에 포함되지 않으므로 리플렉션을 통해 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49231-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49231-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="49231-110">In This Section</span></span>  
  
- [<span data-ttu-id="49231-111">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="49231-111">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)  
  
- [<span data-ttu-id="49231-112">XML 파일 처리</span><span class="sxs-lookup"><span data-stu-id="49231-112">Processing the XML File</span></span>](./processing-the-xml-file.md)  
  
- [<span data-ttu-id="49231-113">문서 태그에 대한 구분 기호</span><span class="sxs-lookup"><span data-stu-id="49231-113">Delimiters for Documentation Tags</span></span>](./delimiters-for-documentation-tags.md)  
  
- [<span data-ttu-id="49231-114">방법: XML 문서 기능 사용</span><span class="sxs-lookup"><span data-stu-id="49231-114">How to: Use the XML Documentation Features</span></span>](./how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="49231-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="49231-115">Related Sections</span></span>  
 <span data-ttu-id="49231-116">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49231-116">For more information, see:</span></span>  
  
- [<span data-ttu-id="49231-117">-설명서(문서 주석 처리)</span><span class="sxs-lookup"><span data-stu-id="49231-117">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="49231-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="49231-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="49231-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49231-119">See also</span></span>

- [<span data-ttu-id="49231-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="49231-120">C# Programming Guide</span></span>](../index.md)
