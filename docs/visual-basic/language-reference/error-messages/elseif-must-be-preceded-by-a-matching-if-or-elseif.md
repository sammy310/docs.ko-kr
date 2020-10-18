---
title: "'#ElseIf'는 짝이 되는 '#If' 또는 '#ElseIf' 뒤에 와야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 142c142afe0d9be0ecd4d8a0340f0f1957b20470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162780"
---
# <a name="bc30014-elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>BC30014: ' #ElseIf '는 짝이 되는 ' #If ' 또는 ' #ElseIf ' 뒤에와 야 합니다.

`#ElseIf` 는 조건부 컴파일 지시문입니다. `#ElseIf`절 앞에는 일치 하는 or 절이와 야 `#If` `#ElseIf` 합니다.

 **오류 ID:** BC30014

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. `#If` `#ElseIf` `#ElseIf` 중간 조건부 컴파일 블록 또는 잘못 배치 된에 의해 앞에 있는 또는가이와 분리 되지 않았는지 확인 `#End If` 합니다.

2. `#ElseIf`이 지시문 뒤에 있으면를 `#Else` 제거 `#Else` 하거나로 변경 합니다 `#ElseIf` .

3. 다른 모든 항목의 순서가 올바른 경우 `#If` 지시문을 조건부 컴파일 블록의 시작 부분에 추가합니다.

## <a name="see-also"></a>참고 항목

- [#If...Then...#Else 지시문](../directives/if-then-else-directives.md)
