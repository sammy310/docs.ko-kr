---
title: .NET에서 사용자 지정 로깅 공급자 구현
description: .NET 애플리케이션에서 사용자 지정 로깅 공급자를 구현하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 09/25/2020
ms.topic: how-to
ms.openlocfilehash: 3a0af6296c2ade15ff1b75dce5a5f99bfe235ebf
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "102402074"
---
# <a name="implement-a-custom-logging-provider-in-net"></a>.NET에서 사용자 지정 로깅 공급자 구현

일반적인 로깅 요구 사항에 사용할 수 있는 다양한 [로깅 공급자](logging-providers.md)가 있습니다. 사용 가능한 공급자 중 하나가 애플리케이션 요구 사항에 맞지 않는 경우 사용자 지정 <xref:Microsoft.Extensions.Logging.ILoggerProvider>를 구현해야 할 수 있습니다. 이 문서에서는 콘솔에서 로그에 색을 지정하는 데 사용할 수 있는 사용자 지정 로깅 공급자를 구현하는 방법을 알아봅니다.

### <a name="sample-custom-logger-configuration"></a>샘플 사용자 지정 로거 구성

샘플에서는 다음 구성 형식을 사용하여 로그 수준 및 이벤트 ID에 따라 다른 색의 콘솔 항목을 만듭니다.

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerConfiguration.cs":::

위의 코드는 기본 수준을 `Information`으로 설정하고 색을 `Green`으로 설정하며 `EventId`는 암시적으로 `0`입니다.

### <a name="create-the-custom-logger"></a>사용자 지정 로거 만들기

`ILogger` 구현 범주 이름은 일반적으로 로깅 원본입니다. 예를 들어 다음은 로거를 만드는 형식입니다.

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs":::

위의 코드는

- 범주 이름별로 로거 인스턴스를 만듭니다.
- `IsEnabled`에서 `logLevel == _config.LogLevel`을 확인하므로 각 `logLevel`에 고유한 로거가 있습니다. 모든 상위 로그 수준에 대해서도 로거를 사용하도록 설정해야 합니다.

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs" range="16-17":::

## <a name="custom-logger-provider"></a>사용자 지정 로거 공급자

`ILoggerProvider` 개체는 로거 인스턴스를 만들어야 합니다. 범주별로 로거 인스턴스를 만들 필요가 없을 수도 있지만, NLog 또는 log4net와 같은 일부 로거에 적합합니다. 이렇게 하면 필요한 경우 범주별로 다른 로깅 출력 대상을 선택할 수도 있습니다.

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerProvider.cs":::

위의 코드에서 <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A>는 범주 이름별로 `ColorConsoleLogger`의 단일 인스턴스를 만들고 [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2)에 저장합니다.

## <a name="usage-and-registration-of-the-custom-logger"></a>사용자 지정 로거의 사용 및 등록

사용자 지정 로깅 공급자와 해당 로거를 추가하려면 <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType>에서 <xref:Microsoft.Extensions.Logging.ILoggingBuilder>와 함께 <xref:Microsoft.Extensions.Logging.ILoggerProvider>를 추가합니다.

:::code language="csharp" source="snippets/configuration/console-custom-logging/Program.cs" range="23-39":::

`ILoggingBuilder`는 하나 이상의 `ILogger` 인스턴스를 만듭니다. `ILogger` 인스턴스는 프레임워크에서 정보를 로그하는 데 사용됩니다.

앞의 코드에서는 `ILoggerFactory`를 위한 확장 메서드를 하나 이상 제공합니다.

:::code language="csharp" source="snippets/configuration/console-custom-logging/Extensions/ColorConsoleLoggerExtensions.cs":::

이 간단한 애플리케이션을 실행하면 다음 콘솔 창과 비슷하게 렌더링됩니다.

:::image type="content" source="media/color-console-logger.png" alt-text="색 콘솔 로거 샘플 출력":::

## <a name="see-also"></a>참고 항목

- [.NET에 로그인](logging.md)
- [.NET의 로깅 공급자](logging-providers.md)
- [.NET의 고성능 로깅](high-performance-logging.md)
