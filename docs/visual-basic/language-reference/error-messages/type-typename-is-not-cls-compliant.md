---
title: <typename>' 형식이 CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: c50e721e9170a402724a11f3aab573c7e8abf4c1
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161168"
---
# <a name="bc40041-type-typename-is-not-cls-compliant"></a>BC40041: 형식이 \<typename> CLS 규격이 아닙니다.

변수, 속성 또는 함수 return이 CLS 규격이 아닌 데이터 형식으로 선언 되었습니다.

 응용 프로그램이 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (cls)를 준수 하도록 하려면 cls 규격 형식만 사용 해야 합니다.

 다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.

- [SByte 데이터 형식](../data-types/sbyte-data-type.md)

- [UInteger 데이터 형식](../data-types/uinteger-data-type.md)

- [ULong 데이터 형식](../data-types/ulong-data-type.md)

- [UShort 데이터 형식](../data-types/ushort-data-type.md)

 **오류 ID:** BC40041

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 응용 프로그램에서 CLS 규격을 준수 해야 하는 경우이 요소의 데이터 형식을 가장 가까운 CLS 규격 형식으로 변경 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.

- 응용 프로그램에서 CLS 규격이 필요 하지 않은 경우에는 아무것도 변경할 필요가 없습니다. 그러나 비준수를 알고 있어야 합니다.
