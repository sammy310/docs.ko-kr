---
description: '자세히 알아보기: BC30029: 파생 클래스에서 기본 클래스 이벤트를 발생 시킬 수 없습니다.'
title: 파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 68546f2654f7c34fcb309d5af68e237d5f1eac79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796602"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: 파생 클래스는 기본 클래스 이벤트를 발생 시킬 수 없습니다.

이벤트는 선언 된 선언 공간 에서만 발생할 수 있습니다. 따라서 클래스는 파생 된 클래스를 비롯 하 여 다른 클래스에서 이벤트를 발생 시킬 수 없습니다.

 **오류 ID:** BC30029

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- `Event`문이나 `RaiseEvent` 문이 동일한 클래스에 있도록 이동 합니다.

## <a name="see-also"></a>참고 항목

- [Event 문](../statements/event-statement.md)
- [RaiseEvent 문](../statements/raiseevent-statement.md)
