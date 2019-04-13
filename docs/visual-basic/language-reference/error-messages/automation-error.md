---
title: 자동화 오류
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 8370f744b916ce4a797c808ed58c5fc9580e6278
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304314"
---
# <a name="automation-error"></a>자동화 오류
메서드를 실행하는 동안 또는 개체 변수의 속성을 가져오거나 설정하는 동안 오류가 발생했습니다. 이 오류는 개체를 만든 응용 프로그램에서 보고했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `Err` 개체의 속성을 점검해 오류의 원인과 특성을 확인합니다.  
  
2. 액세스하는 문 바로 전에 `On Error Resume Next` 문을 사용하고, 액세스하는 문 바로 후에 오류가 발생하는지 확인합니다.  
  
## <a name="see-also"></a>참고자료

- [오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Talk to Us](/visualstudio/ide/talk-to-us)
