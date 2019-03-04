---
title: <remarks> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 3e6625c55a6f5c29fb55bff2eb87959f3237652e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975858"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="3a253-102">\<remarks>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3a253-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="3a253-103">구문</span><span class="sxs-lookup"><span data-stu-id="3a253-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a253-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a253-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="3a253-105">멤버에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="3a253-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a253-106">주의</span><span class="sxs-lookup"><span data-stu-id="3a253-106">Remarks</span></span>  
 <span data-ttu-id="3a253-107">\<remarks> 태그는 형식에 대한 정보를 추가하여 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md)로 지정된 정보를 보완하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a253-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="3a253-108">이 정보는 개체 브라우저 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a253-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="3a253-109">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3a253-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a253-110">예제</span><span class="sxs-lookup"><span data-stu-id="3a253-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3a253-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a253-111">See also</span></span>

- [<span data-ttu-id="3a253-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3a253-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3a253-113">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="3a253-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
