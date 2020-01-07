---
title: Xamarin 제한 사항
ms.date: 12/13/2019
description: Xamarin을 사용할 때 발생 하는 몇 가지 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450407"
---
# <a name="xamarin-limitations"></a>Xamarin 제한 사항

Microsoft. Sqlite 대상은 .NET Standard 2.0 이며 Xamarin에서 지원 됩니다. 다음 표에서는 기본 SQLitePCLRaw 번들이에 대 한 기본 SQLite 이진 파일을 제공 하는 플랫폼을 보여 줍니다. 다른 번들 사용 또는 고유한 기본 SQLite 이진 파일 제공에 대 한 자세한 내용은 [사용자 지정 sqlite 버전](custom-versions.md) 을 참조 하세요.

| Platform | SQLite 이진 파일 |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Xamarin.Mac** | ✔ |
| **TVOS** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

SQLitePCLRaw 번들을 자동으로 초기화 하려고 합니다. 불행 하 게 Xamarin.ios에 대 한 AOT (사전) 컴파일의 제한 사항으로 인해 시도는 실패 하 고 다음과 같은 오류가 발생 합니다.

> `SQLitePCL.raw.SetProvider()`를 호출 해야 합니다. 번들 패키지를 사용 하는 경우 `SQLitePCL.Batteries.Init()`를 호출 하 여이 작업을 수행 합니다.

번들을 초기화 하려면 Microsoft. Sqlite를 사용 하기 전에 앱에 다음 코드 줄을 추가 합니다.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>참조

* [비동기 제한 사항](async.md)
* [사용자 지정 SQLite 버전](custom-versions.md)
