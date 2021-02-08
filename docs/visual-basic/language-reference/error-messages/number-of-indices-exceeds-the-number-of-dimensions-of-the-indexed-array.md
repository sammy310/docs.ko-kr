---
description: '자세히 알아보기: BC30106: 인덱스 수가 인덱싱된 배열의 차원 수를 초과 합니다.'
title: 인덱스 수가 인덱싱된 배열의 차수보다 많습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 35ec1ea106e67022046179412b142cd92712c822
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795613"
---
# <a name="bc30106-number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="a3092-103">BC30106: 인덱스 수가 인덱싱된 배열의 차원 수를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3092-103">BC30106: Number of indices exceeds the number of dimensions of the indexed array</span></span>

<span data-ttu-id="a3092-104">배열 요소에 액세스하는 데 사용하는 인덱스 수는 정확하게 배열의 순위, 즉 배열에 선언된 차원 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3092-104">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>

 <span data-ttu-id="a3092-105">**오류 ID:** BC30106</span><span class="sxs-lookup"><span data-stu-id="a3092-105">**Error ID:** BC30106</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a3092-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a3092-106">To correct this error</span></span>

- <span data-ttu-id="a3092-107">총 첨자 수가 배열의 차수와 같을 때까지 배열 참조에서 아래 첨자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3092-107">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="a3092-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3092-108">For example:</span></span>

    ```vb
    Dim gameBoard(3, 3) As String

    ' Incorrect code. The array has two dimensions.
    gameBoard(1, 1, 1) = "X"
    gameBoard(2, 1, 1) = "O"

    ' Correct code.
    gameBoard(0, 0) = "X"
    gameBoard(1, 0) = "O"
    ```

## <a name="see-also"></a><span data-ttu-id="a3092-109">참조</span><span class="sxs-lookup"><span data-stu-id="a3092-109">See also</span></span>

- [<span data-ttu-id="a3092-110">배열</span><span class="sxs-lookup"><span data-stu-id="a3092-110">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
