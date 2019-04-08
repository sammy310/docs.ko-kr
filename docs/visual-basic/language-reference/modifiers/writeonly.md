---
title: WriteOnly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 1b8de27e872914ba59d73126d2a9a7c42609165e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829030"
---
# <a name="writeonly-visual-basic"></a>WriteOnly(Visual Basic)
속성을 쓸 수는 있지만 읽을 수는 있는지를 지정 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="rules"></a>규칙  
 **선언 컨텍스트입니다.** `WriteOnly`는 모듈 수준에서만 사용할 수 있습니다. 즉, 선언 컨텍스트는 `WriteOnly` 속성 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저 수는 없습니다.  
  
 속성으로 선언할 수 있습니다 `WriteOnly`, 되지만 변수 없습니다.  
  
## <a name="when-to-use-writeonly"></a>WriteOnly를 사용 하는 경우  
 값을 설정 하지만 이것이 무엇 인지를 검색 하지 수를 사용 하는 코드는 경우가 있습니다. 예를 들어 주민 등록 번호나 암호 같은 중요 한 데이터를 설정 하지 않은 모든 구성 요소에 의해 액세스 로부터 보호 해야 합니다. 이러한 경우에 사용할 수는 `WriteOnly` 속성 값을 설정 합니다.  
  
> [!IMPORTANT]
>  정의 하 고 사용 하는 경우를 `WriteOnly` 속성을 다음 추가 보호 조치는 것이 좋습니다.  
  
-   **재정의합니다.** 속성을 클래스의 멤버인 경우 기본적으로 사용 하 고 허용 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), 및 선언 하지 마십시오 `Overridable` 또는 `MustOverride`합니다. 이렇게 하면 파생된 클래스를 재정의 통해 원치 않는 액세스 하지 못하도록 않습니다.  
  
-   **액세스 수준입니다.** 하나 이상의 변수에서 속성의 중요 한 데이터를 보관 하는 경우 선언할 [개인](../../../visual-basic/language-reference/modifiers/private.md) 다른 코드가 없어야 액세스할 수 있도록 합니다.  
  
-   **암호화 합니다.** 일반 텍스트 대신 암호화 된 형태로 모든 중요 한 데이터를 저장 합니다. 어떤 이유로 든 악성 코드에는 메모리의 해당 영역에 대 한 액세스 권한을 획득, 한 경우 더 어렵습니다 되도록 데이터를 사용 합니다. 암호화는 중요 한 데이터를 serialize 해야 하는 경우에 유용 이기도 합니다.  
  
-   **다시 설정 합니다.** 클래스, 구조체 또는 속성을 정의 하는 모듈 종료 될 때 다른 의미가 값 또는 기본값에 중요 한 데이터를 다시 설정 합니다. 이 일반 액세스에 대 한 메모리 영역 해제 될 때 추가 보호를 제공 합니다.  
  
-   **지 속성** 예를 들어 디스크에 모든 중요 한 데이터를 피할 수 지속 되지 않습니다. 또한 클립보드에 모든 중요 한 데이터를 기록 하지 마십시오.  
  
 `WriteOnly` 한정자는이 컨텍스트에서 사용할 수 있습니다.  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>참고자료

- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [전용](../../../visual-basic/language-reference/modifiers/private.md)
- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
