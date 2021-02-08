---
description: "자세한 내용은 다음에 대해 자세히 알아보세요. BC30043: ' <keyword> '은 인스턴스 메서드 내 에서만 사용할 수 있습니다."
title: "'<keyword>'은(는) 인스턴스 메서드 안에서만 사용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 0bca2df44e096da016c9cb0c2031a8ef6faeb2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795978"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a>BC30043: ' \<keyword> '은 (는) 인스턴스 메서드 내 에서만 사용할 수 있습니다.

`Me`, `MyClass` 및 키워드는 `MyBase` 특정 클래스 인스턴스를 참조 합니다. 공유 또는 프로시저 내에서는 사용할 수 `Function` 없습니다 `Sub` .

*오류 ID:** BC30043

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 프로시저에서 키워드를 제거 하거나 `Shared` 프로시저 선언에서 키워드를 제거 합니다.

## <a name="see-also"></a>참고 항목

- [개체 변수 할당](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase 및 MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
