---
ms.openlocfilehash: 077eadb05ab16f5cec8817b89bc771de0c94aefa
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679329"
---
### <a name="publishdepsfilepath-behavior-change"></a>PublishDepsFilePath 동작 변경

단일 파일 애플리케이션의 `PublishDepsFilePath` MSBuild 속성이 비어 있습니다. 또한 비단일 파일 애플리케이션의 경우 빌드 후반까지는 *deps.json* 파일이 출력 디렉터리에 복사되지 않을 수도 있습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 `PublishDepsFilePath` MSBuild 속성은 비단일 파일 애플리케이션의 출력 디렉터리에 있는 앱 *deps.json* 파일의 경로이며 중간 디렉터리에 있는 단일 파일 앱 경로입니다.

.NET 5.0부터 단일 파일 애플리케이션의 `PublishDepsFilePath`는 비어 있으며 새로운 `IntermediateDepsFilePath` 속성이 중간 디렉터리 내의 *deps.json* 위치를 지정합니다. 또한 비단일 파일 애플리케이션의 경우 빌드 후반까지는 *deps.json* 파일이 출력 디렉터리(`PublishDepsFilePath`에 지정된 경로)에 복사되지 않을 수도 있습니다.

#### <a name="reason-for-change"></a>변경 이유

다음과 같은 몇 가지 이유로 이렇게 변경했습니다.

- .NET 5에서 [개선된 단일 파일 앱](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md)을 지원하기 위한 게시 논리의 리팩터링으로 인해.

- 단일 파일 앱에서 *deps.json*이 이미 번들된 후에 *deps.json* 파일을 다시 작성하는 대상을 방지하기 위해(따라서 자동으로 앱에 영향을 주지 않음). 이러한 이유로 단일 파일 애플리케이션의 `PublishDepsFilePath`가 비어 있습니다.

#### <a name="recommended-action"></a>권장 조치

*deps.json* 파일을 다시 작성하는 대상은 일반적으로 `IntermediateDepsFilePath` 속성을 사용하여 다시 작성해야 합니다.

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A

<!--

#### Affected APIs

Not detectable via API analysis.

-->
