---
title: 값이 할당되기 전에 '<variablename>' 변수를 사용했습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 6db8626701267f2051b289b267e7b2d9da51c283
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162221"
---
# <a name="bc42104-variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>B C 42104: 값이 \<variablename> 할당 되기 전에 ' ' 변수를 사용 했습니다.

값이 \<variablename> 할당 되기 전에 ' ' 변수를 사용 했습니다. 런타임에 null 참조 예외가 발생할 수 있습니다.

 응용 프로그램에는 값이 할당 되기 전에 변수를 읽는 코드를 통해 하나 이상의 가능한 경로가 있습니다.

 변수에 값이 할당되지 않으면 해당 데이터 형식에 대한 기본값을 유지합니다. 참조 데이터 형식의 경우 해당 기본값은 [Nothing](../nothing.md)입니다. 값이 `Nothing` 인 참조 변수를 읽으면 일부 환경에서 <xref:System.NullReferenceException> 이 발생할 수 있습니다.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** B C 42104

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 제어 흐름 논리를 확인 하 고 변수가이를 읽는 문으로 제어가 전달 되기 전에 유효한 값을 포함 하는지 확인 합니다.

- 변수를 항상 유효한 값으로 보장 하는 한 가지 방법은 선언의 일부로 초기화 하는 것입니다. [Dim 문에서](../statements/dim-statement.md)"초기화"를 참조 하세요.

## <a name="see-also"></a>참고 항목

- [Dim 문](../statements/dim-statement.md)
- [변수 선언](../../programming-guide/language-features/variables/variable-declaration.md)
- [변수 문제 해결](../../programming-guide/language-features/variables/troubleshooting-variables.md)
