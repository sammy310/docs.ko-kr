---
description: '자세히 알아보기: AddHandler 문'
title: AddHandler 문
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c0c34abd7ff225765ab36278825a555e2b84b0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674105"
---
# <a name="addhandler-statement"></a>AddHandler 문

런타임에 이벤트를 이벤트 처리기와 연결 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>부분  

|||
|---|---|
|이벤트|처리할 이벤트의 이름입니다.|  
|`eventhandler`|이벤트를 처리 하는 프로시저의 이름입니다.|
|||
  
## <a name="remarks"></a>설명  

 `AddHandler`및 `RemoveHandler` 문을 사용 하면 프로그램을 실행 하는 동안 언제 든 지 이벤트 처리를 시작 하 고 중지할 수 있습니다.  
  
 프로시저의 서명은 `eventhandler` 이벤트의 시그니처와 일치 해야 합니다 `event` .  
  
 `Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다. `AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다. 특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다. 자세한 내용은 [핸들](handles-clause.md)을 참조 하세요.  
  
> [!NOTE]
> 사용자 지정 이벤트의 경우 `AddHandler` 문은 이벤트의 접근자를 호출 합니다 `AddHandler` . 사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](event-statement.md)을 참조 하십시오.  
  
## <a name="example"></a>예제  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>참고 항목

- [RemoveHandler 문](removehandler-statement.md)
- [핸들](handles-clause.md)
- [Event 문](event-statement.md)
- [이벤트](../../programming-guide/language-features/events/index.md)
