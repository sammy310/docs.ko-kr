---
title: WPF 호환성이 손상되는 변경
description: Windows Presentation Framework에서 .NET Core 및 .NET 5에 대한 호환성이 손상되는 변경을 나열합니다.
ms.date: 09/08/2020
ms.openlocfilehash: 3bd5cb585509118fbc3ca9ca08c6ed15b4853b93
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679307"
---
# <a name="breaking-changes-in-windows-presentation-framework-wpf"></a>WPF(Windows Presentation Framework)의 호환성이 손상되는 변경

WPF 지원이 버전 3.0의 .NET Core에 추가되었습니다. 이 문서에서는 WPF의 호환성이 손상되는 변경을 .NET 버전(해당 변경이 도입된 버전)을 기준으로 나열합니다. .NET Framework에서 또는 이전 버전의 .NET Core(3.0 이상)에서 WPF 앱을 업그레이드하는 경우 이 문서가 적용됩니다.

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | 5.0 |
| [WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함](#winforms-and-wpf-apps-use-microsoftnetsdk) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***
