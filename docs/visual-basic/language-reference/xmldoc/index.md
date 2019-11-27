---
title: 문서 주석에 대 한 권장 XML 태그
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 093c967557b899c8661fdec348d421996e948b94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352327"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="1057c-102">문서 주석에 대한 권장 XML 태그(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1057c-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="1057c-103">Visual Basic 컴파일러는 코드의 문서 주석을 XML 파일로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="1057c-104">추가 도구를 사용 하 여 XML 파일을 문서로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="1057c-105">형식 및 형식 멤버와 같은 코드 구문에서 XML 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="1057c-106">부분 형식의 경우 해당 멤버를 주석으로 처리 하는 데 제한이 없더라도 형식의 한 부분 에서만 XML 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1057c-107">네임 스페이스에는 문서 주석을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="1057c-108">그 이유는 한 네임 스페이스가 여러 어셈블리에 걸쳐 있을 수 있고 모든 어셈블리를 동시에 로드 해야 하는 것이 아니라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="1057c-109">컴파일러는 유효한 XML 인 모든 태그를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="1057c-110">다음 태그는 사용자 설명서에서 일반적으로 사용 되는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="1057c-111">\<c></span><span class="sxs-lookup"><span data-stu-id="1057c-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="1057c-112">\<code></span><span class="sxs-lookup"><span data-stu-id="1057c-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="1057c-113">\<example></span><span class="sxs-lookup"><span data-stu-id="1057c-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="1057c-114">[\<예외 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1057c-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="1057c-115">[> 1\<포함](../../../visual-basic/language-reference/xmldoc/include.md) <sup></sup></span><span class="sxs-lookup"><span data-stu-id="1057c-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="1057c-116">\<list></span><span class="sxs-lookup"><span data-stu-id="1057c-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="1057c-117">\<para></span><span class="sxs-lookup"><span data-stu-id="1057c-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="1057c-118">[\<매개 변수 >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1057c-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="1057c-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="1057c-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="1057c-120">[\<권한 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1057c-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="1057c-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="1057c-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="1057c-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="1057c-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="1057c-123">[> 1 참조\<](../../../visual-basic/language-reference/xmldoc/see.md) <sup></sup></span><span class="sxs-lookup"><span data-stu-id="1057c-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="1057c-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1057c-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="1057c-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="1057c-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="1057c-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1057c-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="1057c-127">\<value></span><span class="sxs-lookup"><span data-stu-id="1057c-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="1057c-128">(<sup>1</sup> 컴파일러는 구문을 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="1057c-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1057c-129">문서 주석의 텍스트에 꺾쇠 괄호를 표시 하려면 `&lt;` 및 `&gt;`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="1057c-130">예를 들어 `"&lt;text in angle brackets&gt;"` 문자열은 `<text in angle brackets>`으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1057c-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1057c-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="1057c-131">See also</span></span>

- [<span data-ttu-id="1057c-132">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="1057c-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="1057c-133">-doc</span><span class="sxs-lookup"><span data-stu-id="1057c-133">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="1057c-134">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="1057c-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
