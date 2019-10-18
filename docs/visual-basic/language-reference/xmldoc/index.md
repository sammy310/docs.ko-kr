---
title: 문서 주석에 대한 권장 XML 태그(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 7830db136e9b900458496b36df5bc37f76661129
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523969"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="c87b0-102">문서 주석에 대한 권장 XML 태그(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c87b0-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="c87b0-103">Visual Basic 컴파일러는 코드의 문서 주석을 XML 파일로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="c87b0-104">추가 도구를 사용 하 여 XML 파일을 문서로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="c87b0-105">형식 및 형식 멤버와 같은 코드 구문에서 XML 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="c87b0-106">부분 형식의 경우 해당 멤버를 주석으로 처리 하는 데 제한이 없더라도 형식의 한 부분 에서만 XML 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c87b0-107">네임 스페이스에는 문서 주석을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="c87b0-108">그 이유는 한 네임 스페이스가 여러 어셈블리에 걸쳐 있을 수 있고 모든 어셈블리를 동시에 로드 해야 하는 것이 아니라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="c87b0-109">컴파일러는 유효한 XML 인 모든 태그를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="c87b0-110">다음 태그는 사용자 설명서에서 일반적으로 사용 되는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="c87b0-111">\<c></span><span class="sxs-lookup"><span data-stu-id="c87b0-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="c87b0-112">\<code></span><span class="sxs-lookup"><span data-stu-id="c87b0-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="c87b0-113">\<example></span><span class="sxs-lookup"><span data-stu-id="c87b0-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="c87b0-114">[\<exception >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="c87b0-115">[\<include >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="c87b0-116">\<list></span><span class="sxs-lookup"><span data-stu-id="c87b0-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="c87b0-117">\<para></span><span class="sxs-lookup"><span data-stu-id="c87b0-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="c87b0-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="c87b0-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="c87b0-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="c87b0-120">[\<permission >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="c87b0-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="c87b0-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="c87b0-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="c87b0-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="c87b0-123">[\<see >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="c87b0-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="c87b0-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="c87b0-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="c87b0-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c87b0-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="c87b0-127">\<value></span><span class="sxs-lookup"><span data-stu-id="c87b0-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="c87b0-128">(<sup>1</sup> 컴파일러는 구문을 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="c87b0-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c87b0-129">문서 주석의 텍스트에 꺾쇠 괄호를 표시 하려면 `&lt;` 및 `&gt;`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="c87b0-130">예를 들어 `"&lt;text in angle brackets&gt;"` 문자열은 `<text in angle brackets>`으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87b0-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87b0-131">참조</span><span class="sxs-lookup"><span data-stu-id="c87b0-131">See also</span></span>

- [<span data-ttu-id="c87b0-132">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="c87b0-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="c87b0-133">-doc</span><span class="sxs-lookup"><span data-stu-id="c87b0-133">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="c87b0-134">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="c87b0-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
