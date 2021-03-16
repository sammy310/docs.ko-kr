---
title: 종속성 주입 지침
description: .NET 애플리케이션 개발을 위한 다양한 종속성 주입 지침 및 모범 사례를 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/29/2020
ms.topic: guide
ms.openlocfilehash: 105536df873829dc79dcca1b86d080360e71303f
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "102402146"
---
# <a name="dependency-injection-guidelines"></a>종속성 주입 지침

이 문서에서는 .NET 애플리케이션에서 종속성 주입을 구현하기 위한 일반적인 지침 및 모범 사례를 제공합니다.

## <a name="design-services-for-dependency-injection"></a>종속성 주입을 위한 서비스 디자인

종속성 주입을 위한 서비스를 디자인하는 경우

- 상태 저장 정적 클래스 및 멤버를 사용하지 마세요. 대신 싱글톤 서비스를 사용하도록 앱을 설계하여 전역 상태를 만들지 않도록 합니다.
- 서비스 내의 종속 클래스를 직접 인스턴스화하지 마세요. 직접 인스턴스화는 코드를 특정 구현에 결합합니다.
- 서비스를 작고 잘 구성되고 쉽게 테스트할 수 있도록 만듭니다.

클래스에 주입된 종속성이 많은 경우 클래스가 역할이 너무 많고 [SRP(단일 책임 원칙)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility)을 위반하는 것일 수 있습니다. 해당 책임 몇 가지를 새로운 클래스로 이동하여 클래스를 리팩터링해 보세요.

### <a name="disposal-of-services"></a>서비스 삭제

컨테이너는 자신이 만든 형식을 정리하며 <xref:System.IDisposable> 인스턴스에서 <xref:System.IDisposable.Dispose%2A>를 호출합니다. 개발자는 컨테이너에서 확인된 서비스는 삭제해서는 안 됩니다. 형식 또는 팩터리가 싱글톤으로 등록된 경우 컨테이너에서 싱글톤을 자동으로 삭제합니다.

다음 예제에서는 서비스가 서비스 컨테이너에 의해 만들어지고 자동으로 삭제됩니다.

:::code language="csharp" source="snippets/configuration/console-di-disposable/TransientDisposable.cs":::

위의 삭제 가능한 형식은 임시 수명을 갖도록 만들어진 것입니다.

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

위의 삭제 가능한 형식은 범위가 지정된 수명을 갖도록 만들어진 것입니다.

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

위의 삭제 가능한 형식은 싱글톤 수명을 갖도록 만들어진 것입니다.

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60" highlight="":::

디버그 콘솔은 실행 후 다음 샘플 출력을 보여 줍니다.

```console
Scope 1...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

Scope 2...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

info: Microsoft.Hosting.Lifetime[0]
      Application started.Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
     Hosting environment: Production
info: Microsoft.Hosting.Lifetime[0]
     Content root path: .\configuration\console-di-disposable\bin\Debug\net5.0
info: Microsoft.Hosting.Lifetime[0]
     Application is shutting down...
SingletonDisposable.Dispose()
```

### <a name="services-not-created-by-the-service-container"></a>서비스 컨테이너에서 만들지 않은 서비스

