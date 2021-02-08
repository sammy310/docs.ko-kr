---
description: "자세한 정보: BC30481: ' Class ' 문은 짝이 되는 ' End 클래스 '로 끝나야 합니다."
title: "'Class' 문은 짝이 되는 'End Class'로 끝나야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: b0d2d89e9e3549b24f9c923e271b15b3b02026b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796783"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a>BC30481: ' Class ' 문은 짝이 되는 ' End Class '로 끝나야 합니다.

`Class` 는 블록을 시작 하는 데 사용 되므로 블록의 시작 부분에만 나타날 수 있으며 블록을 종료 하는 짝이 되는 `Class` 문을 사용 합니다 `End Class` . 중복 문이 있거나를 사용 하 여 `Class` 블록을 종료 하지 않았습니다 `Class` `End Class` .

 **오류 ID:** BC30481

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 불필요한 `Class` 문을 찾아서 제거합니다.

- 일치 하 `Class` 는를 사용 하 여 블록을 끝냅니다 `End Class` .

## <a name="see-also"></a>참고 항목

- [End \<keyword> 문](../statements/end-keyword-statement.md)
- [Class 문](../statements/class-statement.md)
