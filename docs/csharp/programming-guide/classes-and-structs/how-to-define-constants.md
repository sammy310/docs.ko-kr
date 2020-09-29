---
title: C#에서 상수 정의 방법
description: 컴파일 시간에 값이 설정되는 필드인 C#에서 상수를 정의하는 방법에 대해 알아봅니다. 상수를 사용하여 특수 값에 의미 있는 이름을 제공합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: dd8c6469c4d72da5588f0dce5314308bcc7e3b95
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91199122"
---
# <a name="how-to-define-constants-in-c"></a>C\#에서 상수 정의 방법

상수는 해당 값이 컴파일 시간에 설정되며 변경할 수 없는 필드입니다. 상수를 사용하여 특수 값에 대해 숫자 리터럴(“매직 넘버”) 대신 의미 있는 이름을 제공할 수 있습니다.  
  
> [!NOTE]
> C#에서는 [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) 전처리기 지시문을 사용하여 일반적으로 C와 C++에서 사용되는 방식으로 상수를 정의할 수 없습니다.  
  
 정수 형식(`int`, `byte` 등)의 상수 값을 정의하려면 열거 형식을 사용합니다. 자세한 내용은 [enum](../../language-reference/builtin-types/enum.md)을 참조하세요.  
  
 정수가 아닌 상수를 정의하는 한 가지 방법은 `Constants`라는 단일 정적 클래스로 그룹화하는 것입니다. 이 경우 다음 예제와 같이 상수에 대한 모든 참조 앞에 클래스 이름이 와야 합니다.  
  
## <a name="example"></a>예제  

 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 클래스 이름 한정자를 통해 사용자와 상수를 사용하는 다른 사용자가 상수이며 수정할 수 없음을 쉽게 파악할 수 있습니다.  
  
## <a name="see-also"></a>참조

- [클래스 및 구조체](./index.md)
