---
description: '자세히 알아보기: 잘못 된 패턴 문자열'
title: 잘못된 패턴 문자열
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4fbf16dd43ac4ae44e1a99d85caae4a7baf99109
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462063"
---
# <a name="invalid-pattern-string"></a>잘못된 패턴 문자열

검색의 `Like` 작업에서 지정된 패턴 문자열이 잘못되었습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 목록 식에 유효한 문자를 검토합니다.  
  
2. 패턴 범위에서 `[a-z]`처럼 범위 시작 문자가 범위 끝 문자보다 작은지 확인합니다.  
  
3. 패턴 범위에서 `[a--z]`처럼 여러 하이픈이 서로 인접하지 않는지 확인합니다.  
  
4. 닫는 대괄호를 사용하여 패턴 범위를 종료합니다.  
  
## <a name="see-also"></a>추가 정보

- [Like 연산자](../language-reference/operators/like-operator.md)
