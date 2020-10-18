---
title: 식에 있는 '<typename>' 형식은 제한된 형식이므로 'Object' 또는 'ValueType'에서 상속된 멤버에 액세스하는 데 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3e19c0d71ee47ac61e9704f0fcd2637f01aa0896
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163053"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>BC31393: Expression의 ' ' 형식은 \<typename> 제한 된 형식 이므로 ' Object ' 또는 ' ValueType '에서 상속 된 멤버에 액세스 하는 데 사용할 수 없습니다.

식이 CLR (공용 언어 런타임)에 의해 boxing 될 수 없는 형식으로 계산 되지만 boxing이 필요한 멤버에 액세스 합니다.

 *Boxing* 은 형식을 경우에 따라 `Object` 또는 <xref:System.ValueType>으로 변환하는 데 필요한 처리를 참조합니다. 공용 언어 런타임에서는 특정 구조체 형식 (예:, 및)을 box 할 수 없습니다 <xref:System.ArgIterator> <xref:System.RuntimeArgumentHandle> <xref:System.TypedReference> .

 이 식은 또는와 같이 제한 된 형식을 사용 하 여 또는에서 상속 된 메서드를 호출 하려고 <xref:System.Object> <xref:System.ValueType> <xref:System.Object.GetHashCode%2A> <xref:System.Object.ToString%2A> 합니다. 이 메서드에 액세스 하기 위해 Visual Basic에서이 오류를 발생 시키는 암시적 boxing 변환을 시도 했습니다.

 **오류 ID:** BC31393

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 제시된 형식으로 계산되는 식을 찾습니다.

2. 또는에서 상속 된 메서드를 호출 하려고 하는 문의 일부를 찾습니다 <xref:System.Object> <xref:System.ValueType> .

3. 메서드 호출을 방지 하려면 문을 다시 작성 합니다.

## <a name="see-also"></a>참고 항목

- [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
