---
description: '자세히 알아보기: 방법: 변수에 둘 이상의 값 저장 (Visual Basic)'
title: '방법: 변수에 두 개 이상의 값 사용'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 5248bc29f58cccf3b8ced95d3fba8f0d39033a83
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100484004"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>방법: 변수에 두 개 이상의 값 사용(Visual Basic)

*복합 데이터 형식* 으로 선언 하는 경우 변수에 두 개 이상의 값이 포함 됩니다.

[복합 데이터 형식](composite-data-types.md) 에는 구조체, 배열 및 클래스가 포함 됩니다. 복합 데이터 형식의 변수는 기본 데이터 형식과 기타 복합 형식의 조합을 포함할 수 있습니다. 구조체와 클래스는 데이터 뿐만 아니라 코드도 포함할 수 있습니다.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>변수에 두 개 이상의 값을 저장 하려면

1. 변수에 사용 하려는 복합 데이터 형식을 결정 합니다.

2. 복합 데이터 형식이 아직 정의 되지 않은 경우 변수에서 사용할 수 있도록 정의 합니다.

    - Structure [문을](../../../language-reference/statements/structure-statement.md)사용 하 여 구조체를 정의 합니다.

    - [Dim 문으로](../../../language-reference/statements/dim-statement.md)배열을 정의 합니다.

    - [클래스 문으로](../../../language-reference/statements/class-statement.md)클래스를 정의 합니다.

3. 문을 사용 하 여 변수를 선언 `Dim` 합니다.

4. 변수 이름 뒤에 절을 추가 `As` 합니다.

5. 키워드 뒤에 `As` 적절 한 복합 데이터 형식의 이름을 추가 합니다.

## <a name="see-also"></a>추가 정보

- [데이터 형식](../../../language-reference/data-types/index.md)
- [형식 문자](type-characters.md)
- [복합 데이터 형식](composite-data-types.md)
- [구조체](structures.md)
- [배열](../arrays/index.md)
- [개체 및 클래스](../objects-and-classes/index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
