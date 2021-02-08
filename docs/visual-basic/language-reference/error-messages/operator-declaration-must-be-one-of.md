---
description: '자세한 정보: BC33000: 연산자 선언은 +,-, *,,/, ^, &amp; , Like, Mod, And, or, Xor, Not,  <<,  >> 중 하나 여야 합니다.'
title: 연산자 선언은 +,-, *,-,-, ^, &amp; , Like, Mod, And, or, Xor, Not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse 중 하나 여야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 0ad82a6414387278622a10624952ebc35e7e9b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795562"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>BC33000: 연산자 선언은 +,-, *, \, /, ^, &amp; Like, Mod, And, or, Xor, Not, \<\<, >> 중 하나 여야 합니다.

오버 로드할 수 있는 연산자만 선언할 수 있습니다. 다음 표에서는 선언할 수 있는 연산자를 나열 합니다.

|Type|연산자|
|----------|---------------|
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|이진|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|변환(단항)|`CType`|

 `=`이진 목록의 연산자는 대입 연산자가 아닌 비교 연산자입니다.

 **오류 ID:** BC33000

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.

- 직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.

## <a name="see-also"></a>참고 항목

- [Operator Statement](../statements/operator-statement.md)
- [연산자 프로시저](../../programming-guide/language-features/procedures/operator-procedures.md)
- [방법: 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Function 문](../statements/function-statement.md)
