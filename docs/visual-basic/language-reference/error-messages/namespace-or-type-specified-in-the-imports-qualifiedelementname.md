---
description: "BC40056: Imports ' '에 지정 된 네임 스페이스 또는 형식에 <qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없는 경우에 대해 자세히 알아보세요."
title: Imports '<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: e98ba70660823196e763300cd33ec1ba9a9db3b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795705"
---
# <a name="bc40056-namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>BC40056: Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다.

Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다. 네임 스페이스 또는 형식이 정의 되어 있고 하나 이상의 public 멤버를 포함 하는지 확인 합니다. 별칭 이름이 다른 별칭을 포함 하지 않는지 확인 합니다.

`Imports`문에서 찾을 수 없거나 멤버를 정의 하지 않는 포함 하는 요소를 지정 합니다 `Public` .

*포함 하는 요소* 는 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다. 포함 하는 요소에는 변수, 프로시저 또는 포함 하는 다른 요소와 같은 멤버가 포함 됩니다.

가져오기의 목적은 코드에서 한정 하지 않고 네임 스페이스 또는 형식 멤버에 액세스할 수 있도록 하는 것입니다. 프로젝트에서 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다. 자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "포함 하는 요소 가져오기"를 참조 하세요.

컴파일러가 지정 된 포함 요소를 찾을 수 없는 경우 해당 요소를 사용 하는 참조를 확인할 수 없습니다. 요소를 찾았지만 요소가 멤버를 노출 하지 않는 경우에는 `Public` 참조가 실패할 수 있습니다. 두 경우 모두 요소를 가져오는 것은 의미가 없습니다.

포함 하는 요소를 가져와서 가져오기 별칭을 할당 하는 경우 해당 가져오기 별칭을 사용 하 여 다른 요소를 가져올 수 없습니다. 다음 코드는 컴파일러 오류를 생성 합니다.

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

**오류 ID:** BC40056

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 포함 하는 요소가 프로젝트에서 액세스할 수 있는지 확인 합니다.

2. 포함 하는 요소의 사양이 다른 가져오기의 가져오기 별칭을 포함 하지 않는지 확인 합니다.

3. 포함 하는 요소가 하나 이상의 멤버를 노출 하는지 확인 합니다 `Public` .

## <a name="see-also"></a>참고 항목

- [Imports 문(.NET 네임스페이스 및 형식)](../statements/imports-statement-net-namespace-and-type.md)
- [Namespace 문](../statements/namespace-statement.md)
- [공용](../modifiers/public.md)
- [Visual Basic의 네임스페이스](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
