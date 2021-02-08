---
description: "자세한 내용은 다음에 대해 자세히 알아보세요. BC30617: ' Module ' 문은 파일이 나 네임 스페이스 수준 에서만 발생할 수 있습니다."
title: "'Module' 문은 파일이나 네임스페이스 수준에서만 사용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: f5c3ea0cd1c08fb0243043ae50e707e2c59b00f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795783"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a>BC30617: ' Module ' 문은 파일이 나 네임 스페이스 수준 에서만 발생할 수 있습니다.

`Module` 문은 소스 파일의 맨 위에 `Option` 및 `Imports` 문, 전역 특성 및 네임 스페이스 선언 바로 뒤에, 다른 모든 선언 앞에 표시 되어야 합니다.

 **오류 ID:** BC30617

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- `Module` 문을 네임스페이스 선언 또는 원본 파일의 맨 위로 이동합니다.

## <a name="see-also"></a>참고 항목

- [Module 문](../statements/module-statement.md)
