---
title: "'<classname>' 대리자 클래스에는 Invoke 메서드가 없으므로 이러한 형식의 식은 프로시저 호출의 대상일 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 4e0fc61c7356008755134f670fa1fab0165cfd48
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162793"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>BC30220: 대리자 클래스 ' \<classname> '에는 Invoke 메서드가 없으므로이 형식의 식은 메서드 호출의 대상일 수 없습니다.

대리자 `Invoke` `Invoke` 클래스에서가 구현 되지 않았기 때문에 대리자를 통한 호출이 실패 했습니다.

 **오류 ID:** BC30220

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 문을 사용 하 여 대리자 클래스의 인스턴스를 만들고 `Dim` 프로시저가 연산자를 사용 하 여 대리자 인스턴스에 할당 되었는지 확인 `AddressOf` 합니다.

2. 대리자 클래스를 구현 하는 코드를 찾고 프로시저를 구현 하는지 확인 합니다 `Invoke` .

## <a name="see-also"></a>참고 항목

- [대리자](../../programming-guide/language-features/delegates/index.md)
- [Delegate 문](../statements/delegate-statement.md)
- [AddressOf 연산자](../operators/addressof-operator.md)
- [Dim 문](../statements/dim-statement.md)
