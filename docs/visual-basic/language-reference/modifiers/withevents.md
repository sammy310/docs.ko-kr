---
description: '자세한 정보: WithEvents (Visual Basic)'
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: b27f84fe54aaa10bc9b2359cd74fad3d3ace1ad5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674768"
---
# <a name="withevents-visual-basic"></a>WithEvents(Visual Basic)

하나 이상의 선언 된 멤버 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.

## <a name="remarks"></a>설명

를 사용 하 여 변수를 정의 하는 경우 `WithEvents` 메서드가 키워드를 사용 하 여 변수의 이벤트를 처리 하도록 선언적으로 지정할 수 있습니다 `Handles` .

는 `WithEvents` 클래스 또는 모듈 수준 에서만 사용할 수 있습니다. 즉, 변수에 대 한 선언 컨텍스트는 `WithEvents` 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조 또는 프로시저일 수 없습니다.

`WithEvents`구조체 멤버에는를 사용할 수 없습니다.

에서는 배열이 아니라 개별 변수만 선언할 수 있습니다 `WithEvents` .

## <a name="rules"></a>규칙

**요소 형식.** `WithEvents`클래스 인스턴스를 사용할 수 있도록 변수를 개체 변수로 선언 해야 합니다. 그러나이를로 선언할 수는 없습니다 `Object` . 이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.

`WithEvents`이 컨텍스트에서 한정자를 사용할 수 있습니다. [Dim 문](../statements/dim-statement.md)

## <a name="example"></a>예제

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>참고 항목

- [핸들](../statements/handles-clause.md)
- [C++ 키워드](../keywords/index.md)
- [이벤트](../../programming-guide/language-features/events/index.md)
