---
title: "'#Region' 및 '#End Region' 문은 메서드 본문(multiline lambdas) 내에서 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: e3147b6192f54ce85d0fecd6b67f7d80f6281b54
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870889"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>메서드 본문에서는 '#Region' 및 '#End Region' 문을 사용할 수 없습니다./multiline lambdas

`#Region`블록은 클래스, 모듈 또는 네임 스페이스 수준에서 선언 되어야 합니다. 축소 가능한 영역은 하나 이상의 프로시저를 포함할 수 있지만 프로시저 내에서 시작 하거나 끝날 수 없습니다.  
  
 **오류 ID:** BC32025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 이전 프로시저가 또는 문을 사용 하 여 제대로 종료 되었는지 `End Function` 확인 `End Sub` 합니다.  
  
2. `#Region`및 `#End Region` 지시문이 동일한 코드 블록에 있는지 확인 합니다.  
  
## <a name="see-also"></a>참조

- [#Region 지시문](../directives/region-directive.md)
