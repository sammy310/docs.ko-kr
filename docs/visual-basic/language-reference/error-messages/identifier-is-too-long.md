---
description: '자세히 알아보기: BC30033: 식별자가 너무 깁니다.'
title: 식별자가 너무 깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: f2439c4bfc53f906fdc277b0de1faac0941c8808
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796095"
---
# <a name="bc30033-identifier-is-too-long"></a>BC30033: 식별자가 너무 깁니다.

모든 프로그래밍 요소의 이름 또는 식별자는 1023 자로 제한 됩니다. 또한 정규화 된 이름은 1023 자를 초과할 수 없습니다. 즉, 전체 식별자 문자열 ()은 `<namespace>.<...>.<namespace>.<class>.<element>` 멤버 액세스 연산자 () 문자를 포함 하 여 1023 자를 초과할 수 없습니다 `.` .

 **오류 ID:** BC30033

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 식별자의 길이를 줄입니다.

## <a name="see-also"></a>참고 항목

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
