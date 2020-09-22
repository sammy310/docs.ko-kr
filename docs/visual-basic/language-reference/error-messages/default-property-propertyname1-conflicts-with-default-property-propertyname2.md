---
title: 기본 속성 '<propertyname1>'은(는) '<propertyname2>'의 기본 속성 '<classname>'과(와) 충돌하므로 'Shadows'로 선언해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b857a9ae7875a156179602cbe77558333d07b7b9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874512"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>기본 속성 '\<propertyname1>'은(는) '\<propertyname2>'의 기본 속성 '\<classname>'과(와) 충돌하므로 'Shadows'로 선언해야 합니다.

속성이 기본 클래스에 정의 된 속성과 같은 이름으로 선언 되었습니다. 이 경우이 클래스의 속성은 기본 클래스 속성을 숨겨야 합니다.  
  
 이 메시지는 경고입니다. 기본적으로`Shadows` 로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40007  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 키워드를 `Shadows` 선언에 추가 하거나 선언 되는 속성의 이름을 변경 합니다.  
  
## <a name="see-also"></a>참조

- [Overloads](../modifiers/shadows.md)
- [Visual Basic에서 숨김](../../programming-guide/language-features/declared-elements/shadowing.md)
