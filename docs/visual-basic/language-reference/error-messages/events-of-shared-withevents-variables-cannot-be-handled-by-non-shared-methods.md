---
title: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 02039b81251e59a951a0fe37ec2c9534b458b6a5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161922"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>BC30594: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.

한정자를 사용 하 여 선언 된 변수는 `Shared` 공유 변수입니다. 공유 변수는 정확히 하나의 저장소 위치를 식별 합니다. 한정자를 사용 하 여 선언 된 변수는 변수가 `WithEvents` 속한 형식이 변수가 발생 시키는 이벤트 집합을 처리 함을 어설션 합니다. 변수에 값이 할당 되 면 선언으로 생성 된 속성이 `WithEvents` 기존 이벤트 처리기를 언 후크 하 고 메서드를 통해 새 이벤트 처리기를 후크합니다 `Add` .

 **오류 ID:** BC30594

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 이벤트 처리기를 선언 `Shared` 합니다.

## <a name="see-also"></a>참고 항목

- [공유](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
