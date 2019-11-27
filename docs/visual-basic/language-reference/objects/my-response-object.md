---
title: My.Response 개체
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 522814ad48fb7548032b8a37779bb3ff6ca62413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350653"
---
# <a name="myresponse-object"></a>My.Response 개체
<xref:System.Web.UI.Page>와 연결 된 <xref:System.Web.HttpResponse> 개체를 가져옵니다. 이 개체를 사용하여 HTTP 응답 데이터를 클라이언트에 보낼 수 있고 이 개체는 해당 응답에 대한 정보를 포함합니다.  
  
## <a name="remarks"></a>주의  
 `My.Response` 개체에는 페이지와 연결 된 현재 <xref:System.Web.HttpResponse> 개체가 포함 되어 있습니다.  
  
 `My.Response` 개체는 ASP.NET 응용 프로그램에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `My.Request` 개체에서 헤더 컬렉션을 가져온 다음 `My.Response` 개체를 사용 하 여 ASP.NET 페이지에 씁니다.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Web.HttpResponse>
- [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)
