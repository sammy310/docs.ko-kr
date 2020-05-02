---
title: Xamarin 제한 사항
ms.date: 12/13/2019
description: Xamarin을 사용할 때 발생할 수 있는 몇 가지 제한 사항에 대해 설명합니다.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450407"
---
# <a name="xamarin-limitations"></a>Xamarin 제한 사항

Microsoft.Data.Sqlite는 .NET Standard 2.0을 대상으로 하며 Xamarin에서 지원됩니다. 다음 표에서는 기본 SQLitePCLRaw 번들이 네이티브 SQLite 이진 파일을 제공하는 플랫폼을 보여줍니다. 다른 번들을 사용하거나 고유한 네이티브 SQLite 이진 파일을 제공하는 방법에 대한 자세한 내용은 [사용자 지정 SQLite 버전](custom-versions.md)을 참조하세요.

| 플랫폼 | SQLite 이진 파일 |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Xamarin.Mac** | ✔ |
| **Xamarin.TVOS** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

Microsoft.Data.Sqlite는 SQLitePCLRaw 번들을 자동으로 초기화하려고 합니다. 불행하게도 Xamarin.iOS에 대한 AOT(ahead-of-time) 컴파일의 제한 사항으로 인해 시도는 실패하고 다음과 같은 오류가 발생합니다.

> `SQLitePCL.raw.SetProvider()`를 호출해야 합니다. 번들 패키지를 사용하는 경우 `SQLitePCL.Batteries.Init()`를 호출하여 이 작업을 수행합니다.

번들을 초기화하려면 Microsoft.Data.Sqlite를 사용하기 전에 앱에 다음 코드 줄을 추가합니다.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>참조

* [비동기 제한 사항](async.md)
* [사용자 지정 SQLite 버전](custom-versions.md)
