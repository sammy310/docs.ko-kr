---
title: cref 특성 - C# 프로그래밍 가이드
description: cref 특성에 대해 알아봅니다. cref 특성은 "코드 참조"를 의미하며 태그의 내부 텍스트가 코드 요소임을 지정합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: 31fa1a3f182d7b72a1dfbe1ce47386f87fbbff75
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381998"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="0bd48-104">cref 특성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0bd48-104">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="0bd48-105">XML 문서 태그의 `cref` 특성은 "코드 참조"를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-105">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="0bd48-106">태그의 내부 텍스트를 형식, 메서드, 속성 등의 코드 요소로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-106">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="0bd48-107">[DocFX](https://dotnet.github.io/docfx/) 및 [Sandcastle](https://github.com/EWSoftware/SHFB) 등의 문서화 도구는 `cref` 특성을 사용하여 형식 또는 멤버가 문서화된 페이지에 대한 하이퍼링크를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-107">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="0bd48-108">예제</span><span class="sxs-lookup"><span data-stu-id="0bd48-108">Example</span></span>

<span data-ttu-id="0bd48-109">다음 예제에서는 [\<see>](./see.md) 태그에 사용된 `cref` 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-109">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="0bd48-110">컴파일하면 프로그램이 다음 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-110">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="0bd48-111">예를 들어 `GetZero` 메서드의 `cref` 특성은 컴파일러에서 `"M:TestNamespace.TestClass.GetZero"`로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-111">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="0bd48-112">"M:" 접두사는 "메서드"를 의미하며, DocFX 및 Sandcastle 등의 문서화 도구에서 인식되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd48-112">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="0bd48-113">접두사의 전체 목록은 [XML 파일 처리](./processing-the-xml-file.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd48-113">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="0bd48-114">참조</span><span class="sxs-lookup"><span data-stu-id="0bd48-114">See also</span></span>

- [<span data-ttu-id="0bd48-115">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="0bd48-115">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="0bd48-116">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="0bd48-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
