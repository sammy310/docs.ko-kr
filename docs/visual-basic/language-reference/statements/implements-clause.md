---
description: '자세한 정보: Implements 절 (Visual Basic)'
title: Implements 절
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 360d8812a7c49d6462818246b1448e171dcd597f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769002"
---
# <a name="implements-clause-visual-basic"></a>Implements 절(Visual Basic)

클래스 또는 구조체 멤버가 인터페이스에 정의 된 멤버에 대 한 구현을 제공 함을 나타냅니다.  
  
## <a name="remarks"></a>설명  

`Implements`키워드는 [Implements 문과](implements-statement.md)다릅니다. 문을 사용 하 여 `Implements` 하나 이상의 인터페이스를 구현 하는 클래스 또는 구조체를 지정 하 고 각 멤버에 대해 키워드를 사용 하 여 `Implements` 인터페이스 및 인터페이스를 구현 하는 멤버를 지정 합니다.

클래스 또는 구조체에서 인터페이스를 구현 하는 경우 `Implements` [클래스 문](class-statement.md) 또는 [구조체 문](structure-statement.md)바로 뒤에 문을 포함 해야 하며, 인터페이스에서 정의 된 모든 멤버를 구현 해야 합니다.

## <a name="reimplementation"></a>재구현  

파생 클래스에서 기본 클래스가 이미 구현 된 인터페이스 멤버를 다시 구현할 수 있습니다. 이는 다음과 같은 측면에서 기본 클래스 멤버를 재정의 하는 것과는 다릅니다.

- 기본 클래스 멤버는 다시 구현 수 있도록 [재정의할](../modifiers/overridable.md) 필요가 없습니다.
- 다른 이름을 사용 하 여 멤버를 다시 구현할 수 있습니다.

`Implements`키워드는 다음 컨텍스트에서 사용할 수 있습니다.

- [Event 문](event-statement.md)
- [Function 문](function-statement.md)
- [Property Statement](property-statement.md)
- [Sub 문](sub-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [Implements 문](implements-statement.md)
- [Interface 문](interface-statement.md)
- [Class 문](class-statement.md)
- [Structure 문](structure-statement.md)
