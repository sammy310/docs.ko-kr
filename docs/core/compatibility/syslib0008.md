---
title: SYSLIB0008 경고
description: 컴파일 시간 경고 SYSLIB0008을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440597"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008: CreatePdbGenerator가 지원되지 않음

<xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다. 이 API를 사용하면 컴파일 시간에 `SYSLIB0008` 경고가 생성됩니다.

## <a name="suppress-the-warning"></a>경고를 표시하지 않음

코드를 변경할 수 없는 경우 `#pragma` 지시문 또는 `<NoWarn>` 프로젝트 설정을 통해 경고를 표시하지 않을 수 있습니다. 예제는 [경고 표시 안 함](syslib-obsoletions.md#suppress-warnings)을 참조하세요.
