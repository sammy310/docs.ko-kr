---
description: "BC30920: ' <constructorname> '의 기본 클래스 ' '에 있는 ' '이 ( <baseclassname> <derivedclassname> 가) obsolete로 표시 되어 있으므로이 ' Sub n e w '의 첫 번째 문은 ' mybase.new ' 또는 ' m y s s. n e w '에 대 한 명시적 호출 이어야 합니다. '<errormessage>"
title: "'<constructorname>'의 기본 클래스 '<baseclassname>'에 있는 '<derivedclassname>'이(가) obsolete로 표시되어 있으므로 이 'Sub New'의 첫 번째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 명시적 호출이어야 합니다. '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 777543b7f29fb17dd5eb6a6196035ef0f18bb907
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796238"
---
# <a name="bc30920-first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a>BC30920: ' \<constructorname> '의 기본 클래스 ' '에 있는 ' '이 ( \<baseclassname> \<derivedclassname> 가) obsolete로 표시 되어 있으므로이 ' Sub n e w '의 첫째 문은 ' mybase.new ' 또는 ' m a s s. n e w '에 대 한 명시적 호출 이어야 합니다. \<errormessage> ' '

클래스 생성자는 기본 클래스 생성자를 명시적으로 호출하지 않으며, 암시적 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시되어 오류로 처리합니다.

 파생 클래스 생성자가 기본 클래스 생성자를 호출 하지 않는 경우 Visual Basic는 매개 변수가 없는 기본 클래스 생성자에 대 한 암시적 호출을 생성 하려고 시도 합니다. 인수 없이 호출 될 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없는 경우 Visual Basic는 암시적 호출을 생성할 수 없습니다. 이 경우 필요한 생성자는 특성으로 표시 <xref:System.ObsoleteAttribute> 되므로 Visual Basic 호출할 수 없습니다.

 프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다. 이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다. `True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다. `False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.

 **오류 ID:** BC30920

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.

2. `MyBase.New()` 또는 `MyClass.New()` 에 대한 호출을 파생 클래스에 `Sub New` 의 첫 번째 문으로 포함합니다.

## <a name="see-also"></a>참고 항목

- [특성 개요](../../programming-guide/concepts/attributes/index.md)
