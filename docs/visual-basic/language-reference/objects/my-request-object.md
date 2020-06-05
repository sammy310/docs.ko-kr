---
title: My.Request 개체
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 38f510e2a3958761b902f37760069aa8d595ea8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372429"
---
# <a name="myrequest-object"></a>My.Request 개체
요청된 페이지에 대한 <xref:System.Web.HttpRequest> 개체를 가져옵니다.  
  
## <a name="remarks"></a>설명  
 `My.Request` 개체에는 현재 HTTP 요청에 대한 정보가 포함됩니다.  
  
 `My.Request` 개체는 ASP.NET 애플리케이션에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 개체에서 헤더 컬렉션을 가져오고 `My.Request` 개체를 사용 하 여 `My.Response` ASP.NET 페이지에 씁니다.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Web.HttpRequest>
- [My.Response 개체](my-response-object.md)
