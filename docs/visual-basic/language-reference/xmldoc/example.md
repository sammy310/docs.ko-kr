---
description: 다음에 대해 자세히 알아보세요. <example> (Visual Basic)
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 643e06fd24e38123dd2693d671b9ab33da5b413e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787489"
---
# <a name="example-visual-basic"></a><span data-ttu-id="88eb8-103">\<example>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88eb8-103">\<example> (Visual Basic)</span></span>

<span data-ttu-id="88eb8-104">멤버에 대 한 예제를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88eb8-104">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88eb8-105">구문</span><span class="sxs-lookup"><span data-stu-id="88eb8-105">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="88eb8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88eb8-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="88eb8-107">코드 샘플에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="88eb8-107">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88eb8-108">설명</span><span class="sxs-lookup"><span data-stu-id="88eb8-108">Remarks</span></span>  

 <span data-ttu-id="88eb8-109">`<example>` 태그를 사용하면 메서드 또는 기타 라이브러리 멤버를 사용하는 방법의 예제를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88eb8-109">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="88eb8-110">여기에는 일반적으로 [\<code>](code.md) 태그를 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88eb8-110">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="88eb8-111">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="88eb8-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88eb8-112">예제</span><span class="sxs-lookup"><span data-stu-id="88eb8-112">Example</span></span>  

 <span data-ttu-id="88eb8-113">이 예제에서는 태그를 사용 하 여 `<example>` 필드 사용에 대 한 예제를 포함 합니다 `ID` .</span><span class="sxs-lookup"><span data-stu-id="88eb8-113">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="88eb8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88eb8-114">See also</span></span>

- [<span data-ttu-id="88eb8-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="88eb8-115">XML Comment Tags</span></span>](index.md)
