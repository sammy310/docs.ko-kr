---
description: "자세한 정보: BC40007: 기본 속성 ' '이 ( <propertyname1> 가) ' '의 기본 속성 ' '과 (와) 충돌 <propertyname2> <classname> 하므로 ' Shadows '로 선언 되어야 합니다."
title: 기본 속성 '<propertyname1>'은(는) '<propertyname2>'의 기본 속성 '<classname>'과(와) 충돌하므로 'Shadows'로 선언해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 8ec7e36da18bbf8dda35e1a521d64268d14b7b26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796641"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>BC40007: ' '의 기본 속성 ' '이 ( \<propertyname1> 가) ' '의 기본 속성 ' '과 (와) 충돌 \<propertyname2> \<classname> 하므로 ' s h a r '로 선언

속성이 기본 클래스에 정의 된 속성과 같은 이름으로 선언 되었습니다. 이 경우이 클래스의 속성은 기본 클래스 속성을 숨겨야 합니다.

 이 메시지는 경고입니다. 기본적으로`Shadows` 로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC40007

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 키워드를 `Shadows` 선언에 추가 하거나 선언 되는 속성의 이름을 변경 합니다.

## <a name="see-also"></a>참고 항목

- [Overloads](../modifiers/shadows.md)
- [Visual Basic에서 숨김](../../programming-guide/language-features/declared-elements/shadowing.md)
