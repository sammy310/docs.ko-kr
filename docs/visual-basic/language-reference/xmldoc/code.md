---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524031"
---
# <a name="code-visual-basic"></a><span data-ttu-id="291e5-101">\<code > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="291e5-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="291e5-102">텍스트가 여러 줄의 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="291e5-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="291e5-103">구문</span><span class="sxs-lookup"><span data-stu-id="291e5-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="291e5-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="291e5-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="291e5-105">코드로 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="291e5-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="291e5-106">주의</span><span class="sxs-lookup"><span data-stu-id="291e5-106">Remarks</span></span>  
 <span data-ttu-id="291e5-107">@No__t_0 태그를 사용 하 여 여러 줄을 코드로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="291e5-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="291e5-108">설명 내의 텍스트가 코드로 표시되도록 지정하려면 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="291e5-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="291e5-109">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="291e5-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="291e5-110">예제</span><span class="sxs-lookup"><span data-stu-id="291e5-110">Example</span></span>  
 <span data-ttu-id="291e5-111">이 예제에서는 \<code > 태그를 사용 하 여 `ID` 필드를 사용 하는 예제 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="291e5-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="291e5-112">참조</span><span class="sxs-lookup"><span data-stu-id="291e5-112">See also</span></span>

- [<span data-ttu-id="291e5-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="291e5-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
