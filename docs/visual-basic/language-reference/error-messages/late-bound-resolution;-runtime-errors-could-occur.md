---
title: 런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: ef0fa295cadaaa0550be4809ec97c6da13b5e2db
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160433"
---
# <a name="bc42017-late-bound-resolution-runtime-errors-could-occur"></a>BC42017: 런타임에 바인딩 확인; 런타임 오류가 발생할 수 있습니다.

개체는 [개체 데이터 형식](../data-types/object-data-type.md)으로 선언 된 변수에 할당 됩니다.

 변수를로 선언 하는 경우 `Object` 컴파일러는 런타임에 *바인딩을*수행 해야 하므로 런타임에 추가 작업이 발생 합니다. 또한 애플리케이션이 잠재적인 런타임 오류에 노출됩니다. 예를 들어를 변수에 할당 한 <xref:System.Windows.Forms.Form> `Object` 다음 속성에 액세스 하려고 하면 <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> <xref:System.MemberAccessException> <xref:System.Windows.Forms.Form> 클래스가 속성을 노출 하지 않기 때문에 런타임이을 throw 합니다 `NameTable` .

 변수를 특정 형식으로 선언 하는 경우 컴파일러는 컴파일 타임에 *초기 바인딩을* 수행할 수 있습니다. 이로 인해 성능이 향상 되 고, 특정 형식의 멤버에 대 한 액세스를 제어 하 고, 코드 가독성을 높일 수 있습니다.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC42017

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 가능 하면 변수를 특정 형식으로 선언 합니다.

## <a name="see-also"></a>참고 항목

- [초기 바인딩 및 런타임에 바인딩](../../programming-guide/language-features/early-late-binding/index.md)
- [개체 변수 선언](../../programming-guide/language-features/variables/object-variable-declaration.md)
