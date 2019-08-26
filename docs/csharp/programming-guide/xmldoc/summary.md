---
title: <summary> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 4a509c002bb6a55b4751712925ae7cc613911af2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587623"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="c08ca-102">\<summary>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c08ca-102">\<summary> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c08ca-103">구문</span><span class="sxs-lookup"><span data-stu-id="c08ca-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c08ca-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c08ca-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c08ca-105">개체에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c08ca-106">설명</span><span class="sxs-lookup"><span data-stu-id="c08ca-106">Remarks</span></span>  
 <span data-ttu-id="c08ca-107">\<summary > 태그를 사용하여 형식 또는 형식 멤버를 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="c08ca-108">[\<remarks>](./remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="c08ca-109">[cref 특성](./cref-attribute.md)을 사용하면 [DocFX](https://dotnet.github.io/docfx/) 및 [Sandcastle](https://github.com/EWSoftware/SHFB) 등의 문서화 도구를 통해 코드 요소의 문서화 페이지에 대한 내부 하이퍼링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="c08ca-110">\<summary> 태그의 텍스트는 IntelliSense의 형식에 대한 유일한 정보 소스이며 개체 브라우저 창에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="c08ca-111">[/doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-111">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="c08ca-112">컴파일러에서 생성한 파일을 기반으로 해서 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [DocFX](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c08ca-113">예</span><span class="sxs-lookup"><span data-stu-id="c08ca-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
 <span data-ttu-id="c08ca-114">앞의 예제에서는 다음 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="c08ca-115">예</span><span class="sxs-lookup"><span data-stu-id="c08ca-115">Example</span></span>  
 <span data-ttu-id="c08ca-116">다음 예제에서는 제네릭 형식에 대한 `cref` 참조를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]  
  
 <span data-ttu-id="c08ca-117">앞의 예제에서는 다음 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ca-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c08ca-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c08ca-118">See also</span></span>

- [<span data-ttu-id="c08ca-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c08ca-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c08ca-120">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="c08ca-120">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
