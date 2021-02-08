---
description: "자세한 정보: ' ' <attribute> GUID ' '의 형식이 올바르지 않기 때문에 BC32500: ' '을 (를) 적용할 수 없습니다. <number>"
title: "'GUID '<attribute>'의 형식이 올바르지 않으므로 '<number>'을(를) 적용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: a527608aebf338a5877bb3439f45fc79a40f5ac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797135"
---
# <a name="bc32500-attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>\<attribute>GUID ' '의 형식이 올바르지 않으므로 BC32500: ' '을 (를) 적용할 수 없습니다. \<number>

`COMClassAttribute`특성 블록은 guid의 적절 한 형식을 따르지 않는 guid (globally unique identifier)를 지정 합니다. `COMClassAttribute` 는 Guid를 사용 하 여 클래스, 인터페이스 및 생성 이벤트를 고유 하 게 식별 합니다.

 GUID는 16바이트로 구성되며, 그중에서 처음 8바이트는 숫자이고 마지막 8바이트는 이진입니다. uuidgen.exe와 같은 Microsoft 유틸리티에서 생성 되며 공백과 시간에서 고유 하 게 보장 됩니다.

 **오류 ID:** BC32500

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. COM 개체를 식별 하는 데 필요한 올바른 GUID 또는 guid를 확인 합니다.

2. `COMClassAttribute` 특성 블록에 제공되는 GUID 문자열이 올바르게 복사되었는지 확인합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Guid>
- [특성 개요](../../programming-guide/concepts/attributes/index.md)
