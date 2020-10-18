---
title: <variable> 범위 변수가 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 90fed3dd27f18fe87c326cc36dfb774822fc4b21
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162351"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>BC36633: 범위 변수는 \<variable> 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다.

,, 또는 절에 지정 된 범위 변수 이름이 `Select` `From` `Aggregate` `Let` 쿼리에서 이미 이전에 지정 된 범위 변수의 이름 또는 쿼리에서 암시적으로 선언 된 변수 이름 (예: 필드 이름 또는 집계 함수의 이름)을 복제 합니다.

 **오류 ID:** BC36633

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 특정 쿼리 범위의 모든 범위 변수 이름이 고유한 지 확인 합니다. 쿼리를 괄호로 묶어 중첩 된 쿼리에 고유한 범위가 있는지 확인할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [From 절](../queries/from-clause.md)
- [Let 절](../queries/let-clause.md)
- [Aggregate Clause](../queries/aggregate-clause.md)
- [Select 절](../queries/select-clause.md)
