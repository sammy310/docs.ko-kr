---
title: 문서 주석에 대한 권장 태그 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: ac8629dacbb8c1fde1f55468e5d2aeaf78cfe017
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928034"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="14c16-102">문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="14c16-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="14c16-103">C# 컴파일러는 코드의 문서 주석을 처리하고 **/doc** 명령줄 옵션에서 지정한 이름의 파일에 XML로 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="14c16-104">컴파일러에서 생성한 파일을 기반으로 해서 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [DocFX](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="14c16-105">태그는 형식, 형식 멤버 등의 코드 구문에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14c16-106">네임스페이스에는 문서 주석을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="14c16-107">컴파일러는 유효한 XML인 태그를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="14c16-108">다음 태그는 사용자 문서에서 일반적으로 사용되는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="14c16-109">Tags</span><span class="sxs-lookup"><span data-stu-id="14c16-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="14c16-110">\<c></span><span class="sxs-lookup"><span data-stu-id="14c16-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="14c16-111">\<para></span><span class="sxs-lookup"><span data-stu-id="14c16-111">\<para></span></span>](./para.md)|<span data-ttu-id="14c16-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="14c16-113">\<code></span><span class="sxs-lookup"><span data-stu-id="14c16-113">\<code></span></span>](./code.md)|<span data-ttu-id="14c16-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="14c16-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="14c16-116">\<example></span><span class="sxs-lookup"><span data-stu-id="14c16-116">\<example></span></span>](./example.md)|[<span data-ttu-id="14c16-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="14c16-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="14c16-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="14c16-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="14c16-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="14c16-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="14c16-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="14c16-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="14c16-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="14c16-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="14c16-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="14c16-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="14c16-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="14c16-125">\<list></span><span class="sxs-lookup"><span data-stu-id="14c16-125">\<list></span></span>](./list.md)|[<span data-ttu-id="14c16-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="14c16-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="14c16-127">\<value></span><span class="sxs-lookup"><span data-stu-id="14c16-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="14c16-128">(\* 컴파일러에서 구문을 확인함을 나타냅니다.)</span><span class="sxs-lookup"><span data-stu-id="14c16-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="14c16-129">문서 주석의 텍스트에 꺾쇠 괄호를 표시하려면 각각 `&lt;` 및 `&gt;`인 `<` 및 `>`의 HTML 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="14c16-130">이 인코딩은 다음 예제에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c16-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="14c16-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14c16-131">See also</span></span>

- [<span data-ttu-id="14c16-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="14c16-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="14c16-133">/doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="14c16-133">/doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="14c16-134">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="14c16-134">XML Documentation Comments</span></span>](./index.md)
