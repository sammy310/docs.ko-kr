---
title: 파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874491"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.

이벤트는 선언 된 선언 공간 에서만 발생할 수 있습니다. 따라서 클래스는 파생 된 클래스를 비롯 하 여 다른 클래스에서 이벤트를 발생 시킬 수 없습니다.  
  
 **오류 ID:** BC30029  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `Event`문이나 `RaiseEvent` 문이 동일한 클래스에 있도록 이동 합니다.  
  
## <a name="see-also"></a>참조

- [Event 문](../statements/event-statement.md)
- [RaiseEvent 문](../statements/raiseevent-statement.md)
