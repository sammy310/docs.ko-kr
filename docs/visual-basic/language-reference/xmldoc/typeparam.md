---
description: 다음에 대해 자세히 알아보세요. <typeparam> (Visual Basic)
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: efb4394ee2badcf52bac75d7d9e317c732789746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640266"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="408cb-103">\<typeparam>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="408cb-103">\<typeparam> (Visual Basic)</span></span>

<span data-ttu-id="408cb-104">형식 매개 변수 이름 및 설명을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="408cb-104">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="408cb-105">구문</span><span class="sxs-lookup"><span data-stu-id="408cb-105">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="408cb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="408cb-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="408cb-107">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="408cb-107">The name of the type parameter.</span></span> <span data-ttu-id="408cb-108">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="408cb-108">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="408cb-109">형식 매개 변수에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="408cb-109">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="408cb-110">설명</span><span class="sxs-lookup"><span data-stu-id="408cb-110">Remarks</span></span>  

 <span data-ttu-id="408cb-111">`<typeparam>`제네릭 형식 또는 제네릭 멤버 선언에 대 한 주석의 태그를 사용 하 여 형식 매개 변수 중 하나를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="408cb-111">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="408cb-112">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="408cb-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="408cb-113">예제</span><span class="sxs-lookup"><span data-stu-id="408cb-113">Example</span></span>  

 <span data-ttu-id="408cb-114">이 예제에서는 태그를 사용 하 여 `<typeparam>` 매개 변수를 설명 합니다 `id` .</span><span class="sxs-lookup"><span data-stu-id="408cb-114">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="408cb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="408cb-115">See also</span></span>

- [<span data-ttu-id="408cb-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="408cb-116">XML Comment Tags</span></span>](index.md)
