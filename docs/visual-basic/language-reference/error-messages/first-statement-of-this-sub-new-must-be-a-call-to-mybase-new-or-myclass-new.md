---
title: 이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다(매개 변수가 없는 액세스할 수 있는 생성자가 없음).
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: bce8ad10bc201386f34d6623741c7d41a5dec27e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163027"
---
# <a name="bc30148-first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>BC30148:이 ' Sub n e w '의 첫째 문은 ' Mybase.new ' 또는 ' MyClass. n e w '에 대 한 호출 이어야 합니다 (매개 변수가 없는 액세스 가능 생성자 없음).

' '의 기본 클래스 ' '에는 \<basename> \<derivedname> 인수 없이 호출할 수 있는 액세스 가능한 ' sub n e w '가 없으므로이 ' sub n e w '의 첫째 문은 ' mybase.new ' 또는 ' m a s s. n e w '에 대 한 호출 이어야 합니다.

 파생 클래스에서 모든 생성자는 기본 클래스 생성자 ()를 호출 해야 합니다 `MyBase.New` . 기본 클래스에 파생 클래스에서 액세스할 수 있는 매개 변수가 없는 생성자가 있는 경우를 `MyBase.New` 자동으로 호출할 수 있습니다. 그렇지 않은 경우 기본 클래스 생성자는 매개 변수를 사용 하 여 호출 해야 하며,이 작업은 자동으로 수행할 수 없습니다. 이 경우 모든 파생 클래스 생성자의 첫 번째 문은 기본 클래스에서 매개 변수가 있는 생성자를 호출 하거나 기본 클래스 생성자를 호출 하는 파생 클래스의 다른 생성자를 호출 해야 합니다.

 **오류 ID:** BC30148

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- `MyBase.New`필요한 매개 변수를 제공 하는를 호출 하거나 이러한 호출을 수행 하는 피어 생성자를 호출 합니다.

     예를 들어 기본 클래스에로 선언 된 생성자가 있는 경우 `Public Sub New(ByVal index as Integer)` 파생 클래스 생성자의 첫 번째 문은이 될 수 있습니다 `MyBase.New(100)` .

## <a name="see-also"></a>참고 항목

- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
