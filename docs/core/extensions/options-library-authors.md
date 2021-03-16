---
title: .NET 라이브러리 작성자를 위한 옵션 패턴 지침
author: IEvangelist
description: .NET 라이브러리 작성자로서 옵션 패턴을 노출하는 방법을 알아봅니다.
ms.author: dapine
ms.date: 01/28/2021
ms.openlocfilehash: d0da94a8f25c9e5aba6093fab07ccca6a0a7c345
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "102402140"
---
# <a name="options-pattern-guidance-for-net-library-authors"></a>.NET 라이브러리 작성자를 위한 옵션 패턴 지침

종속성 주입의 도움으로 서비스 및 해당 구성을 등록하면 ‘옵션 패턴’을 사용할 수 있습니다. 옵션 패턴을 사용하면 라이브러리(및 서비스)의 소비자가 [옵션 인터페이스](options.md#options-interfaces) 인스턴스를 요구할 수 있습니다. 여기서 `TOptions`는 옵션 클래스입니다. 강력한 형식의 개체를 통해 구성 옵션을 사용하면 일관된 값 표시가 보장되고 문자열 값을 수동으로 구문 분석하는 부담이 사라집니다. 라이브러리의 소비자가 사용할 수 있는 [구성 공급자](configuration-providers.md)가 많이 있습니다. 이러한 공급자를 통해 소비자는 여러 방법으로 라이브러리를 구성할 수 있습니다.

이 문서에서는 .NET 라이브러리 작성자가 라이브러리의 소비자에게 옵션 패턴을 올바르게 노출하는 방법에 대한 일반적인 지침을 알아봅니다. 여러 방법으로 동일한 목적을 달성할 수 있으며 몇 가지 고려할 사항이 있습니다.

## <a name="naming-conventions"></a>명명 규칙

규칙에 따라 서비스 등록을 담당하는 확장 메서드는 이름이 `Add{Service}`로 지정됩니다. 여기서 `{Service}`는 의미 있고 설명이 포함된 이름입니다. 패키지에 따라 서비스 등록에 `Use{Service}` 확장 메서드가 함께 사용될 수 있습니다. `Use{Service}` 확장 메서드는 [ASP.NET Core](/aspnet)에서 일반적입니다.

✔️ 서비스를 다른 제품과 명확하게 구분하는 이름을 고려하세요.

❌ 공식 Microsoft 패키지의 .NET 에코시스템에 이미 포함된 이름은 사용하지 마세요.

✔️ 확장 메서드를 노출하는 정적 클래스의 이름을 `{Type}Extensions`로 지정하는 것이 좋습니다. 여기서 `{Type}`는 확장하는 형식입니다.

### <a name="namespace-guidance"></a>네임스페이스 지침

Microsoft 패키지는 `Microsoft.Extensions.DependencyInjection` 네임스페이스를 활용하여 다양한 서비스 제품의 등록을 통합합니다.

✔️ 패키지 제품을 명확하게 식별하는 네임스페이스를 고려하세요.

❌ 비공식 Microsoft 패키지에 `Microsoft.Extensions.DependencyInjection` 네임스페이스를 사용하지 마세요.

## <a name="parameterless"></a>매개 변수가 없음

서비스를 최소한의 구성으로 또는 명시적 구성 없이 사용할 수 있는 경우에는 매개 변수가 없는 확장 메서드를 사용하는 것이 좋습니다.

:::code language="csharp" source="snippets/configuration/options-noparams/ServiceCollectionExtensions.cs" highlight="10-14":::

위의 코드에서 `AddMyLibraryService`는

- <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.
- `LibraryOptions`의 형식 매개 변수를 사용하여 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType>를 호출합니다.
- 기본 옵션 값을 지정하는 <xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A>에 대한 호출을 연결합니다.

## <a name="iconfiguration-parameter"></a>`IConfiguration` 매개 변수

소비자에게 많은 옵션을 노출하는 라이브러리를 작성하는 경우 `IConfiguration` 매개 변수 확장 메서드를 요구하는 것이 좋습니다. 필요한 `IConfiguration` 인스턴스는 <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A?displayProperty=nameWithType> 함수를 사용하여 구성의 명명된 섹션으로 범위가 지정되어야 합니다.

:::code language="csharp" source="snippets/configuration/options-configparam/ServiceCollectionExtensions.cs" highlight="10,12-16":::

위의 코드에서 `AddMyLibraryService`는

- <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.
- <xref:Microsoft.Extensions.Configuration.IConfiguration> 매개 변수 `namedConfigurationSection`을 정의합니다.
- <xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind(Microsoft.Extensions.Configuration.IConfiguration,System.Object)>를 호출하여 구성이 바인딩되는 옵션 인스턴스를 전달합니다.

이 패턴의 소비자는 명명된 섹션의 범위가 지정된 `IConfiguration` 인스턴스를 제공합니다.

:::code language="csharp" source="snippets/configuration/options-configparam/Program.cs" highlight="22-23":::

`.AddMyLibraryService`에 대한 호출은 <xref:Microsoft.Extensions.Hosting.IHostBuilder.ConfigureServices%2A> 메서드에서 생성됩니다. `Startup` 클래스를 사용할 때에도 마찬가지입니다. 등록하는 서비스의 추가가 `ConfigureServices`에서 발생합니다.

기본값 지정은 라이브러리 작성자가 해야 합니다.

> [!NOTE]
> 구성을 옵션 인스턴스에 바인딩할 수 있습니다. 그러나 이름 충돌 때문에 오류가 발생할 위험이 있습니다. 또한 이렇게 수동으로 바인딩하는 경우 옵션 패턴 소비를 한 번만 읽기로 제한합니다. 이러한 소비자는 [IOptionsMonitor](options.md#ioptionsmonitor) 인터페이스를 사용할 수 없기 때문에 설정 변경 사항이 다시 바인딩되지 않습니다.
>
> ```csharp
> services.AddOptions<LibraryOptions>()
>     .Configure<IConfiguration>(
>         (options, configuration) =>
>             configuration.GetSection("LibraryOptions").Bind(options));
> ```

## <a name="actiontoptions-parameter"></a>`Action<TOptions>` 매개 변수

라이브러리 소비자가 옵션 클래스의 인스턴스를 생성하는 람다 식을 제공하는 데 관심이 있을 수 있습니다. 이 시나리오에서는 확장 메서드에서 `Action<LibraryOptions>` 매개 변수를 정의합니다.

:::code language="csharp" source="snippets/configuration/options-action/ServiceCollectionExtensions.cs" highlight="10,12":::

위의 코드에서 `AddMyLibraryService`는

- <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.
- <xref:System.Action%601>를 정의합니다. 여기서 `T`는 `LibraryOptions` 매개 변수 `configureOptions`입니다.
- `configureOptions` 작업이 지정되면 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>를 호출합니다.

이 패턴의 소비자는 람다 식(또는 `Action<LibraryOptions>` 매개 변수를 충족하는 대리자)을 제공합니다.

:::code language="csharp" source="snippets/configuration/options-action/Program.cs" highlight="22-26":::

## <a name="options-instance-parameter"></a>옵션 인스턴스 매개 변수

라이브러리 소비자가 인라인 옵션 인스턴스를 제공하는 것을 선호할 수 있습니다. 이 시나리오에서는 옵션 개체 `LibraryOptions`의 인스턴스를 사용하는 확장 메서드를 노출합니다.

:::code language="csharp" source="snippets/configuration/options-object/ServiceCollectionExtensions.cs" highlight="9,11-17":::

위의 코드에서 `AddMyLibraryService`는

- <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.
- `LibraryOptions`의 형식 매개 변수를 사용하여 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType>를 호출합니다.
- 지정된 `userOptions` 인스턴스에서 재정의할 수 있는 기본 옵션 값을 지정하는 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>에 대한 호출을 연결합니다.

이 패턴의 소비자는 `LibraryOptions` 클래스의 인스턴스를 제공하여 원하는 속성 값을 인라인으로 정의합니다.

:::code language="csharp" source="snippets/configuration/options-object/Program.cs" highlight="22-26":::

## <a name="post-configuration"></a>구성 후

모든 구성 옵션 값을 바인딩하거나 지정한 후에는 사후 구성 기능을 사용할 수 있습니다. 앞서 설명한 것과 동일한 [`Action<TOptions>` 매개 변수](#actiontoptions-parameter)를 노출하여 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>를 호출하도록 선택할 수 있습니다. 사후 구성은 모든 `.Configure` 호출 후에 실행됩니다.

:::code language="csharp" source="snippets/configuration/options-postconfig/ServiceCollectionExtensions.cs" highlight="10,12":::

위의 코드에서 `AddMyLibraryService`는

- <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.
- <xref:System.Action%601>를 정의합니다. 여기서 `T`는 `LibraryOptions` 매개 변수 `configureOptions`입니다.
- `configureOptions` 작업이 지정되면 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>를 호출합니다.

이 패턴의 소비자는 사후 구성을 사용하지 않는 시나리오의 [`Action<TOptions>` 매개 변수]와 마찬가지로 람다 식(또는 `Action<LibraryOptions>` 매개 변수를 충족하는 대리자)을 제공합니다.

:::code language="csharp" source="snippets/configuration/options-postconfig/Program.cs" highlight="22-26":::

## <a name="see-also"></a>참고 항목

- [.NET의 옵션 패턴](options.md)
- [.NET에서 종속성 주입](dependency-injection.md)
- [종속성 주입 지침](dependency-injection-guidelines.md)
