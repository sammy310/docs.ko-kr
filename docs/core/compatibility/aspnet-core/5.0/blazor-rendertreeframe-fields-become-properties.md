---
title: '호환성이 손상되는 변경: Blazor: RenderTreeFrame 읽기 전용 퍼블릭 필드가 속성이 됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: RenderTreeFrame 읽기 전용 퍼블릭 필드가 속성이 됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759607"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a>Blazor: RenderTreeFrame 읽기 전용 퍼블릭 필드가 속성이 됨

ASP.NET Core 3.0 및 3.1에서는 <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> 구조체가 <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> 등을 비롯한 다양한 `readonly public` 필드를 노출했습니다. ASP.NET Core 5.0 RC1 이상 버전에서는 모든 `readonly public` 필드가 `readonly public` 속성으로 변경되었습니다.

이 변경은 다음과 같은 이유로 인해 많은 개발자에게 영향을 주지는 않습니다.

* `.razor` 파일(또는 수동 <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> 호출)을 사용하여 구성 요소를 정의하는 앱이나 라이브러리는 이 형식을 직접 참조하지 않습니다.
* `RenderTreeFrame` 형식 자체는 프레임워크 외부에서 사용하기 위한 것이 아니라 구현 세부 정보로 간주됩니다. ASP.NET Core 3.0 이상에는 해당 형식이 직접 사용되는 경우 컴파일러 경고를 발생시키는 분석기가 포함되어 있습니다.
* `RenderTreeFrame`을 직접 참조하는 경우에도 이 변경은 소스 변경이 아니라 이진 변경입니다. 즉, 기존 소스 코드는 올바르게 컴파일하고 동작합니다. .NET Core 3.x 프레임워크에 대해 컴파일한 후 .NET 5.0 RC1 이상 프레임워크에 대해 이진 파일을 실행하는 경우에만 문제가 발생합니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 RC1

## <a name="old-behavior"></a>이전 동작

`RenderTreeFrame`의 퍼블릭 멤버는 필드로 정의됩니다. 예를 들어 `renderTreeFrame.Sequence` 및 `renderTreeFrame.ElementName`를 지정합니다.

## <a name="new-behavior"></a>새 동작

`RenderTreeFrame`의 퍼블릭 멤버는 이전과 동일한 이름의 속성으로 정의됩니다. 예를 들어 `renderTreeFrame.Sequence` 및 `renderTreeFrame.ElementName`를 지정합니다.

이 변경 후 이전에 미리 컴파일된 코드를 다시 컴파일하지 않은 경우 다음과 비슷한 예외가 throw될 수 있습니다. *MissingFieldException: 필드를 찾을 수 없습니다. ‘Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType’* .

## <a name="reason-for-change"></a>변경 이유

ASP.NET Core 5.0에서 Blazor 구성 요소 렌더링에 큰 영향을 주는 성능 개선을 구현하기 위해 이러한 변경이 필요했습니다. 동일한 수준의 안전 및 캡슐화를 유지 관리합니다.

## <a name="recommended-action"></a>권장 조치

대부분의 Blazor 개발자는 이러한 변경의 영향을 받지 않습니다. 이 변경은 아주 드문 경우에 라이브러리 및 패키지 작성자에게 영향을 미칠 가능성이 더 큽니다. 특히 다음과 같은 경우:

* 앱을 개발하는 중이며 ASP.NET Core 3.x 버전을 사용하거나 5.0 RC1 이상으로 업그레이드하는 경우 고유한 코드를 변경할 필요가 없습니다. 하지만 이 변경을 고려하여 업그레이드된 라이브러리에 의존하는 경우에는 해당 라이브러리의 최신 버전으로 업데이트해야 합니다.
* 라이브러리를 개발하는 중이며 ASP.NET Core 5.0 RC1 이상만 지원하려는 경우 아무 작업도 필요하지 않습니다. 프로젝트 파일에서 `<TargetFramework>` 값을 `net5.0` 이상 버전으로 선언해야 합니다.
* 라이브러리를 개발하는 중이며 ASP.NET Core 3.x 및 5.0을 ‘모두’ 지원하려는 경우 코드에서 `RenderTreeFrame` 멤버를 읽도록 할지를 결정합니다. 예를 들어 `someRenderTreeFrame.FrameType`을 평가합니다.
  * 대부분의 라이브러리는 `.razor` 구성 요소를 포함하는 라이브러리를 비롯하여 `RenderTreeFrame` 멤버를 읽지 않습니다. 이 경우 아무 작업도 필요하지 않습니다.
  * 그러나 라이브러리가 해당 멤버를 읽는 경우에는 `netstandard2.1` 및 `net5.0`을 모두 지원하기 위해 멀티 타기팅해야 합니다. 프로젝트 파일에서 다음과 같이 변경을 적용합니다.
    * 기존 `<TargetFramework>` 요소를 `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`로 바꿉니다.
    * 지원하려는 두 버전을 모두 고려하여 조건부 `Microsoft.AspNetCore.Components` 패키지 참조를 사용합니다. 예를 들면 다음과 같습니다.

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

추가 설명을 보려면 [@jsakamoto가 `Toolbelt.Blazor.HeadElement` 라이브러리를 이미 업그레이드한 방법을 보여 주는 diff](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51)를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
