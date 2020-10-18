---
title: 인덱스 수가 인덱싱된 배열의 차수보다 많습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 9a191ff7ec3ad6a607e6509cc143c359f64f21ea
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159913"
---
# <a name="bc30106-number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a>BC30106: 인덱스 수가 인덱싱된 배열의 차원 수를 초과 합니다.

배열 요소에 액세스하는 데 사용하는 인덱스 수는 정확하게 배열의 순위, 즉 배열에 선언된 차원 수와 같아야 합니다.

 **오류 ID:** BC30106

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 총 첨자 수가 배열의 차수와 같을 때까지 배열 참조에서 아래 첨자를 제거 합니다. 예를 들면 다음과 같습니다.

    ```vb
    Dim gameBoard(3, 3) As String

    ' Incorrect code. The array has two dimensions.
    gameBoard(1, 1, 1) = "X"
    gameBoard(2, 1, 1) = "O"

    ' Correct code.
    gameBoard(0, 0) = "X"
    gameBoard(1, 0) = "O"
    ```

## <a name="see-also"></a>참조

- [배열](../../programming-guide/language-features/arrays/index.md)
