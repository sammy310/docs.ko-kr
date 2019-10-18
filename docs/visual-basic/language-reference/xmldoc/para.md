---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524732"
---
# <a name="para-visual-basic"></a><span data-ttu-id="ac554-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac554-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="ac554-103">내용이 단락 형식으로 지정 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac554-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac554-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac554-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac554-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac554-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="ac554-106">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="ac554-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac554-107">주의</span><span class="sxs-lookup"><span data-stu-id="ac554-107">Remarks</span></span>  
 <span data-ttu-id="ac554-108">@No__t_0 태그는 [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), \<returns [>](../../../visual-basic/language-reference/xmldoc/returns.md)등의 태그 내에서 사용 하기 위한 것 이며 텍스트에 구조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac554-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="ac554-109">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ac554-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac554-110">예제</span><span class="sxs-lookup"><span data-stu-id="ac554-110">Example</span></span>  
 <span data-ttu-id="ac554-111">이 예제에서는 `<para>` 태그를 사용 하 여 `UpdateRecord` 메서드의 설명 섹션을 두 단락으로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac554-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ac554-112">참조</span><span class="sxs-lookup"><span data-stu-id="ac554-112">See also</span></span>

- [<span data-ttu-id="ac554-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="ac554-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
