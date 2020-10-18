---
title: 이름 <membername>은(는) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 43fff3f12295f3837148b0a349887e8405126819
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160238"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a>BC40031: 이름이 \<membername> CLS 규격이 아닙니다.

어셈블리가로 표시 되어 `<CLSCompliant(True)>` 있지만 이름이 밑줄 ()로 시작 하는 멤버를 노출 `_` 합니다.

 프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)를 준수 하려면 밑줄로 시작 하지 않아야 합니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.

 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.

 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC40031

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 소스 코드에 대 한 제어 권한이 있는 경우 밑줄로 시작 하지 않도록 멤버 이름을 변경 합니다.

- 멤버 이름이 변경 되지 않은 상태로 유지 되어야 하는 경우 해당 <xref:System.CLSCompliantAttribute> 정의에서를 제거 하거나로 표시 `<CLSCompliant(False)>` 합니다. 여전히 어셈블리를로 표시할 수 있습니다 `<CLSCompliant(True)>` .

## <a name="see-also"></a>참고 항목

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Visual Basic 명명 규칙](../../programming-guide/program-structure/naming-conventions.md)