다음 코드를 살펴보세요.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton(new ExampleService());

    // ...
}
```

위의 코드에서

- `ExampleService` 인스턴스가 서비스 컨테이너에서 만들어지지 **않았습니다**.
- 프레임워크가 서비스를 자동으로 삭제하지 **않습니다**.
- 개발자가 서비스 삭제를 담당합니다.

### <a name="idisposable-guidance-for-transient-and-shared-instances"></a>임시 및 공유 인스턴스에 대한 IDisposable 지침

#### <a name="transient-limited-lifetime"></a>임시적인 제한 수명

**시나리오**

앱에는 다음 시나리오 중 하나에 대해 임시 수명으로 <xref:System.IDisposable> 인스턴스가 필요합니다.

- 인스턴스가 루트 범위(루트 컨테이너)에서 확인됩니다.
- 범위가 끝나기 전에 인스턴스를 삭제해야 합니다.

**해결 방법**

부모 범위 밖에서 인스턴스를 생성하려면 팩터리 패턴을 사용합니다. 이 경우 앱에는 일반적으로 최종 형식의 생성자를 직접 호출하는 `Create` 메서드가 있습니다. 최종 형식에 다른 종속성이 있는 경우 팩터리는 다음을 수행할 수 있습니다.

- 해당 생성자에서 <xref:System.IServiceProvider>을 수신합니다.
- 해당 종속성에서 컨테이너를 사용하는 동안 컨테이너 외부의 인스턴스를 인스턴스화하기 위해 <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType>을 사용합니다.

#### <a name="shared-instance-limited-lifetime"></a>공유 인스턴스 및 제한 수명

**시나리오**

앱은 여러 서비스에서 공유 <xref:System.IDisposable> 인스턴스가 필요하지만 <xref:System.IDisposable> 인스턴스는 수명이 제한되어 있어야 합니다.

**해결 방법**

인스턴스를 범위가 지정된 수명으로 등록합니다. <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType>을 사용하여 새 <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>를 만듭니다. 범위의 <xref:System.IServiceProvider>를 사용하여 필요한 서비스를 가져옵니다. 더 이상 필요하지 않은 범위를 삭제합니다.

#### <a name="general-idisposable-guidelines"></a>일반 `IDisposable` 지침

- 임시 수명에 <xref:System.IDisposable> 인스턴스를 등록하지 마세요. 대신 팩터리 패턴을 사용합니다.
- 루트 범위에서 임시 또는 범위가 지정된 수명으로 <xref:System.IDisposable> 인스턴스를 확인하지 마세요. 앱이 <xref:System.IServiceProvider>를 생성/재생성 및 삭제하는 경우만 예외이지만, 이상적인 패턴이 아닙니다.
- DI를 통한 <xref:System.IDisposable> 종속성 수신은 수신자가 자체적으로 <xref:System.IDisposable>를 구현할 필요가 없습니다. <xref:System.IDisposable> 종속성의 수신자는 해당 종속성에서 <xref:System.IDisposable.Dispose%2A>를 호출하지 않아야 합니다.
- 범위를 사용하여 서비스 수명을 제어합니다. 범위는 계층적이지 않으며 범위 간 특수 연결이 없습니다.

리소스 정리에 대한 자세한 내용은 [`Dispose` 메서드 구현](../../standard/garbage-collection/implementing-dispose.md)또는 [`DisposeAsync` 메서드 구현](../../standard/garbage-collection/implementing-disposeasync.md)을 참조하세요. 또한 리소스 정리와 관련하여 [컨테이너가 삭제 가능한 임시 서비스를 캡처](#disposable-transient-services-captured-by-container) 시나리오를 살펴보세요.

## <a name="default-service-container-replacement"></a>기본 서비스 컨테이너 바꾸기

기본 제공 서비스 컨테이너는 프레임워크 및 대부분의 소비자 앱의 요구를 충족하기 위한 것입니다. 다음과 같이 지원하지 않는 특정 기능이 필요하지 않는 한 기본 제공 컨테이너를 사용하는 것이 좋습니다.

- 속성 삽입
- 이름에 기반한 삽입
- 자식 컨테이너
- 사용자 지정 수명 관리
- 초기화 지연에 대한 `Func<T>` 지원
- 규칙 기반 등록

ASP.NET Core 앱에서 사용할 수 있는 타사 컨테이너는 다음과 같습니다.

- [Autofac](https://autofac.readthedocs.io/en/latest/integration/aspnetcore.html)
- [DryIoc](https://www.nuget.org/packages/DryIoc.Microsoft.DependencyInjection)
- [유예](https://www.nuget.org/packages/Grace.DependencyInjection.Extensions)
- [LightInject](https://github.com/seesharper/LightInject.Microsoft.DependencyInjection)
- [Lamar](https://jasperfx.github.io/lamar/)
- [Stashbox](https://github.com/z4kn4fein/stashbox-extensions-dependencyinjection)
- [Unity](https://www.nuget.org/packages/Unity.Microsoft.DependencyInjection)

## <a name="thread-safety"></a>스레드로부터의 안전성

스레드로부터 안전한 싱글톤 서비스를 만듭니다. 싱글톤 서비스가 Transient 서비스에 대한 종속성을 갖는 경우 Transient 서비스는 싱글톤에서 사용되는 방식에 따라 스레드 보안이 필요할 수 있습니다.

[AddSingleton\<TService>(IServiceCollection, Func\<IServiceProvider,TService>)](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A)의 두 번째 인수와 같은 싱글톤 서비스의 팩터리 메서드는 스레드로부터 안전하지 않아도 됩니다. 형식(`static`) 생성자와 같이 이 메서드는 단일 스레드에서 한 번만 호출됩니다.

## <a name="recommendations"></a>권장 사항

- `async/await` 및 `Task` 기반 서비스 확인은 지원되지 않습니다. C#은 비동기 생성자를 지원하지 않으므로, 서비스를 동기식으로 확인한 후 비동기 메서드를 사용합니다.
- 데이터 및 구성을 서비스 컨테이너에 직접 저장하지 마세요. 예를 들어 사용자의 쇼핑 카트는 일반적으로 서비스 컨테이너에 추가하지 말아야 합니다. 구성은 옵션 패턴을 사용해야 합니다. 마찬가지로 다른 개체에 대한 액세스를 허용하기 위해서만 존재하는 “데이터 보유자” 개체를 사용하지 마세요. DI를 통해 실제 항목을 요청하는 것이 좋습니다.
- 서비스에 정적 액세스를 사용하지 마십시오. 예를 들어 다른 곳에 사용하기 위해 [IApplicationBuilder.ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices)를 정적 필드 또는 속성으로 캡처하지 마세요.
- [DI 팩터리](#async-di-factories-can-cause-deadlocks)를 빠르고 동기식으로 유지하세요.
- [‘서비스 로케이터 패턴’](#scoped-service-as-singleton)을 사용하지 마세요. 예를 들어 DI를 대신 사용할 수 있는 경우 서비스 인스턴스를 가져오기 위해 <xref:System.IServiceProvider.GetService%2A>를 호출하지 마세요.
- 피해야 하는 또 다른 서비스 로케이터 변형은 런타임에 종속성을 해결하는 팩터리를 주입하는 것입니다. 이러한 두 가지 방법 모두 [제어 반전](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) 전략을 혼합합니다.
- `ConfigureServices`에서 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>를 호출하지 마세요. 일반적으로 `BuildServiceProvider`는 개발자가 `ConfigureServices`에서 서비스를 해결하려는 경우 호출합니다.
- 컨테이너가 삭제를 위해 [삭제 가능한 임시 서비스를 캡처](#disposable-transient-services-captured-by-container)합니다. 따라서 최상위 컨테이너에서 해결할 경우 메모리 누수가 발생할 수 있습니다.
- 범위 유효성 검사를 사용하여 범위가 지정된 서비스를 캡처하는 싱글톤이 앱에 없는지 확인합니다. 자세한 내용은 [범위 유효성 검사](dependency-injection.md#scope-validation)를 참조하세요.

모든 권장 사항과 마찬가지로, 권장 사항을 무시해야 하는 상황이 발생할 수 있습니다. 예외는 드물게 발생하며 대부분 프레임워크 자체 내에서 특별한 경우에만 발생합니다.

DI는 정적/전역 개체 액세스 패턴의 ‘대안’입니다. 고정 개체 액세스와 함께 사용할 경우 DI의 장점을 실현할 수 없습니다.

## <a name="example-anti-patterns"></a>안티 패턴 예제

이 문서의 지침 외에 ‘**지양** 해야 할’ 몇 가지 안티 패턴이 있습니다. 이러한 안티 패턴 중 일부는 런타임 자체를 개발하면서 배웁니다.

> [!WARNING]
> 다음은 안티 패턴 예제입니다. 코드를 복사하지 ‘말고’ 이러한 패턴을 사용하지 ‘않으며’ 어떤 경우에도 이러한 패턴을 피해야 합니다.

### <a name="disposable-transient-services-captured-by-container"></a>컨테이너가 삭제 가능한 임시 서비스를 캡처

<xref:System.IDisposable>을 구현하는 ‘임시’ 서비스를 등록하는 경우 기본적으로 DI 컨테이너는 이러한 참조를 유지하고 컨테이너에서 확인된 경우 애플리케이션이 중지하여 컨테이너가 삭제될 때까지 또는 범위에서 확인된 경우 범위가 삭제될 때까지는 <xref:System.IDisposable.Dispose>하지 않습니다. 따라서 컨테이너 수준에서 확인할 경우 메모리 누수가 발생할 수 있습니다.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="18-30":::

위의 안티 패턴에서는 1,000개의 `ExampleDisposable` 개체가 인스턴스화되고 루팅됩니다. 이들은 `serviceProvider` 인스턴스가 삭제될 때까지 삭제되지 않습니다.

메모리 누수를 디버깅하는 방법에 대한 자세한 내용은 [.NET에서 메모리 누수 디버깅](../diagnostics/debug-memory-leak.md)을 참조하세요.

### <a name="async-di-factories-can-cause-deadlocks"></a>비동기 DI 팩터리에서 교착 상태가 발생할 수 있음

‘DI 팩터리’라는 용어는 `Add{LIFETIME}`을 호출할 때 존재하는 오버로드 메서드를 의미합니다. `Func<IServiceProvider, T>`를 허용하는 오버로드가 있습니다. 여기서 `T`는 등록할 서비스이고, 매개 변수 이름은 `implementationFactory`입니다. `implementationFactory`는 람다 식, 로컬 함수 또는 메서드로 제공될 수 있습니다. 팩터리가 비동기식이고 <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>를 사용하는 경우 교착 상태가 발생합니다.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="32-45" highlight="4-8":::

위의 코드에서는 `implementationFactory`에 본문이 `Task<Bar>` 반환 메서드에서 <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>를 호출하는 람다 식이 지정됩니다. 이로 인해 ‘교착 상태가 발생’합니다. `GetBarAsync` 메서드는 단순히 <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>를 사용하여 비동기 작업을 에뮬레이트한 다음 <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)>를 호출합니다.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="47-53":::

비동기 지침에 대한 자세한 내용은 [비동기 프로그래밍: 중요 정보 및 조언](../../csharp/async.md#important-info-and-advice)을 참조하세요. 교착 상태 디버깅에 대한 자세한 내용은 [.NET에서 교착 상태 디버깅](../diagnostics/debug-deadlock.md)을 참조하세요.

이 안티 패턴을 실행 중이고 교착 상태가 발생하는 경우 Visual Studio의 병렬 스택 창에서 두 개의 스레드가 대기하는 것을 볼 수 있습니다. 자세한 내용은 [병렬 스택 창에서 스레드 및 작업 보기](/visualstudio/debugger/using-the-parallel-stacks-window)를 참조하세요.

### <a name="captive-dependency"></a>조임 종속성

[‘조임 종속성’](https://blog.ploeh.dk/2014/06/02/captive-dependency)은 [Mark Seeman](https://blog.ploeh.dk/about)이 만든 용어로, 수명이 긴 서비스에서 수명이 짧은 서비스를 보유하는 잘못된 서비스 수명 구성을 의미합니다.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="55-65":::

위의 코드에서 `Foo`는 싱글톤으로 등록되고 `Bar`는 범위가 지정되는데, 표면적으로는 유효한 것으로 보입니다. 그러나 `Foo`의 구현을 생각해보세요.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Foo.cs" highlight="5":::

`Foo` 개체에는 `Bar` 개체가 필요하며, `Foo`는 싱글톤이고 `Bar`는 범위가 지정되므로 이는 잘못된 구성입니다. `Foo`가 한 번만 인스턴스화되고 해당 수명 동안 `Bar`를 유지해야 하는데 이 수명이 `Bar`의 의도된 범위가 지정된 수명보다 길기 때문입니다. `validateScopes: true`를 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)>에 전달하여 범위 유효성 검사를 고려해야 합니다. 범위의 유효성을 검사할 때 "싱글톤 'Foo'에서 범위가 지정된 서비스 'Bar'를 사용할 수 없음"과 비슷한 메시지가 포함된 <xref:System.InvalidOperationException>이 발생합니다.

자세한 내용은 [범위 유효성 검사](dependency-injection.md#scope-validation)를 참조하세요.

### <a name="scoped-service-as-singleton"></a>범위가 지정된 서비스를 싱글톤으로

범위가 지정된 서비스를 사용할 때 범위를 만들지 않거나 기존 범위 안에 들어가는 경우 해당 서비스는 싱글톤이 됩니다.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="68-82" highlight="13-14":::

위의 코드에서는 `Bar`가 <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> 내에서 검색되며 이는 올바른 패턴입니다. 안티 패턴은 범위 밖에서 `Bar`를 검색하는 것입니다. 예제 검색이 잘못된 패턴임을 표시하기 위해 변수의 이름이 `avoid`로 지정되어 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET에서 종속성 주입](dependency-injection.md)
- [자습서: .NET에서 종속성 주입 사용](dependency-injection-usage.md)
