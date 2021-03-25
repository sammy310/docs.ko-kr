---
title: 문서 주석에 대한 권장 태그 - C# 프로그래밍 가이드
description: 문서 주석용 권장 태그에 대해 알아봅니다. 권장 태그 목록 및 사용 가능한 추가 리소스를 확인합니다.
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 74fd18a09458c399aa135552e5f6f0bca359f09e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477840"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="dec91-104">문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="dec91-104">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="dec91-105">C# 컴파일러는 코드의 문서 주석을 처리하고 **/doc** 명령줄 옵션에서 지정한 이름의 파일에 XML로 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-105">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="dec91-106">컴파일러에서 생성한 파일을 기반으로 해서 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [DocFX](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-106">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="dec91-107">태그는 형식, 형식 멤버 등의 코드 구문에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-107">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="dec91-108">네임스페이스에는 문서 주석을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-108">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="dec91-109">컴파일러는 유효한 XML인 태그를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-109">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="dec91-110">다음 태그는 사용자 문서에서 일반적으로 사용되는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-110">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="dec91-111">Tags</span><span class="sxs-lookup"><span data-stu-id="dec91-111">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
<span data-ttu-id="dec91-112">(\* 컴파일러에서 구문을 확인함을 나타냅니다.)</span><span class="sxs-lookup"><span data-stu-id="dec91-112">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="dec91-113">문서 주석의 텍스트에 꺾쇠 괄호를 표시하려면 각각 `&lt;` 및 `&gt;`인 `<` 및 `>`의 HTML 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-113">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="dec91-114">이 인코딩은 다음 예제에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec91-114">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="dec91-115">참조</span><span class="sxs-lookup"><span data-stu-id="dec91-115">See also</span></span>

- [<span data-ttu-id="dec91-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dec91-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="dec91-117">**DocumentationFile**(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="dec91-117">**DocumentationFile** (C# compiler options)</span></span>](../../language-reference/compiler-options/output.md#documentationfile)
- [<span data-ttu-id="dec91-118">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="dec91-118">XML documentation comments</span></span>](./index.md)
