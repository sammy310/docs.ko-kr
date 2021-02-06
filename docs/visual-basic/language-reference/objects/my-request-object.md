---
description: 다음에 대해 자세히 알아보세요. Request 개체
title: My.Request 개체
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 0b72252e261cd033bfc35c546de5c53a4f3cfe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640656"
---
# <a name="myrequest-object"></a><span data-ttu-id="512c7-103">My.Request 개체</span><span class="sxs-lookup"><span data-stu-id="512c7-103">My.Request Object</span></span>

<span data-ttu-id="512c7-104">요청된 페이지에 대한 <xref:System.Web.HttpRequest> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="512c7-104">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="512c7-105">설명</span><span class="sxs-lookup"><span data-stu-id="512c7-105">Remarks</span></span>  

 <span data-ttu-id="512c7-106">`My.Request` 개체에는 현재 HTTP 요청에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="512c7-106">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="512c7-107">`My.Request` 개체는 ASP.NET 애플리케이션에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="512c7-107">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="512c7-108">예제</span><span class="sxs-lookup"><span data-stu-id="512c7-108">Example</span></span>  

 <span data-ttu-id="512c7-109">다음 예제에서는 개체에서 헤더 컬렉션을 가져오고 `My.Request` 개체를 사용 하 여 `My.Response` ASP.NET 페이지에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="512c7-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="512c7-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="512c7-110">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="512c7-111">My.Response 개체</span><span class="sxs-lookup"><span data-stu-id="512c7-111">My.Response Object</span></span>](my-response-object.md)
