---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174267"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a>Blazor: 컴파일 시간에 구성 요소에서 중요하지 않은 공백을 자름

ASP.NET Core 5.0 미리 보기 7부터 Razor 컴파일러는 컴파일 시간에 Blazor 구성 요소( *.razor* 파일)에서 중요하지 않은 공백을 생략합니다. 자세한 내용은 이슈 [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 7

#### <a name="old-behavior"></a>이전 동작

Blazor Server 및 Blazor WebAssembly의 3.x 버전에서는 구성 요소의 소스 코드에서 공백이 적용됩니다. 공백만 있는 텍스트 노드는 시각적 효과가 없는 경우에도 브라우저의 DOM(문서 개체 모델)에서 렌더링됩니다.

다음 Blazor 구성 요소 코드를 고려합니다.

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

앞의 예제에서는 다음 위치에서 두 개의 공백 노드를 렌더링합니다.

* `@foreach` 코드 블록의 외부
* `<li>` 요소의 주위
* `@item.Text` 출력의 주위

100개 항목을 포함하는 목록은 402개 공백 노드를 생성합니다. 공백 노드가 렌더링된 출력에 시각적으로 영향을 주지 않더라도 해당 개수는 렌더링된 모든 노드의 절반을 초과합니다.

구성 요소의 정적 HTML을 렌더링하면 태그 안의 공백이 유지되지 않습니다. 예를 들어 다음 구성 요소의 소스를 봅니다.

```razor
<foo        bar="baz"     />
```

공백이 유지되지 않습니다. 미리 렌더링된 출력은 다음과 같습니다.

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a>새 동작

`@preservewhitespace` 지시문이 `true` 값과 함께 사용되지 않을 때 공백 노드가 제거되는 경우는 다음과 같습니다.

* 공백 노드가 요소 내에서 선행 또는 후행인 경우
* 공백 노드가 `RenderFragment` 매개 변수 내에서 선행 또는 후행인 경우(예: 자식 콘텐츠가 다른 구성 요소로 전달됨)
* 공백 노드가 `@if` 및 `@foreach`와 같은 C# 코드 블록의 앞 또는 뒤에 있는 경우

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 5.0에서 Blazor의 목표는 렌더링 및 diff 수행 성능을 향상하는 것입니다. 중요하지 않은 공백 트리 노드는 벤치마크에서 렌더링 시간의 최대 40%를 사용했습니다.

#### <a name="recommended-action"></a>권장 조치

대부분의 경우 렌더링된 구성 요소의 시각적 레이아웃에는 영향을 받지 않습니다. 그러나 `white-space: pre` 같은 CSS 규칙을 사용하는 경우 공백 제거는 렌더링된 출력에 영향을 줄 수 있습니다. 성능 최적화를 사용하지 않고 공백을 유지하려면 다음 작업 중 하나를 수행합니다.

* *.razor* 파일의 맨 위에 `@preservewhitespace true` 지시문을 추가하여 특정 구성 요소에 기본 설정을 적용합니다.
* *_Imports.razor* 파일 안에 `@preservewhitespace true` 지시문을 추가하여 전체 하위 디렉터리 또는 전체 프로젝트에 기본 설정을 적용합니다.

대부분의 경우 애플리케이션은 대개 계속해서 정상적으로(그러나 더 빠르게) 동작하므로 필요한 작업이 없습니다. 공백 제거 시 특정 구성 요소에 문제가 발생하는 경우에는 해당 구성 요소에서 `@preservewhitespace true`를 사용하여 최적화를 사용하지 않도록 설정합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

#### Affected APIs

Not detectable via API analysis

-->
