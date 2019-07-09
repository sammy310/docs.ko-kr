---
title: Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c49e9a5c4b8785704f8c4cbd1c9b7af10dc0c689
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661778"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원

.NET Framework 4.5는 Windows 런타임을 사용 하 여 소프트웨어 개발 시나리오를 지원합니다. 이러한 시나리오는 다음 세 가지 범주로 구분됩니다.

- 개발 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 에 설명 된 대로 XAML 컨트롤을 사용 하 여 앱 [Windows 스토어 앱 용 로드맵 C# 또는 Visual Basic을 사용 하 여](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [하는 방법 (XAML) tos](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), 및 [.NET Windows 스토어 용 앱 개요 ](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- .NET Framework로 만든 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에서 사용할 클래스 라이브러리 개발.

- Windows 런타임 구성 요소를 패키지를 개발 합니다. Windows 런타임을 지 원하는 모든 프로그래밍 언어에서 사용할 수 있는 WinMD 파일입니다. 예를 들어, 참조 [Creating Windows Runtime Components in C# 및 Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)합니다.

이 항목에서는.NET Framework 모든 세 범주를 제공 하 고 Windows 런타임 구성 요소에 대 한 시나리오를 설명 지원을 간략하게 설명 합니다. 첫 번째 섹션은.NET Framework와 Windows 런타임 간의 관계에 대 한 기본 정보를 포함 하 고 도움말 시스템 및 IDE에서 발생할 수 있는 몇 가지 oddities를 설명 합니다. 합니다 [섹션을 두 번째](#WindowsRuntimeComponents) Windows 런타임 구성 요소를 개발 하기 위한 시나리오에 설명 합니다.

## <a name="the-basics"></a>기본 사항

.NET Framework 지원 함으로써 앞서 나열한 세 가지 개발 시나리오 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Windows 런타임 자체를 지원 합니다.

- [.NET framework 및 Windows Runtime 네임 스페이스](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) .NET Framework 클래스 라이브러리의 간결한 뷰를 제공 하 고는 형식 및 멤버를 만드는 데 사용할 수 있는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱 및 Windows 런타임 구성 요소입니다.

  - Visual Studio (Visual Studio 2012 이상 버전) 개발에 사용 하는 경우는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 참조 어셈블리 집합으로 관련 형식 및 멤버만 표시 되도록 앱 또는 Windows 런타임 구성 요소입니다.

  - 이 간소화 된 API 집합은 단순화 하는 추가 기능을.NET Framework 내에서 중복 되는 또는 Windows 런타임을 복제 하는 기능 제거 합니다. 예를 들어, 컬렉션 형식의 제네릭 버전만 포함 하 고 Windows 런타임 XML API를 위해 제거 하는 XML 문서 개체 모델을 설정 합니다.

  - Windows 런타임에서 관리 코드에서 쉽게 호출할 수 있으므로 운영 체제 API를 래핑하는 기능 또한 제거 됩니다.

  에 대 한 자세한 합니다 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]를 참조 합니다 [.NET Windows 스토어 용 앱 개요](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). API 선택 프로세스에 대 한 자세한 내용은 참조는 [Metro 스타일 앱 용.NET](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) .NET 블로그의 항목입니다.

- [Windows 런타임](/uwp/api/) 건물에 대 한 사용자 인터페이스 요소를 제공 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램, 운영 체제 기능에 대 한 액세스를 제공 합니다. .NET Framework와 같은 Windows 런타임이 사용 하도록 설정 하는 메타 데이터는 C# 및.NET Framework를 사용 하는 방법은 Windows 런타임을 사용 하도록 Visual Basic 컴파일러 클래스 라이브러리입니다. .NET Framework에서는 몇 가지 차이점을 숨겨 Windows 런타임을 사용 하기 쉽게 합니다.

  - .NET Framework 및 Windows 런타임 이벤트 처리기 추가 및 제거에 대 한 패턴과 같은 사이의 프로그래밍 패턴의 일부 차이점이 숨겨져 있습니다. .NET Framework 패턴을 그대로 사용하면 됩니다.

  - 자주 사용되는 형식(예: 기본 형식 및 컬렉션)의 일부 차이점이 숨겨져 있습니다. 에 설명 된 대로 단순히.NET Framework 형식에 사용할 [차이점 표시 되는 IDE에서](#DifferencesVisibleInIDE)이 문서의 뒷부분에 나오는.

대부분의 경우 Windows 런타임용.NET Framework 지원은 투명 합니다. 다음 섹션에서는 관리 코드와 Windows 런타임 간 명백한 차이점 중 일부를 설명합니다.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework 및 Windows 런타임 참조 설명서

Windows 런타임 및.NET Framework 설명서 집합 구분 됩니다. 형식이나 멤버에 도움말을 표시하기 위해 F1 키를 누르면, 적절한 집합의 참조 설명서가 표시됩니다. 그러나 탐색할 경우 합니다 [Windows 런타임 참조](/uwp/api/) 같이 난해해 보이는 예제를 발생할 수 있습니다.

- 와 같은 항목을 <xref:Windows.Foundation.Collections.IIterable%601> 인터페이스는 Visual Basic 또는 C# 용 선언 구문이 없는 합니다. 구문 섹션 위에 메모가 표시 하는 대신 (이 경우 ".NET: 이 인터페이스 System.Collections.Generic.IEnumerable 요소로\<T > "). 이.NET Framework와 Windows 런타임 다른 인터페이스를 사용 하 여 비슷한 기능을 제공 합니다. 게다가 동작의 차이점도 있습니다. 예를 들면 `IIterable`은 `First` 메서드 대신에 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드를 사용하여 열거자를 반환합니다. 일반적인 작업을 수행 하는 다른 방법을 배워야 할 필요 없이,.NET Framework는 관리 코드가 익숙한 형식을 사용 하도록 표시 하 여 Windows 런타임 지원 합니다. 표시 되지 않습니다는 `IIterable` IDE에서 인터페이스 이므로 Windows 런타임 참조 설명서에서 발생 하는 유일한 방법은 해당 설명서를 통해 직접 이동 하 여 합니다.

- <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> 설명서는 밀접 하 게 관련 된 문제를 보여 줍니다. 해당 매개 변수 형식이 언어 마다 다른 것으로 나타납니다. C# 및 Visual Basic의 경우 매개 변수 형식은 <xref:System.String?displayProperty=nameWithType> 및 <xref:System.Uri?displayProperty=nameWithType>입니다. 즉, .NET Framework에 자체 `String` 및 `Uri` 형식이 있고, 이같이 자주 사용되는 형식에 대해 다른 작업 방식을 배우도록 .NET Framework 사용자를 강요하는 것이 적합하지 않기 때문입니다. IDE에서.NET Framework 숨기는 해당 Windows 런타임 형식입니다.

- 몇 가지 경우에 같은 <xref:Windows.UI.Xaml.GridLength> 구조를.NET Framework 이름은 같지만 더 많은 기능을 사용 하 여 형식을 제공 합니다. 예를 들어, 생성자 및 속성 항목 집합은 `GridLength`와 연관되어 있지만, 멤버를 관리 코드에서만 사용할 수 있기 때문에 Visual Basic 및 C#용 구문 블록만 있습니다. Windows 런타임에서 구조체는 필드만 포함 되어 있습니다. Windows 런타임 구조체에 도우미 클래스인 필요 <xref:Windows.UI.Xaml.GridLengthHelper>, 해당 기능을 제공 합니다. 관리 코드를 작성할 때 IDE에서 도우미 클래스를 볼 수 없습니다.

- IDE에서 Windows 런타임 형식에서 파생 시키는 표시 <xref:System.Object?displayProperty=nameWithType>합니다. <xref:System.Object>과 같은 <xref:System.Object.ToString%2A?displayProperty=nameWithType>에서 상속된 멤버를 가진 것으로 나타납니다. 이러한 멤버에서 형식을 실제로 상속 하는 경우와 같이 작동할 <xref:System.Object>, Windows 런타임 형식으로 캐스팅 될 수 있습니다 <xref:System.Object>합니다. 이 기능에는 Windows 런타임용.NET Framework에서 제공 하는 지원의 일부입니다. 그러나 Windows 런타임 참조 설명서에서 형식의 보면 이러한 멤버가 나타납니다. 이 상속된 명백한 멤버에 대한 문서는 <xref:System.Object?displayProperty=nameWithType> 참조 문서에서 제공합니다.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>IDE에서 표시되는 차이점

더 많은 고급 프로그래밍 시나리오에서 작성 된 Windows 런타임 구성 요소를 사용 하는 등 C# 에 대 한 응용 프로그램 논리를 제공 하는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] JavaScript를 사용 하 여 Windows 용으로 빌드된 앱에서 이러한 차이점은 에서처럼도 IDE에서 명확 합니다 설명서입니다. 구성 요소가 반환 하는 경우는 `IDictionary<int, string>` JavaScript를 JavaScript 디버거에서 살펴보면의 메서드를 보면 `IMap<int, string>` JavaScript Windows 런타임 형식을 사용 합니다. 두 언어에서 다르게 나타나는 일반적으로 사용되는 컬렉션 형식의 일부는 다음 표에 표시됩니다.

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

Windows 런타임에서 `IMap<K, V>` 하 고 `IMapView<K, V>` 사용 하 여 반복 됩니다 `IKeyValuePair`합니다. 관리 코드에 전달되면 이들은 `IDictionary<TKey, TValue>` 및 `IReadOnlyDictionary<TKey, TValue>`로 표시되므로 당연히 `System.Collections.Generic.KeyValuePair<TKey, TValue>`를 사용하여 열거해야 합니다.

인터페이스가 관리 코드에 표시되는 방식은 이러한 인터페이스를 구현하는 형식이 표시되는 방식에 영향을 미칩니다. 예를 들어 `PropertySet` 클래스는 관리되는 코드에 `IDictionary<TKey, TValue>`로 나타나는 `IMap<K, V>`를 구현합니다. `PropertySet`에서 `IMap<K, V>` 대신 `IDictionary<TKey, TValue>`가 구현된 것으로 나타나므로 관리되는 코드에서는 .NET Framework 사전의 `Add` 메서드처럼 동작하는 `Add` 메서드가 있는 것으로 나타납니다. 이 클래스는 `Insert` 메서드를 가지고 있는 것으로 보이지 않습니다.

.NET Framework를 사용 하 여 Windows 런타임 구성 요소를 만들고 JavaScript를 사용 하 여 이러한 구성 요소를 사용 하는 방법을 보여 주는 연습에 대 한 자세한 내용은 참조 하세요. [Creating Windows Runtime Components in C# 및 Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>기본 형식

관리 코드에서 Windows 런타임 자연스럽 게 사용할 수 있도록, 코드에서 Windows 런타임 기본 형식 대신.NET Framework 기본 형식 표시 됩니다. .NET Framework에서 `Int32` 구조체와 같은 기본 형식에는 `Int32.TryParse` 메서드 등 유용한 속성 및 메서드가 많이 포함되어 있습니다. 반면, 기본 형식 및 Windows 런타임 구조에는 필드만 있습니다. 관리 코드에서 기본 형식을 사용할 때 .NET Framework 형식으로 표시되고, 평소와 같이 .NET Framework 형식의 속성 및 메서드를 사용할 수 있습니다. 다음 목록은 요약을 제공합니다.

- Windows 런타임 기본 형식에 대해 `Int32`, `Int64`, `Single`, `Double`를 `Boolean`를 `String` (유니코드 문자를 변경할 수 없는 컬렉션), `Enum`를 `UInt32`, `UInt64`, 및 `Guid`에 있는 동일한 이름의 형식을 사용 합니다 `System` 네임 스페이스입니다.

- `UInt8`에 대해 `System.Byte`를 사용합니다.

- `Char16`에 대해 `System.Char`를 사용합니다.

- `IInspectable` 인터페이스에 대해 `System.Object`를 사용합니다.

- `HRESULT`에 대해 하나의 `System.Int32` 멤버가 있는 구조체를 사용합니다.

와 마찬가지로 인터페이스 형식에이 표현의 증거 때 표시 될 수 있습니다.NET Framework 프로젝트에서 사용 되는 Windows 런타임 구성 요소는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] JavaScript를 사용 하 여 빌드된 앱입니다.

해당.NET Framework 포함 관리 코드에 표시 되는 다른 기본, 자주 사용 되는 Windows 런타임 형식 합니다 `Windows.Foundation.DateTime` 구조는 관리 코드에 나타나는 <xref:System.DateTimeOffset?displayProperty=nameWithType> 구조 및 `Windows.Foundation.TimeSpan` 구조체는 으로 표시 되는 <xref:System.TimeSpan?displayProperty=nameWithType> 구조입니다.

### <a name="other-differences"></a>기타 차이점

몇 가지 경우에 Windows 런타임 형식 대신 코드에서.NET Framework 형식을 표시 하는 사용자의 조치가 필요 합니다. 예를 들어 합니다 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 으로 표시 되는 클래스 <xref:System.Uri?displayProperty=nameWithType> .NET Framework 코드에서. <xref:System.Uri?displayProperty=nameWithType> 상대 URI를 사용할 수 있지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 는 절대 URI가 필요 합니다. 따라서 Windows 런타임 메서드에 URI를 전달 하는 경우가 절대적인 지 확인 해야 합니다. (참조 [Windows 런타임에 URI 전달](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Windows 런타임 구성 요소를 개발하기 위한 시나리오

관리 되는 Windows 런타임 구성 요소에 대 한 지원 되는 시나리오는 다음 일반 원칙에 따라 달라 집니다.

- .NET Framework를 사용 하 여 작성 된 Windows 런타임 구성 요소는 다른 Windows Runtimelibraries와에서 명백한 차이점이 없습니다. 예를 들어 관리 되는 코드를 사용 하 여 네이티브 Windows 런타임 구성 요소를 다시 구현 하는 경우 두 구성 않습니다 외부적으로 구별할 수 있습니다. 코드 그 자체가 관리 코드이더라도 구성 요소가 관리 코드로 작성되었다는 사실은 그것을 사용하는 코드에 표시되지 않습니다. 그러나 내부적으로 구성 요소는 실제 관리 코드이며 CLR(공용 언어 런타임)에서 실행됩니다.

- 구성 요소는 응용 프로그램 논리, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] UI 컨트롤 또는 둘 모두를 구현하는 형식을 포함할 수 있습니다.

  > [!NOTE]
  > UI 요소를 응용 프로그램 논리에서 분리하는 것이 좋습니다. 또한 JavaScript 및 HTML을 사용하여 Windows용으로 빌드된 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] UI 컨트롤을 사용할 수 없습니다.

- 구성 요소는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 위한 Visual Studio 솔루션 내의 프로젝트이거나 여러 솔루션에 추가할 수 있는 재사용 가능한 구성 요소일 수 있습니다.

  > [!NOTE]
  > 구성 요소와만 함께 사용할 경우 C# 또는 Visual Basic의 경우는 Windows 런타임 구성 요소를 만들 필요가 없습니다. 만들 경우 일반.NET Framework 클래스 라이브러리를 대신, Windows 런타임 형식으로 공용 API 화면을 제한할 필요가 없습니다.

- Windows 런타임을 사용 하 여 다양 한 재사용 가능한 구성 요소를 해제할 수 있습니다 <xref:Windows.Foundation.Metadata.VersionAttribute> 형식 (및 형식 내 멤버)를 식별 하기 위한 특성 서로 다른 버전에 추가 되었습니다.

- 구성 요소의 유형을 Windows 런타임 형식에서 파생 될 수 있습니다. 컨트롤의 기본 컨트롤 형식에서 파생 될 수 있습니다 합니다 <xref:Windows.UI.Xaml.Controls.Primitives> 네임 스페이스 또는 좀 더 완료 된 컨트롤 같은 <xref:Windows.UI.Xaml.Controls.Button>합니다.

  > [!IMPORTANT]
  > 부터 [!INCLUDE[win8](../../../includes/win8-md.md)] 및.NET Framework 4.5에서 관리 되는 Windows 런타임 구성 요소에서 모든 공용 형식은 봉인 되어야 합니다. 다른 Windows 런타임 구성 요소에서 형식에서 파생 될 수 없습니다. 구성 요소에서 다형 동작을 제공하려면 인터페이스를 만들어 다형 형식에서 구현할 수 있습니다.

- 구성 요소에서 공용 형식에서 모든 매개 변수 및 반환 형식에는 Windows 런타임 형식 (구성 요소를 정의 하는 Windows 런타임 형식 포함) 여야 합니다.

다음 섹션에서는 일반적인 시나리오의 예제를 제공합니다.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>JavaScript을 사용한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에 대한 응용 프로그램 논리

JavaScript를 사용하여 Windows용으로 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 개발할 때 관리 코드에서 응용 프로그램 논리의 일부가 더 잘 수행되거나 개발하기 더 쉬울 수도 있습니다. JavaScript는 .NET Framework 클래스 라이브러리를 직접 사용할 수 없지만, 이 클래스 라이브러리를 .WinMD 파일로 만들 수 있습니다. 이 시나리오에서는 Windows 런타임 구성 요소 이므로 앱의 핵심 버전 특성을 제공에 적합 하지 않습니다.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>다시 사용 가능한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] UI 컨트롤

재사용 가능한 Windows 런타임 구성 요소에서 관련된 UI 컨트롤 집합을 패키징할 수 있습니다. 구성 요소는 직접 시장에 출시하거나 사용자가 만든 앱의 요소로서 사용할 수 있습니다. 이 시나리오에서는 Windows 런타임을 사용 하는 것이 있도록 <xref:Windows.Foundation.Metadata.VersionAttribute> 호환성을 개선 하는 특성입니다.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>기존 .NET Framework 앱의 재사용 가능한 응용 프로그램 논리

독립 실행형 Windows 런타임 구성 요소로 기존 데스크톱 앱에서 관리 되는 코드를 패키지할 수 있습니다. 따라서 C++ 또는 JavaScript를 사용하여 빌드한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱 및 C# 또는 Visual Basic을 사용하여 빌드한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱 모두에서 구성 요소를 사용할 수 있습니다. 코드를 재사용하는 시나리오가 여러 개일 경우 버전 관리는 옵션입니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[Windows 스토어 앱용 .NET 개요](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|.NET Framework 형식 및 멤버를 만드는 데 사용할 수 있는 설명 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱 및 Windows RuntimeComponents 합니다. (Windows 개발자 센터)|
|[C# 또는 Visual Basic을 사용 하 여 Windows 스토어 앱 용 로드맵](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|C# 또는 Visual Basic을 사용하여 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 개발하기 시작할 때 도움을 주기 위해 다양한 퀵 스타트 항목, 지침 및 모범 사례를 포함한 주요 리소스를 제공합니다. (Windows 개발자 센터)|
|[방법 tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|C# 또는 Visual Basic을 사용하여 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 개발하기 시작할 때 도움을 주기 위해 다양한 퀵 스타트 항목, 지침 및 모범 사례를 포함한 주요 리소스를 제공합니다. (Windows 개발자 센터)|
|[C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|.NET Framework를 사용 하 여 Windows 런타임 구성 요소를 만드는 방법에 설명의 일부로 사용 하는 방법에 설명는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱에서 JavaScript를 사용 하 여 Windows 용으로 빌드된 및 Visual Studio로 조합을 디버깅 하는 방법에 설명 합니다. (Windows 개발자 센터)|
|[Windows 런타임 참조](/uwp/api/)|Windows 런타임에 대 한 참조 설명서입니다. (Windows 개발자 센터)|
|[Windows 런타임에 URI 전달](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Windows 런타임 및 방지 방법은 관리 되는 코드에서 URI를 전달 하는 경우 발생할 수 있는 문제를 설명 합니다.|
