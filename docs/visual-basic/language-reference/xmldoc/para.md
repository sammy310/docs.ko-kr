---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352309"
---
# <a name="para-visual-basic"></a><span data-ttu-id="c1aa3-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1aa3-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="c1aa3-102">Specifies that the content is formatted as a paragraph.</span><span class="sxs-lookup"><span data-stu-id="c1aa3-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1aa3-103">구문</span><span class="sxs-lookup"><span data-stu-id="c1aa3-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1aa3-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1aa3-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="c1aa3-105">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c1aa3-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1aa3-106">주의</span><span class="sxs-lookup"><span data-stu-id="c1aa3-106">Remarks</span></span>  
 <span data-ttu-id="c1aa3-107">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span><span class="sxs-lookup"><span data-stu-id="c1aa3-107">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="c1aa3-108">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c1aa3-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1aa3-109">예제</span><span class="sxs-lookup"><span data-stu-id="c1aa3-109">Example</span></span>  
 <span data-ttu-id="c1aa3-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span><span class="sxs-lookup"><span data-stu-id="c1aa3-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c1aa3-111">참조</span><span class="sxs-lookup"><span data-stu-id="c1aa3-111">See also</span></span>

- [<span data-ttu-id="c1aa3-112">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="c1aa3-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
