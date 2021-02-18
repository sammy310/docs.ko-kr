---
title: '호환성이 손상되는 변경: WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨'
description: Windows Forms 앱에 대해 OutputType이 WinExe로 자동으로 설정되는 .NET SDK 5.0.100의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/18/2020
ms.openlocfilehash: 38d9b910374f9e44f7e35296808930c6a6d45f0d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431466"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨

WPF(Windows Presentation Foundation) 및 Windows Forms 앱에 대해 `OutputType`은 자동으로 `WinExe`로 설정됩니다. `OutputType`이 `WinExe`로 설정되면 앱 실행 시 콘솔 창이 열리지 않습니다.

## <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET SDK에서는 프로젝트 파일의 `OutputType`에 지정된 값이 사용됩니다. 예를 들면 다음과 같습니다.

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

.NET SDK의 5.0.100 버전부터, `OutputType`이 `Exe`로 설정된 경우에는 .NET Framework를 비롯한 모든 프레임워크 버전을 대상으로 하는 WPF 및 Windows Forms 앱에 대해 자동으로 `WinExe`로 변경됩니다.

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

 프로젝트 파일에서 `OutputType`이 지정되지 않으면 기본적으로 `Library`로 설정되고 값이 변경되지 않습니다.

## <a name="reason-for-change"></a>변경 이유

대부분 사용자가 WPF 또는 Windows Forms 앱 실행 시 콘솔 창이 열리기를 원하지 않는 것으로 가정합니다. 또한 [이제 이러한 애플리케이션 유형에 .NET SDK를 사용](sdk-and-target-framework-change.md)(Windows 데스크톱 SDK 아님)하므로 올바른 기본값이 설정됩니다. 또한 iOS 및 Android 대상 지정을 위한 지원이 추가되면 동일한 출력 형식이 사용되는 경우 여러 플랫폼 사이에 멀티 타기팅하기가 더 쉬워집니다.

## <a name="version-introduced"></a>도입된 버전

.NET 5.0.100

## <a name="recommended-action"></a>권장 조치

아무 작업도 수행할 필요가 없습니다. 하지만 이전 동작으로 되돌리려면 프로젝트 파일에서 `DisableWinExeOutputInference` 속성을 `true`로 설정합니다.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
