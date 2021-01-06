---
title: SYSLIB0012 경고
description: 컴파일 시간 경고 SYSLIB0012를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 9b3fa94029efb2343e6dbbeb3ae36195f0956523
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596332"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012: Assembly.CodeBase 및 Assembly.EscapedCodeBase가 사용되지 않음

다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다. 코드에서 이러한 API를 사용하면 컴파일 시간에 `SYSLIB0012` 경고가 생성됩니다.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a>해결 방법

대신 <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>를 사용하세요.

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]
