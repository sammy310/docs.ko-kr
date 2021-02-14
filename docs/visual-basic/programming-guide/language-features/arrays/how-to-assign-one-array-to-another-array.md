---
description: '자세한 정보: 방법: 한 배열에 다른 배열 할당 (Visual Basic)'
title: '방법: 한 배열에 다른 배열 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: dc86225c1f25c207e793e33a048d948646ac77b6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434734"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>방법: 한 배열에 다른 배열 할당(Visual Basic)

배열은 개체 이기 때문에 다른 개체 형식과 같은 대입문에서 사용할 수 있습니다. 배열 변수는 배열 요소와 차수 및 length 정보를 백업을 위해 하는 데이터에 대 한 포인터를 보유 하 고 할당은이 포인터만 복사 합니다.

### <a name="to-assign-one-array-to-another-array"></a>한 배열을 다른 배열에 할당 하려면

1. 두 배열의 차수 (차원 수)와 호환 되는 요소 데이터 형식이 같은지 확인 합니다.

2. 표준 대입문을 사용 하 여 소스 배열을 대상 배열에 할당 합니다. 괄호를 사용 하 여 배열 이름을 따르지 마십시오.

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

한 배열을 다른 배열에 할당 하는 경우 다음 규칙이 적용 됩니다.

- **순위가 동일 합니다.** 대상 배열의 차수 (차원 수)는 원본 배열의 차수 (차원 수)와 같아야 합니다.

  두 배열의 순위가 동일 하 게 지정 된 경우 차원이 같을 필요는 없습니다. 지정 된 차원의 요소 수는 할당 중에 변경 될 수 있습니다.

- **요소 형식.** 두 배열 중 하나에 *참조 형식* 요소가 있거나 두 배열에 모두 *값 형식* 요소가 있어야 합니다. 자세한 내용은 [값 형식 및 참조 형식](../data-types/value-types-and-reference-types.md)을 참조 하세요.

  - 두 배열에 모두 값 형식 요소가 있으면 요소 데이터 형식이 정확히 동일 해야 합니다. 이에 대 한 유일한 예외는 `Enum` 요소의 배열을 기본 형식의 배열에 할당할 수 있다는 것입니다 `Enum` .

  - 두 배열에 모두 참조 형식 요소가 있으면 원본 요소 형식이 대상 요소 형식에서 파생 되어야 합니다. 이 경우 두 배열의 요소와 상속 관계가 동일 합니다. 이를 *배열 공분산* 이라고 합니다.

위의 규칙을 위반 하는 경우 (예: 데이터 형식이 호환 되지 않거나 순위가 같지 않은 경우) 컴파일러에서 오류를 보고 합니다. 코드에 오류 처리를 추가 하 여 배열이 호환 되는지 확인 하 고 할당을 시도할 수 있습니다. 예외를 throw 하지 않으려면 [TryCast Operator](../../../language-reference/operators/trycast-operator.md) 키워드를 사용할 수도 있습니다.

## <a name="see-also"></a>참조

- [배열](index.md)
- [배열 문제 해결](troubleshooting-arrays.md)
- [Enum 문](../../../language-reference/statements/enum-statement.md)
- [배열 규칙](../data-types/array-conversions.md)
