---
description: 'BC40033: cls 규격이 아닌 경우에 대 한 자세한 내용은 <membername> cls 규격 인터페이스에서 사용할 수 없습니다.'
title: CLS 규격 인터페이스에는 CLS 규격이 아닌 <membername>을(를) 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: 070b56a8bf9df930de5bb5e363a9b157fcdc7ad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795640"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>BC40033: cls \<membername> 규격 인터페이스에는 cls 규격이 아닙니다.

인터페이스의 속성, 프로시저 또는 이벤트는 `<CLSCompliant(True)>` 인터페이스 자체가로 표시 `<CLSCompliant(False)>` 되거나 표시 되지 않는 경우로 표시 됩니다.

 인터페이스가 [언어 독립성 및 CLS (Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) )를 준수 하 게 하려면 모든 멤버가 규격 이어야 합니다.

 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.

 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC40033

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어 해야 하는 경우 인터페이스를 `<CLSCompliant(True)>` 모든 멤버가 규정을 준수 하는 것으로 표시 합니다.

- CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어할 수 없는 경우 또는 규격이 아닌 경우 다른 인터페이스 내에서이 멤버를 정의 합니다.

- 이 멤버를 현재 인터페이스 내에 유지 해야 하는 경우 해당 <xref:System.CLSCompliantAttribute> 정의에서를 제거 하거나로 표시 `<CLSCompliant(False)>` 합니다.

## <a name="see-also"></a>참고 항목

- [Interface 문](../statements/interface-statement.md)
