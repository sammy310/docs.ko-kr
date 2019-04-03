---
title: My.Response 개체 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 2f72f493d99c1e0b0469150c041649486e5ed124
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818997"
---
# <a name="myresponse-object"></a><span data-ttu-id="21a61-102">My.Response 개체</span><span class="sxs-lookup"><span data-stu-id="21a61-102">My.Response Object</span></span>
<span data-ttu-id="21a61-103">가져옵니다 합니다 <xref:System.Web.HttpResponse> 연관 된 개체는 <xref:System.Web.UI.Page>합니다.</span><span class="sxs-lookup"><span data-stu-id="21a61-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="21a61-104">이 개체를 사용하여 HTTP 응답 데이터를 클라이언트에 보낼 수 있고 이 개체는 해당 응답에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="21a61-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21a61-105">설명</span><span class="sxs-lookup"><span data-stu-id="21a61-105">Remarks</span></span>  
 <span data-ttu-id="21a61-106">합니다 `My.Response` 개체에 현재 포함 되어 <xref:System.Web.HttpResponse> 페이지와 연결 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="21a61-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="21a61-107">합니다 `My.Response` 개체는 사용할 수만 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="21a61-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21a61-108">예제</span><span class="sxs-lookup"><span data-stu-id="21a61-108">Example</span></span>  
 <span data-ttu-id="21a61-109">다음 예제에서 헤더 컬렉션을 가져옵니다 합니다 `My.Request` 사용 하 여 개체를 `My.Response` ASP.NET 페이지에 쓸 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="21a61-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="21a61-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="21a61-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="21a61-111">My.Request 개체</span><span class="sxs-lookup"><span data-stu-id="21a61-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
