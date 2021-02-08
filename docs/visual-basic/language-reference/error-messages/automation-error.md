---
description: '자세히 알아보기: 자동화 오류'
title: 자동화 오류
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e4d283b16b4c54e2488fedfc58d3c881cf6b0218
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797122"
---
# <a name="automation-error"></a>자동화 오류

메서드를 실행하는 동안 또는 개체 변수의 속성을 가져오거나 설정하는 동안 오류가 발생했습니다. 이 오류는 개체를 만든 애플리케이션에서 보고했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `Err` 개체의 속성을 점검해 오류의 원인과 특성을 확인합니다.  
  
2. 액세스하는 문 바로 전에 `On Error Resume Next` 문을 사용하고, 액세스하는 문 바로 후에 오류가 발생하는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목

- [오류 유형](../../programming-guide/language-features/error-types.md)
- [의견 보내기](/visualstudio/ide/feedback-options)
