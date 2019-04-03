---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 16d10b2f955a4d9a02075ee4cc40dfa2b18c3541
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814512"
---
# <a name="para-visual-basic"></a><span data-ttu-id="9e064-102">\<p a r a > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e064-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="9e064-103">콘텐츠를 단락으로 형식이 지정 되었는지 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e064-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e064-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e064-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e064-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e064-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="9e064-106">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="9e064-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e064-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e064-107">Remarks</span></span>  
 <span data-ttu-id="9e064-108">합니다 `<para>` 태그와 같은 태그 내에서 사용 하기 위한 것 [ \<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md)를 [ \<설명 >](../../../visual-basic/language-reference/xmldoc/remarks.md), 또는 [ \<반환 >](../../../visual-basic/language-reference/xmldoc/returns.md), 텍스트에 구조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e064-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="9e064-109">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e064-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e064-110">예제</span><span class="sxs-lookup"><span data-stu-id="9e064-110">Example</span></span>  
 <span data-ttu-id="9e064-111">이 예제에서는 합니다 `<para>` 태그에 대 한 설명 부분을 분할 하는 `UpdateRecord` 두 단락 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e064-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9e064-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e064-112">See also</span></span>

- [<span data-ttu-id="9e064-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="9e064-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
