---
title: <c>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523932"
---
# <a name="c-visual-basic"></a><span data-ttu-id="50dc6-102">\<c > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50dc6-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="50dc6-103">설명의 텍스트가 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50dc6-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50dc6-104">구문</span><span class="sxs-lookup"><span data-stu-id="50dc6-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="50dc6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50dc6-105">Parameters</span></span>  
  
|<span data-ttu-id="50dc6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50dc6-106">Parameter</span></span>|<span data-ttu-id="50dc6-107">설명</span><span class="sxs-lookup"><span data-stu-id="50dc6-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="50dc6-108">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="50dc6-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50dc6-109">주의</span><span class="sxs-lookup"><span data-stu-id="50dc6-109">Remarks</span></span>  
 <span data-ttu-id="50dc6-110">@No__t_0 태그는 설명 내의 텍스트를 코드로 표시 하도록 지정 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50dc6-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="50dc6-111">여러 줄을 코드로 지정하려면 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50dc6-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="50dc6-112">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="50dc6-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50dc6-113">예제</span><span class="sxs-lookup"><span data-stu-id="50dc6-113">Example</span></span>  
 <span data-ttu-id="50dc6-114">이 예제에서는 요약 섹션의 `<c>` 태그를 사용 하 여 `Counter` 코드 임을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="50dc6-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="50dc6-115">참조</span><span class="sxs-lookup"><span data-stu-id="50dc6-115">See also</span></span>

- [<span data-ttu-id="50dc6-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="50dc6-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
