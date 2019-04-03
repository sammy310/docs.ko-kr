---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c5c088472ae09a416953d9c0829cad1cb48646b8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833492"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="e0700-102">\<설명 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0700-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="e0700-103">멤버에 대 한 설명 부분을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0700-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0700-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0700-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0700-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e0700-106">멤버에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0700-107">설명</span><span class="sxs-lookup"><span data-stu-id="e0700-107">Remarks</span></span>  
 <span data-ttu-id="e0700-108">사용 된 `<remarks>` 태그를 사용 하 여 지정 된 정보를 보완 하는 형식에 대 한 정보를 추가 [ \<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="e0700-109">이 정보는 개체 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="e0700-110">개체 브라우저에 대 한 정보를 참조 하세요 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="e0700-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0700-112">예제</span><span class="sxs-lookup"><span data-stu-id="e0700-112">Example</span></span>  
 <span data-ttu-id="e0700-113">이 예제에서는 `<remarks>` 기능을 설명 하는 태그를 `UpdateRecord` 메서드는 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0700-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e0700-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0700-114">See also</span></span>

- [<span data-ttu-id="e0700-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="e0700-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
