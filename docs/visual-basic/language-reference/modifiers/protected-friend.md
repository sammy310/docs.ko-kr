---
title: 보호 된 Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: d3592feaece1d5ce85ee6e2657d8a2715c4097a3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524778"
---
# <a name="protected-friend-visual-basic"></a>보호 된 Friend (Visual Basic)

`Protected Friend` 키워드 조합은 멤버 액세스 한정자입니다. 선언 된 요소에 대 한 [Friend](friend.md) 액세스와 [보호 된](protected.md) 액세스를 모두 권한을 부여, 동일한 어셈블리, 자체 클래스 및 파생 클래스의 어디에서 나 액세스할 수 있습니다. @No__t_0는 클래스의 멤버에만 지정할 수 있습니다. 구조체는 상속 될 수 없으므로 구조체의 멤버에 `Protected Friend`을 적용할 수 없습니다.

> [!NOTE]
> Visual Studio에서는 `protected friend`에 대 한 F1 도움말을 선택 하 여 [보호](protected.md) 또는 [friend](friend.md)에 대 한 도움말을 제공 합니다. IDE는 복합 단어가 아니라 커서에서 단일 토큰을 선택 합니다.

## <a name="rules"></a>규칙

**선언 컨텍스트입니다.** 클래스 수준 에서만 `Protected Friend`를 사용할 수 있습니다. 즉, `Protected` 요소에 대 한 선언 컨텍스트는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.

## <a name="see-also"></a>참조

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [전용](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
