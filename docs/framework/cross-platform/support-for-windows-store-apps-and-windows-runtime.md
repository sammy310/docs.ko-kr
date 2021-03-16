---
description: '자세한 정보: Microsoft Store 앱 및 Windows 런타임에 대한 .NET Framework 지원'
title: Microsoft Store 앱 및 Windows 런타임에 대한 .NET Framework 지원
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
ms.openlocfilehash: 851deb30420eb19c4fe2037bebe2cf8f84743c49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402264"
---
# <a name="net-framework-support-for-microsoft-store-apps-and-windows-runtime"></a>Microsoft Store 앱 및 Windows 런타임에 대한 .NET Framework 지원

.NET Framework 4.5는 Windows 런타임을 사용하는 다양한 소프트웨어 개발 시나리오를 지원합니다. 이러한 시나리오는 다음 세 가지 범주로 구분됩니다.

- [C# 또는 Visual Basic을 사용하는 Windows 스토어 앱용 로드맵](/previous-versions/windows/apps/br229583(v=win.10)), [방법(XAML)](/previous-versions/windows/apps/br229566(v=win.10)) 및 [Windows 스토어 앱용 .NET 개요](/previous-versions/windows/apps/br230302(v=vs.140))에 설명된 대로 XAML 컨트롤을 사용하여 Windows 8.x 스토어 앱 개발.

- .NET Framework로 만든 Windows 8.x 스토어 앱에서 사용할 클래스 라이브러리 개발.

- Windows 런타임을 지원하는 모든 프로그래밍 언어에서 사용할 수 있는 .WinMD 파일에서 패키지된 Windows 런타임 구성 요소 개발. 예를 들어 [C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)를 참조하세요.

이 문서에서는 .NET Framework에서 모든 세 가지 범주에 대해 제공하는 지원을 간략하게 설명하고 Windows 런타임 구성 요소에 대한 시나리오를 설명합니다. 첫 번째 섹션에서는 .NET Framework와 Windows 런타임 사이의 관계에 대한 기본 정보가 포함되어 있으며 도움말 시스템 및 IDE에서 발생할 수 있는 일부 의문 사항을 설명합니다. [두 번째 섹션](#WindowsRuntimeComponents)에서는 Windows 런타임 구성 요소의 개발에 대한 시나리오를 설명합니다.

## <a name="the-basics"></a>기본 사항

.NET Framework는 Windows 8.x 스토어 앱용 .NET를 제공하고 Windows 런타임 자체를 지원하여 앞서 설명한 세 가지 개발 시나리오를 지원합니다.

- [.NET Framework 및 Windows 런타임 네임스페이스](/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces)는 .NET Framework 클래스 라이브러리를 간소화된 보기로 제공하고 Windows 8.x 스토어 앱 및 Windows 런타임 구성 요소를 만드는 데 사용할 수 있는 형식과 멤버만 포함합니다.

  - Visual Studio(Visual Studio 2012 이상)를 사용하여 Windows 8.x 스토어 앱 또는 Windows 런타임 구성 요소를 개발하는 경우 참조 어셈블리 집합은 관련 형식 및 멤버만 볼 수 있게 합니다.

  - 이 간소화된 API 집합은 .NET Framework 내에서 복제되었거나 Windows 런타임 기능을 복제하는 기능을 제거하여 더욱 간단해졌습니다. 예를 들어, 컬렉션 형식의 제네릭 버전만 포함하고, XML 문서 개체 모델은 Windows 런타임 XML API 집합을 위해 제거됩니다.

  - Windows 런타임을 관리 코드에서 쉽게 호출할 수 있기 때문에 단순히 운영 체제 API를 래핑하는 기능 또한 제거됩니다.

  Windows 8.x 스토어 앱용 .NET에 대한 자세한 내용은 [Windows 스토어 앱용 .NET 개요](/previous-versions/windows/apps/br230302(v=vs.140))를 참조하세요. API 선택 프로세스에 대한 내용을 보려면 .NET 블로그의 [Metro 스타일 앱용 .NET](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) 항목을 참조하세요.

- [Windows 런타임](/uwp/api/)은 Windows 8.x 스토어 앱을 빌드하기 위한 사용자 인터페이스 요소를 제공하고 운영 체제 기능에 대한 액세스를 제공합니다. .NET Framework와 같이 Windows 런타임에는 C# 및 Visual Basic 컴파일러가 .NET Framework 클래스 라이브러리를 사용하는 방식과 같이 Windows 런타임을 사용할 수 있는 메타데이터가 있습니다. .NET Framework에서는 다음과 같이 일부 차이점을 숨겨 Windows 런타임을 좀 더 쉽게 사용할 수 있습니다.

  - .NET Framework와 Windows 런타임 사이의 몇몇 프로그래밍 패턴 차이점(예: 이벤트 처리기를 추가 및 제거하기 위한 패턴)은 숨겨져 있습니다. .NET Framework 패턴을 그대로 사용하면 됩니다.

  - 자주 사용되는 형식(예: 기본 형식 및 컬렉션)의 일부 차이점이 숨겨져 있습니다. 이 문서의 뒷부분에 나오는 [IDE에서 표시되는 차이점](#DifferencesVisibleInIDE)에서 설명된 대로 .NET Framework 형식을 그대로 사용하면 됩니다.

대부분의 경우 Windows 런타임에 대한 .NET Framework 지원은 투명합니다. 다음 섹션에서는 관리 코드와 Windows 런타임 사이의 일부 명백한 차이점을 설명합니다.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework 및 Windows 런타임 참조 설명서

Windows 런타임 설명서 집합과 .NET Framework 설명서 집합은 별개입니다. 형식이나 멤버에 도움말을 표시하기 위해 F1 키를 누르면, 적절한 집합의 참조 설명서가 표시됩니다. 그러나 [Windows 런타임 참조](/uwp/api/)를 탐색할 경우 다음과 같이 난해할 수 있는 예제를 볼 수 있습니다.

- <xref:Windows.Foundation.Collections.IIterable%601> 인터페이스와 같은 항목에는 Visual Basic 또는 C#용 선언 구문이 없습니다. 대신, 구문 섹션 위에 메모가 표시됩니다(이 경우 ".NET: 이 인터페이스는 System.Collections.Generic.IEnumerable\<T>로 나타납니다."). 이는 .NET Framework와 Windows 런타임이 서로 다른 인터페이스로 비슷한 기능을 제공하기 때문입니다. 게다가 동작의 차이점도 있습니다. 예를 들면 `IIterable`은 `First` 메서드 대신에 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드를 사용하여 열거자를 반환합니다. 일반적인 작업을 수행하는 다른 방법을 배우도록 강요하는 대신, .NET Framework는 관리 코드가 익숙한 형식을 사용하는 것처럼 보이게 하여 Windows 런타임을 지원합니다. IDE에서 `IIterable` 인터페이스를 볼 수 없으므로 Windows 런타임 참조 설명서에서 확인할 수 있는 유일한 방법은 해당 설명서를 직접 살펴보는 것입니다.

- <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> 설명서에서 밀접하게 관련된 문제를 보여 줍니다. 해당 매개 변수 형식이 언어마다 다르게 나타납니다. C# 및 Visual Basic의 경우 매개 변수 형식은 <xref:System.String?displayProperty=nameWithType> 및 <xref:System.Uri?displayProperty=nameWithType>입니다. 즉, .NET Framework에 자체 `String` 및 `Uri` 형식이 있고, 이같이 자주 사용되는 형식에 대해 다른 작업 방식을 배우도록 .NET Framework 사용자를 강요하는 것이 적합하지 않기 때문입니다. IDE에서 .NET Framework는 해당 Windows 런타임 형식을 숨깁니다.

- <xref:Windows.UI.Xaml.GridLength> 구조체와 같은 일부의 경우 .NET Framework에서 이름은 같지만 기능이 더 많은 형식을 제공합니다. 예를 들어, 생성자 및 속성 항목 집합은 `GridLength`와 연관되어 있지만, 멤버를 관리 코드에서만 사용할 수 있기 때문에 Visual Basic 및 C#용 구문 블록만 있습니다. Windows 런타임에서 구조체는 필드만 가지고 있습니다. Windows 런타임 구조체에는 동일한 기능을 제공하기 위해 도우미 클래스 <xref:Windows.UI.Xaml.GridLengthHelper>가 필요합니다. 관리 코드를 작성할 때 IDE에서 도우미 클래스를 볼 수 없습니다.

- IDE에서 Windows 런타임 형식은 <xref:System.Object?displayProperty=nameWithType>에서 파생되어 나타납니다. <xref:System.Object>과 같은 <xref:System.Object.ToString%2A?displayProperty=nameWithType>에서 상속된 멤버를 가진 것으로 나타납니다. 이러한 멤버는 형식이 실제로 <xref:System.Object>에서 상속된 것처럼 작동하고, Windows 런타임 형식은 <xref:System.Object>로 캐스팅할 수 있습니다. 이 기능은 Windows 런타임에 대해 .NET Framework가 제공하는 지원의 일부입니다. 그러나 Windows 런타임 참조 설명서에서 형식을 볼 경우 이러한 멤버는 표시되지 않습니다. 이 상속된 명백한 멤버에 대한 문서는 <xref:System.Object?displayProperty=nameWithType> 참조 문서에서 제공합니다.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>IDE에서 표시되는 차이점

더 많은 고급 프로그래밍 시나리오(예: JavaScript를 사용하여 Windows용으로 빌드한 Windows 8.x 스토어 앱에 대한 애플리케이션 논리를 제공하는 데 C#에서 작성된 Windows 런타임 구성 요소 사용)에서 이러한 차이점은 IDE와 설명서 모두에서 명백합니다. 구성 요소가 `IDictionary<int, string>`을 JavaScript로 반환하고 이를 JavaScript 디버거에서 살펴보면, JavaScript는 Windows 런타임 형식을 사용하므로 `IMap<int, string>`의 메서드를 볼 수 있습니다. 두 언어에서 다르게 나타나는 일반적으로 사용되는 컬렉션 형식의 일부는 다음 표에 표시됩니다.

|Windows 런타임 형식|해당 .NET Framework 형식|
|--------------------------------------------------------------|---------------------------------------|
|`IIterable<T>`|`IEnumerable<T>`|
|`IIterator<T>`|`IEnumerator<T>`|
|`IVector<T>`|`IList<T>`|
|`IVectorView<T>`|`IReadOnlyList<T>`|
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|
|`IBindableIterable`|`IEnumerable`|
|`IBindableVector`|`IList`|
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|

Windows 런타임에서 `IMap<K, V>`와 `IMapView<K, V>`는 `IKeyValuePair`를 사용하며 반복됩니다. 관리 코드에 전달되면 이들은 `IDictionary<TKey, TValue>` 및 `IReadOnlyDictionary<TKey, TValue>`로 표시되므로 당연히 `System.Collections.Generic.KeyValuePair<TKey, TValue>`를 사용하여 열거해야 합니다.

인터페이스가 관리 코드에 표시되는 방식은 이러한 인터페이스를 구현하는 형식이 표시되는 방식에 영향을 미칩니다. 예를 들어 `PropertySet` 클래스는 관리되는 코드에 `IDictionary<TKey, TValue>`로 나타나는 `IMap<K, V>`를 구현합니다. `PropertySet`에서 `IMap<K, V>` 대신 `IDictionary<TKey, TValue>`가 구현된 것으로 나타나므로 관리되는 코드에서는 .NET Framework 사전의 `Add` 메서드처럼 동작하는 `Add` 메서드가 있는 것으로 나타납니다. 이 클래스는 `Insert` 메서드를 가지고 있는 것으로 보이지 않습니다.

.NET Framework를 사용하여 Windows 런타임 구성 요소를 만드는 방법 및 JavaScript와 함께 이러한 구성 요소를 사용하는 방법을 보여 주는 연습에 대한 자세한 내용은 [C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)를 참조하세요.

### <a name="primitive-types"></a>기본 유형

관리 코드에서 Windows 런타임을 자연스럽게 사용할 수 있도록 코드에서 Windows 런타임 기본 형식 대신 .NET Framework 기본 형식이 나타납니다. .NET Framework에서 `Int32` 구조체와 같은 기본 형식에는 `Int32.TryParse` 메서드 등 유용한 속성 및 메서드가 많이 포함되어 있습니다. 반면, Windows 런타임의 기본 형식 및 구조에는 필드만 있습니다. 관리 코드에서 기본 형식을 사용할 때 .NET Framework 형식으로 표시되고, 평소와 같이 .NET Framework 형식의 속성 및 메서드를 사용할 수 있습니다. 다음 목록은 요약을 제공합니다.

- Windows 런타임 기본 형식인 `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String`(변경할 수 없는 유니코드 문자 컬렉션), `Enum`, `UInt32`, `UInt64` 및 `Guid`의 경우 `System` 네임스페이스에 있는 동일한 이름의 형식을 사용합니다.

- `UInt8`의 경우 `System.Byte`을 사용합니다.

- `Char16`의 경우 `System.Char`을 사용합니다.

- `IInspectable` 인터페이스에 대해 `System.Object`를 사용합니다.

- `HRESULT`에 대해 하나의 `System.Int32` 멤버가 있는 구조체를 사용합니다.

인터페이스 형식에서처럼, .NET Framework 프로젝트가 JavaScript를 사용하여 빌드된 Windows 8.x 스토어 앱에서 사용하는 Windows 런타임 구성 요소일 때에만 이 표현의 증거를 볼 수 있습니다.

관리 코드에 해당 .NET Framework 형식으로 표시되는 일반적으로 사용되는 다른 기본 Windows 런타임 형식에는 `Windows.Foundation.DateTime` 구조체(관리 코드에 <xref:System.DateTimeOffset?displayProperty=nameWithType> 구조체로 표시됨) 및 `Windows.Foundation.TimeSpan` 구조체(<xref:System.TimeSpan?displayProperty=nameWithType> 구조체로 표시됨)가 포함됩니다.

### <a name="other-differences"></a>기타 차이점

일부의 경우 Windows 런타임 형식 대신 .NET Framework 형식이 코드에 나타나는 사실로 보아 사용자가 수행해야 할 작업이 있습니다. 예를 들어 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 .NET Framework 코드에서 <xref:System.Uri?displayProperty=nameWithType>로 나타납니다. <xref:System.Uri?displayProperty=nameWithType>는 상대 URI를 허용하지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType>에는 절대 URI가 필요합니다. 따라서 URI를 Windows 런타임 메서드로 전달할 때 URI가 절대적인지 확인해야 합니다. [Windows 런타임에 URI 전달](passing-a-uri-to-the-windows-runtime.md)을 참조하세요.

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Windows 런타임 구성 요소를 개발하기 위한 시나리오

관리 Windows 런타임 구성 요소에 대해 지원되는 시나리오는 다음 일반 원칙에 따라 다릅니다.

- .NET Framework를 사용하여 빌드된 Windows 런타임 구성 요소는 다른 Windows 런타임 라이브러리와 명백한 차이점이 없습니다. 예를 들어 관리 코드를 사용하여 네이티브 Windows 런타임 구성 요소를 다시 구현하는 경우, 두 구성 요소는 외적으로 구별할 수 없습니다. 코드 그 자체가 관리 코드이더라도 구성 요소가 관리 코드로 작성되었다는 사실은 그것을 사용하는 코드에 표시되지 않습니다. 그러나 내부적으로 구성 요소는 실제 관리 코드이며 CLR(공용 언어 런타임)에서 실행됩니다.

- 구성 요소는 애플리케이션 논리, Windows 8.x 스토어 UI 컨트롤 또는 둘 모두를 구현하는 형식을 포함할 수 있습니다.

  > [!NOTE]
  > UI 요소를 애플리케이션 논리에서 분리하는 것이 좋습니다. 또한 JavaScript 및 HTML을 사용하여 Windows용으로 빌드한 Windows 8.x 스토어 앱에서 Windows 8.x 스토어 UI 컨트롤을 사용할 수 없습니다.

- 구성 요소는 Windows 8.x 스토어 앱용 Visual Studio 솔루션 내의 프로젝트이거나 여러 솔루션에 추가할 수 있는 재사용 가능한 구성 요소일 수 있습니다.

  > [!NOTE]
  > 구성 요소가 C# 또는 Visual Basic에서만 사용될 경우에는 Windows 런타임 구성 요소로 만들 필요가 없습니다. 대신 일반적인 .NET Framework 클래스 라이브러리로 만들 경우 Windows 런타임 형식에 대해 공용 API 화면을 제한할 필요가 없습니다.

- 서로 다른 버전에 추가된 형식(및 형식 내 멤버)을 식별하려면 Windows 런타임 <xref:Windows.Foundation.Metadata.VersionAttribute> 특성을 사용하여 여러 버전의 재사용 가능한 구성 요소를 릴리스할 수 있습니다.

- 구성 요소의 형식은 Windows 런타임 형식에서 파생될 수 있습니다. 컨트롤은 <xref:Windows.UI.Xaml.Controls.Primitives> 네임스페이스의 기본 컨트롤 형식 또는 <xref:Windows.UI.Xaml.Controls.Button>와 같은 보다 완성된 컨트롤에서 파생될 수 있습니다.

  > [!IMPORTANT]
  > Windows 8 및 .NET Framework 4.5부터 관리되는 Windows 런타임 구성 요소의 모든 공용 형식은 봉인되어야 합니다. 다른 Windows 런타임 구성 요소의 형식은 여기서 파생될 수 없습니다. 구성 요소에서 다형 동작을 제공하려면 인터페이스를 만들어 다형 형식에서 구현할 수 있습니다.

- 구성 요소에서 공용 형식에 대한 모든 매개 변수 및 반환 형식은 Windows 런타임 형식(구성 요소가 정의하는 Windows 런타임 형식 포함)이어야 합니다.

다음 섹션에서는 일반적인 시나리오의 예제를 제공합니다.

### <a name="application-logic-for-a-windows-8x-store-app-with-javascript"></a>JavaScript를 사용하는 Windows 8.x 스토어 앱에 대한 애플리케이션 논리

JavaScript를 사용하여 Windows용으로 Windows 8.x 스토어 앱을 개발할 때 관리 코드에서 애플리케이션 논리의 일부가 더 잘 수행되거나 개발하기 더 쉬울 수도 있습니다. JavaScript는 .NET Framework 클래스 라이브러리를 직접 사용할 수 없지만, 이 클래스 라이브러리를 .WinMD 파일로 만들 수 있습니다. 이 시나리오에서 Windows 런타임 구성 요소는 앱의 핵심 부분이므로 버전 특성을 제공하는 것은 바람직하지 않습니다.

### <a name="reusable-windows-8x-store-ui-controls"></a>재사용 가능한 Windows 8.x 스토어 UI 컨트롤

관련된 UI 컨트롤 집합을 재사용 가능한 Windows 런타임 구성 요소에 패키지할 수 있습니다. 구성 요소는 직접 시장에 출시하거나 사용자가 만든 앱의 요소로서 사용할 수 있습니다. 이 시나리오에서는 Windows 런타임 <xref:Windows.Foundation.Metadata.VersionAttribute> 특성을 사용하여 호환성을 향상하는 것이 좋습니다.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>기존 .NET Framework 앱의 재사용 가능한 애플리케이션 논리

기존 데스크톱 앱에서 관리 코드를 독립 실행형 Windows 런타임 구성 요소로 패키지할 수 있습니다. 따라서 C++ 또는 JavaScript를 사용하여 빌드한 Windows 8.x 스토어 앱과 C# 또는 Visual Basic을 사용하여 빌드한 Windows 8.x 스토어 앱 모두에서 구성 요소를 사용할 수 있습니다. 코드를 재사용하는 시나리오가 여러 개일 경우 버전 관리는 옵션입니다.

## <a name="related-topics"></a>관련 항목

|제목|Description|
|-----------|-----------------|
|[Windows 스토어 앱용 .NET 개요](/previous-versions/windows/apps/br230302(v=vs.140))|Windows 8.x 스토어 앱 및 Windows 런타임 구성 요소를 만드는 데 사용할 수 있는 .NET Framework 형식 및 멤버를 설명합니다. (Windows 개발자 센터)|
|[C# 또는 Visual Basic을 사용한 Windows 스토어 앱용 로드맵](/previous-versions/windows/apps/br229583(v=win.10))|C# 또는 Visual Basic을 사용하여 Windows 8.x 스토어 앱을 개발하기 시작할 때 도움을 주기 위해 다양한 빠른 시작 항목, 지침 및 모범 사례를 포함한 주요 리소스를 제공합니다. (Windows 개발자 센터)|
|[방법(XAML)](/previous-versions/windows/apps/br229566(v=win.10))|C# 또는 Visual Basic을 사용하여 Windows 8.x 스토어 앱을 개발하기 시작할 때 도움을 주기 위해 다양한 빠른 시작 항목, 지침 및 모범 사례를 포함한 주요 리소스를 제공합니다. (Windows 개발자 센터)|
|[C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|.NET Framework를 사용하여 Windows 런타임 구성 요소를 만드는 방법, JavaScript를 사용하여 Windows용으로 빌드한 Windows 8.x 스토어 앱의 일부로 사용하는 방법 및 Visual Studio로 조합을 디버깅하는 방법을 설명합니다. (Windows 개발자 센터)|
|[Windows 런타임 참조](/uwp/api/)|Windows 런타임에 대한 참조 설명서입니다. (Windows 개발자 센터)|
|[Windows 런타임에 URI 전달](passing-a-uri-to-the-windows-runtime.md)|관리 코드에서 URI를 Windows 런타임으로 전달할 때 발생할 수 있는 문제 및 이러한 문제를 방지하는 방법을 설명합니다.|
