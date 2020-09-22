---
title: 선언 컨텍스트 및 기본 액세스 수준
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: a659481b34b8b44f1f387b464d5d9656ed98ab3f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874956"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>선언 컨텍스트 및 기본 액세스 수준(Visual Basic)

이 항목에서는 다른 형식 내에서 선언할 수 있는 Visual Basic 형식 및 지정 되지 않은 경우 기본적으로 사용 되는 액세스 수준에 대해 설명 합니다.  
  
## <a name="declaration-context-levels"></a>선언 컨텍스트 수준  

 프로그래밍 요소의 *선언 컨텍스트* 는 선언 된 코드 영역입니다. 이는 일반적으로 *포함 하는 요소*라고 하는 또 다른 프로그래밍 요소입니다.  
  
 선언 컨텍스트의 수준은 다음과 같습니다.  
  
- *네임 스페이스 수준* -소스 파일 또는 네임 스페이스 내에 있지만 클래스, 구조체, 모듈 또는 인터페이스에는 포함 되지 않습니다.  
  
- *모듈 수준* -클래스, 구조체, 모듈 또는 인터페이스 내에서 프로시저나 블록 내에 있지 않습니다.  
  
- 프로시저 *수준* -프로시저 또는 블록 내에서 (예: `If` 또는 `For` )  
  
 다음 표에서는 선언 컨텍스트에 따라 다양 하 게 선언 된 프로그래밍 요소에 대 한 기본 액세스 수준을 보여 줍니다.  
  
|선언 요소|네임 스페이스 수준|모듈 수준|프로시저 수준|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([Dim 문](dim-statement.md))|허용되지 않음|`Private`에서는 `Public` `Structure` 허용 되지 않습니다. `Interface`|`Public`|  
|상수 ([Const 문](const-statement.md))|허용되지 않음|`Private`에서는 `Public` `Structure` 허용 되지 않습니다. `Interface`|`Public`|  
|Enumeration ([Enum 문](enum-statement.md))|`Friend`|`Public`|허용되지 않음|  
|클래스 ([클래스 문](class-statement.md))|`Friend`|`Public`|허용되지 않음|  
|Structure ([Structure 문](structure-statement.md))|`Friend`|`Public`|허용되지 않음|  
|Module ([Module 문](module-statement.md))|`Friend`|허용되지 않음|허용되지 않음|  
|Interface ([Interface 문](interface-statement.md))|`Friend`|`Public`|허용되지 않음|  
|프로시저 ([Function 문](function-statement.md), [Sub 문](sub-statement.md))|허용되지 않음|`Public`|허용되지 않음|  
|외부 참조 ([Declare 문](declare-statement.md))|허용되지 않음|`Public` (에서 허용 되지 않음 `Interface` )|허용되지 않음|  
|Operator ([Operator 문](operator-statement.md))|허용되지 않음|`Public` (또는에서는 허용 되지 않음 `Interface` `Module` )|허용되지 않음|  
|Property ([Property 문](property-statement.md))|허용되지 않음|`Public`|허용되지 않음|  
|Default 속성 ([기본값](../modifiers/default.md))|허용되지 않음|`Public` (에서 허용 되지 않음 `Module` )|허용되지 않음|  
|이벤트 ([Event Statement](event-statement.md))|허용되지 않음|`Public`|허용되지 않음|  
|Delegate ([Delegate 문](delegate-statement.md))|`Friend`|`Public`|허용되지 않음|  
  
 자세한 내용은 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [Friend](../modifiers/friend.md)
- [개인](../modifiers/private.md)
- [공용](../modifiers/public.md)
