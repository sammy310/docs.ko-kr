---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348506"
---
# <a name="c-visual-basic"></a><span data-ttu-id="1c3b5-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c3b5-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="1c3b5-102">Indicates that text within a description is code.</span><span class="sxs-lookup"><span data-stu-id="1c3b5-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c3b5-103">구문</span><span class="sxs-lookup"><span data-stu-id="1c3b5-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c3b5-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c3b5-104">Parameters</span></span>  
  
|<span data-ttu-id="1c3b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c3b5-105">Parameter</span></span>|<span data-ttu-id="1c3b5-106">설명</span><span class="sxs-lookup"><span data-stu-id="1c3b5-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="1c3b5-107">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3b5-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c3b5-108">주의</span><span class="sxs-lookup"><span data-stu-id="1c3b5-108">Remarks</span></span>  
 <span data-ttu-id="1c3b5-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span><span class="sxs-lookup"><span data-stu-id="1c3b5-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="1c3b5-110">여러 줄을 코드로 지정하려면 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3b5-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="1c3b5-111">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3b5-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c3b5-112">예제</span><span class="sxs-lookup"><span data-stu-id="1c3b5-112">Example</span></span>  
 <span data-ttu-id="1c3b5-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span><span class="sxs-lookup"><span data-stu-id="1c3b5-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c3b5-114">참조</span><span class="sxs-lookup"><span data-stu-id="1c3b5-114">See also</span></span>

- [<span data-ttu-id="1c3b5-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="1c3b5-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
