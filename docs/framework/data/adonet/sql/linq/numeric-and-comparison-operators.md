---
title: 숫자 및 비교 연산자
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: b29f78a13d6d0313e0ad29754f6d13ac08be1092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783138"
---
# <a name="numeric-and-comparison-operators"></a>숫자 및 비교 연산자

산술 및 비교 연산자는 CLR(공용 언어 런타임) 예외에서 다음과 같이 예상대로 동작합니다.

- SQL에서는 부동 소수점 숫자에 대해 모듈 연산자를 지원하지 않습니다.

- SQL에서는 unchecked 산술 연산을 지원하지 않습니다.

- 증가 및 감소 연산자를 SQL에서 복제할 수 없는 식에 사용하면 예기치 않은 결과가 발생할 수 있기 때문에 두 연산자는 지원되지 않습니다.

## <a name="supported-operators"></a>지원되는 연산자

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 연산자를 지원합니다.

- 기본 산술 연산자:

  - `+`

  - `-`(빼기)

  - `*`

  - `/`

  - `\`(Visual Basic 정수 나누기)

  - `%`(Visual Basic `Mod`)

  - `<<`

  - `>>`

  - `-`(단항 부정 연산자)

- 기본 비교 연산자:

  - Visual Basic `=` 및 C# `==`

  - Visual Basic `<>` 및 C# `!=`

  - Visual Basic `Is/IsNot`

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a>참고자료

- [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [C# 연산자](../../../../../../docs/csharp/language-reference/operators/index.md)
- [연산자](../../../../../visual-basic/language-reference/operators/index.md)
