---
title: "'<methodname>'에 서명이 동일한 정의가 여러 개 있습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160368"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: ' \<methodname> '에 시그니처가 동일한 정의가 여러 개 있습니다.

`Function`또는 `Sub` 프로시저 선언에서 이전 선언과 동일한 프로시저 이름 및 인수 목록을 사용 합니다. 한 가지 가능한 원인은 원래 프로시저를 오버 로드 하려고 시도 하는 것입니다. 오버 로드 된 프로시저에는 서로 다른 인수 목록이 있어야 합니다.

 **오류 ID:** BC30269

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 프로시저 이름 또는 인수 목록을 변경 하거나 중복 된 선언을 제거 합니다.

## <a name="see-also"></a>참고 항목

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [프로시저 오버로드에서 고려해야 할 사항](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
