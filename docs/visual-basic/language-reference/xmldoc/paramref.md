---
title: <paramref>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3e2bf7990343a325bbecc56f6d3754a77f1e08e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940844"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="9078e-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9078e-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="9078e-103">단어를 형식을 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9078e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9078e-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9078e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9078e-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9078e-106">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="9078e-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9078e-108">설명</span><span class="sxs-lookup"><span data-stu-id="9078e-108">Remarks</span></span>  
 <span data-ttu-id="9078e-109">`<paramref>` 태그 하면 단어는 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="9078e-110">XML 파일을 다른 방식으로이 매개 변수 형식을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="9078e-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9078e-112">예제</span><span class="sxs-lookup"><span data-stu-id="9078e-112">Example</span></span>  
 <span data-ttu-id="9078e-113">이 예제에서는 합니다 `<paramref>` 참조 하는 태그를 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9078e-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9078e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="9078e-114">See also</span></span>

- [<span data-ttu-id="9078e-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="9078e-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
