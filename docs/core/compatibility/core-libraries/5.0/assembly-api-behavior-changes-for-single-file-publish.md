---
title: '호환성이 손상되는 변경: 단일 파일 게시 형식에 대한 어셈블리 관련 API 동작 변경'
description: 단일 파일 게시 형식으로 호출될 때 어셈블리의 파일 위치와 관련된 여러 API의 동작이 변경되는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: d77e30318040c8298065073a41caab56f2ca3875
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759786"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a>단일 파일 게시 형식에 대한 어셈블리 관련 API 동작 변경

단일 파일 게시 형식으로 호출된 경우 어셈블리의 파일 위치와 관련된 여러 API의 동작이 변경되었습니다.

## <a name="change-description"></a>변경 내용 설명

.NET 5.0 이상 버전의 단일 파일 게시에서는 번들 어셈블리가 디스크에 추출되는 대신 메모리에서 로드됩니다. 이로 인해 단일 파일 게시 앱의 경우 .NET 5.0 이상과 이전 버전의 .NET에서 특정 위치 관련 API를 통해 반환되는 값이 서로 다릅니다. 변경 내용은 다음과 같습니다.

| API | 이전 버전 | .NET 5.0 이상 |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | 추출된 DLL 파일 경로를 반환합니다. | 번들 어셈블리에 대해 빈 문자열을 반환합니다. |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | 추출된 DLL 파일 경로를 반환합니다. | 번들 어셈블리에 대해 예외를 throw합니다. |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | 번들 어셈블리에 대해 `null`을 반환합니다. | 번들 어셈블리에 대해 예외를 throw합니다. |
| `Environment.GetCommandLineArgs()[0]` | 값은 진입점 DLL의 이름입니다. | 값은 호스트 실행 파일의 이름입니다. |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | 값은 임시 추출 디렉터리입니다. | 값은 호스트 실행 파일을 포함하는 디렉터리입니다. |

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

단일 파일로 게시하는 경우 어셈블리 파일 위치에 대한 종속성을 피합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
