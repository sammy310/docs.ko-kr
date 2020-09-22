---
title: 개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: e55a5515d88bd2782e31fdea7c07e16c595d43b5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873647"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.

`WithEvents`지정 된 이벤트 집합에 대 한 이벤트 소스로 작동할 수 없는 구성 요소에서 변수를 사용 하려고 했습니다. 예를 들어 개체의 이벤트를 싱크 한 다음 `Implements` 첫 번째 개체에 해당 하는 다른 개체를 만들 수 있습니다. 구현 된 개체에서 이벤트를 싱크할 수도 있지만이 경우에는 항상 그렇지는 않습니다. `Implements` 는 메서드 및 속성에 대 한 인터페이스만 구현 합니다. `WithEvents` 는를 발생 시키는 데 `UserControls` 필요한 형식 정보를 런타임에 사용할 수 없으므로 private에 대해 지원 되지 않습니다 `ObjectEvent` .  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 이벤트를 소스 하지 않는 구성 요소에 대 한 이벤트를 싱크할 수 없습니다.  
  
## <a name="see-also"></a>참조

- [WithEvents](../modifiers/withevents.md)
- [Implements 문](../statements/implements-statement.md)
