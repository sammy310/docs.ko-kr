---
title: SYSLIB0009 경고
description: 컴파일 시간 경고 SYSLIB0009를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 922fcc30b2b1577976e4e88e3f7631e19d4b2cce
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596358"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a>SYSLIB0009: AuthenticationManager 인증 및 PreAuthenticate 메서드가 지원되지 않음

다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다. 이러한 API를 사용하면 컴파일 시간에 `SYSLIB0009` 경고가 생성됩니다.

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a>경고를 표시하지 않음

코드를 변경할 수 없는 경우 `#pragma` 지시문 또는 `<NoWarn>` 프로젝트 설정을 통해 경고를 표시하지 않을 수 있습니다. 예제는 [경고 표시 안 함](../syslib-obsoletions.md#suppress-warnings)을 참조하세요.
