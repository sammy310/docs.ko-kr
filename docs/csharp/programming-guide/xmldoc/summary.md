---
title: <summary> - C# 프로그래밍 가이드
description: XML <summary> 태그에 대해 알아봅니다. 이 태그는 형식 또는 형식 멤버를 설명하는 데 사용됩니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: e20970971636f13357c165f3065050fcf5914ada
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477709"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="f9ca6-105">\<summary>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f9ca6-105">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="f9ca6-106">구문</span><span class="sxs-lookup"><span data-stu-id="f9ca6-106">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="f9ca6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9ca6-107">Parameters</span></span>

- `description`

  <span data-ttu-id="f9ca6-108">개체에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-108">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9ca6-109">설명</span><span class="sxs-lookup"><span data-stu-id="f9ca6-109">Remarks</span></span>

<span data-ttu-id="f9ca6-110">`<summary>` 태그를 사용하여 형식 또는 형식 멤버를 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-110">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="f9ca6-111">[\<remarks>](./remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-111">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="f9ca6-112">[cref 특성](./cref-attribute.md)을 사용하면 [DocFX](https://dotnet.github.io/docfx/) 및 [Sandcastle](https://github.com/EWSoftware/SHFB) 등의 문서화 도구를 통해 코드 요소의 문서화 페이지에 대한 내부 하이퍼링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-112">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="f9ca6-113">`<summary>` 태그의 텍스트는 IntelliSense의 형식에 대한 유일한 정보 소스이며 개체 브라우저 창에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-113">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="f9ca6-114">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-114">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span> <span data-ttu-id="f9ca6-115">컴파일러에서 생성한 파일을 기반으로 해서 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [DocFX](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-115">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="f9ca6-116">예제</span><span class="sxs-lookup"><span data-stu-id="f9ca6-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="f9ca6-117">앞의 예제에서는 다음 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            </summary>
            <seealso cref="M:TestClass.Main"/>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="cref-example"></a><span data-ttu-id="f9ca6-118">cref 예</span><span class="sxs-lookup"><span data-stu-id="f9ca6-118">cref example</span></span>

<span data-ttu-id="f9ca6-119">다음 예제에서는 제네릭 형식에 대한 `cref` 참조를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-119">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="f9ca6-120">앞의 예제에서는 다음 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ca6-120">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="f9ca6-121">참조</span><span class="sxs-lookup"><span data-stu-id="f9ca6-121">See also</span></span>

- [<span data-ttu-id="f9ca6-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f9ca6-122">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="f9ca6-123">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="f9ca6-123">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
