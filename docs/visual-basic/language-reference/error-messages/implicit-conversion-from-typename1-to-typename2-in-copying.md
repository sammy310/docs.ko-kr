---
description: "<typename1> <typename2> ' ByRef ' 매개 변수 ' '의 값을 일치 하는 <parametername> 인수에 다시 복사 하는 중에 BC41999: ' '에서 ' ' (으)로의 암시적 변환에 대해 자세히 알아보세요."
title: ByRef' 매개 변수 '<typename1>'의 값을 해당 인수에 다시 복사하는 동안 발생하는 '<typename2>'에서 '<parametername>'(으)로의 암시적 변환입니다.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: debe9d248a41d1b5c1f541392a1846b8598c126f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796082"
---
# <a name="bc41999-implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a>BC41999: ' \<typename1> \<typename2> ByRef ' 매개 변수 ' '의 값을 일치 하는 인수에 다시 복사 하는 동안 ' '에서 ' ' (으)로 암시적으로 변환 \<parametername> 합니다.

해당 매개 변수와 다른 형식의 [ByRef](../modifiers/byref.md) 인수를 사용 하 여 프로시저를 호출 합니다.

 인수를 전달 하는 경우 Visual Basic는 경우 `ByRef` 에 따라 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다. 이 경우 프로시저가 반환 될 때 Visual Basic는 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.

 `ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다. 그러나 형식이 서로 다르면 Visual Basic 양방향으로 변환 해야 합니다. `CType`프로시저 인수나 매개 변수에서 또는 다른 변환 키워드를 사용할 수 없기 때문에 이러한 변환은 항상 암시적입니다.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC41999

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 가능 하면 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 하므로 Visual Basic는 변환을 수행할 필요가 없습니다.

- 매개 변수 형식과 다른 인수 형식을 사용하여 프로시저를 호출해야 하지만 호출 인수에 값을 반환할 필요가 없는 경우 매개 변수를 [ByRef](../modifiers/byval.md) 가 아니라 `ByRef`로 정의합니다.

## <a name="see-also"></a>참고 항목

- [절차](../../programming-guide/language-features/procedures/index.md)
- [프로시저 매개 변수 및 인수](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [값 또는 참조로 인수 전달](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
