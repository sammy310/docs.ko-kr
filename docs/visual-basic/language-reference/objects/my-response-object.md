---
description: 다음에 대해 자세히 알아보세요. Response 개체
title: My.Response 개체
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 551528356040539994251cb66a905d0249f482da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640617"
---
# <a name="myresponse-object"></a>My.Response 개체

<xref:System.Web.HttpResponse>와 연결 된 개체를 가져옵니다 <xref:System.Web.UI.Page> . 이 개체를 사용하여 HTTP 응답 데이터를 클라이언트에 보낼 수 있고 이 개체는 해당 응답에 대한 정보를 포함합니다.  
  
## <a name="remarks"></a>설명  

 `My.Response`개체는 페이지와 관련 된 현재 개체를 포함 합니다 <xref:System.Web.HttpResponse> .  
  
 `My.Response`개체는 ASP.NET 응용 프로그램에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 개체에서 헤더 컬렉션을 가져오고 `My.Request` 개체를 사용 하 여 `My.Response` ASP.NET 페이지에 씁니다.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Web.HttpResponse>
- [My.Request 개체](my-request-object.md)
