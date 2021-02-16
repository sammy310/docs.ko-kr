---
description: '자세한 정보: 루프 구조 (Visual Basic)'
title: 루프 구조체
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 82ff36d8f5c05501fcff0f1d564e2613c9b78953
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480650"
---
# <a name="loop-structures-visual-basic"></a>루프 구조(Visual Basic)

Visual Basic 루프 구조를 사용 하면 하나 이상의 코드 줄을 반복적으로 실행할 수 있습니다. 조건이 `True` 이거나, 조건이 `False` 이거나, 지정 된 횟수 만큼 또는 컬렉션의 각 요소에 대해 한 번까지 루프 구조에서 문을 반복할 수 있습니다.  
  
 다음 그림은 조건이 true가 될 때까지 문 집합을 실행 하는 루프 구조를 보여 줍니다.  
  
 ![Do ...를 보여 주는 순서도 ... Until 루프.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a>While 루프  

 `While`... `End While` 생성은 문에 지정 된 조건이 인 한 문 집합을 실행 합니다 `While` `True` . 자세한 내용은 While 항목을 참조 하세요. [ End While 문](../../../language-reference/statements/while-end-while-statement.md)입니다.  
  
## <a name="do-loops"></a>Do 루프  

 `Do`... `Loop` 생성을 사용 하면 루프 구조의 시작 부분 또는 끝 부분에서 조건을 테스트할 수 있습니다. 조건이 유지 되는 동안 `True` 또는 상태가 될 때까지 루프를 반복할지 여부도 지정할 수 있습니다 `True` . 자세한 내용은 다음 [을 참조 하세요. Loop 문](../../../language-reference/statements/do-loop-statement.md).  
  
## <a name="for-loops"></a>For 루프  

 `For`... 생성은 설정 된 횟수 만큼 루프를 수행 합니다. `Next` 루프 제어 변수 ( *카운터* 라고도 함)를 사용 하 여 반복을 추적 합니다. 이 카운터에 대 한 시작 값과 끝 값을 지정 하 고, 필요에 따라 반복에서 다음 반복까지 늘리는 크기를 지정할 수 있습니다. 자세한 내용은 다음 [을 참조 하세요. 다음 문](../../../language-reference/statements/for-next-statement.md).  
  
## <a name="for-each-loops"></a>For Each 루프  

 `For Each`... `Next` 생성은 컬렉션의 각 요소에 대해 문 집합을 한 번씩 실행 합니다. 루프 제어 변수를 지정 하지만 해당 변수를 시작 하거나 종료 하는 값을 결정할 필요가 없습니다. 자세한 내용은 For Each ...를 참조 하십시오. [ 다음 문](../../../language-reference/statements/for-each-next-statement.md).  
  
## <a name="see-also"></a>추가 정보

- [제어 흐름](index.md)
- [판단 구조체](decision-structures.md)
- [기타 제어 구조체](other-control-structures.md)
- [중첩 제어 구조체](nested-control-structures.md)
