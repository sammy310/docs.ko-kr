---
title: .NET에서 종속성 주입
description: .NET에서 종속성 주입을 구현하는 방법 및 사용 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/28/2020
ms.topic: overview
ms.openlocfilehash: cc030e32846690b6544b99030800b50055a3113e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "102402104"
---
# <a name="dependency-injection-in-net"></a>.NET에서 종속성 주입

.NET는 클래스와 해당 종속성 간의 [IoC(Inversion of Control)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion)를 실현하는 기술인 DI(종속성 주입) 소프트웨어 디자인 패턴을 지원합니다. .NET에서 종속성 주입은 구성, 로깅, 옵션 패턴과 함께 [주요 구성 요소](https://en.wikipedia.org/wiki/First-class_citizen)입니다.

‘종속성’은 다른 개체가 종속된 개체입니다. 다른 클래스가 종속된 `MessageWriter` 클래스에서 `Write` 메서드를 사용하는 다음 코드를 살펴보세요.

```csharp
public class MessageWriter
{
    public void Write(string message)
    {
        Console.WriteLine($"MessageWriter.Write(message: \"{message}\")");
    }
}
```

클래스에서 `MessageWriter` 클래스의 인스턴스를 만들어 `Write` 메서드를 사용할 수 있습니다. 다음 예제에서 `MessageWriter` 클래스는 `Worker` 클래스의 종속성입니다.

```csharp
public class Worker : BackgroundService
{
    private readonly MessageWriter _messageWriter = new MessageWriter();

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _messageWriter.Write($"Worker running at: {DateTimeOffset.Now}");
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

이 클래스는 `MessageWriter` 클래스를 만들고 이 클래스에 직접 종속됩니다. 이전 예제와 같은 하드 코딩된 종속성은 문제가 있으며 다음과 같은 이유로 사용하지 않아야 합니다.

- `MessageWriter`를 다른 구현으로 바꾸려면 `Worker` 클래스를 수정해야 합니다.
- `MessageWriter`에 종속성이 있으면 `Worker` 클래스에서 해당 종속성도 구성해야 합니다. 여러 클래스가 `MessageWriter`에 종속되어 있는 대형 프로젝트에서는 구성 코드가 앱 전체에 분산됩니다.
- 이 구현은 단위 테스트하기가 어렵습니다. 앱에서 모의 또는 스텁 `MessageWriter` 클래스를 사용해야 하지만, 이 방법에서는 가능하지 않습니다.

종속성 주입은 다음을 통해 이러한 문제를 해결합니다.

- 인퍼테이스 또는 기본 클래스를 사용하여 종속성 구현을 추상화합니다.
- 서비스 컨테이너에 종속성 등록. .NET는 서비스 컨테이너인 <xref:System.IServiceProvider>를 기본 제공합니다. 서비스는 일반적으로 앱 시작 시 등록되고 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>에 추가됩니다. 모든 서비스가 추가되면 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>를 사용하여 서비스 컨테이너를 만듭니다.
- 서비스가 사용되는 클래스의 생성자에 주입됨. 프레임워크가 종속성의 인스턴스를 만들고 더 이상 필요하지 않으면 삭제하는 작업을 담당합니다.

예를 들어 `IMessageWriter` 인터페이스는 `Write` 메서드를 정의합니다.

:::code language="csharp" source="snippets/configuration/dependency-injection/IMessageWriter.cs":::

이 인터페이스는 구체적인 형식 `MessageWriter`에서 구현됩니다.

:::code language="csharp" source="snippets/configuration/dependency-injection/MessageWriter.cs":::

샘플 코드에서는 `IMessageWriter` 서비스를 구체적인 형식 `MessageWriter`로 등록합니다. <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> 메서드는 단일 요청의 수명인 범위가 지정된 수명으로 서비스를 등록합니다. [서비스 수명](#service-lifetimes)에 대해서는 이 문서의 뒷부분에서 설명합니다.

:::code language="csharp" source="snippets/configuration/dependency-injection/Program.cs" highlight="16":::

샘플 앱에서는 `IMessageWriter` 서비스가 요청되며 이 서비스는 `Write` 메서드를 호출하는 데 사용됩니다.

:::code language="csharp" source="snippets/configuration/dependency-injection/Worker.cs":::

DI 패턴을 사용하여 작업자 서비스는

- 구체적인 형식 `MessageWriter`를 사용하지 않고 구현되는 `IMessageWriter` 인터페이스만 사용합니다. 따라서 컨트롤러에서 사용하는 구현을 컨트롤러를 수정하지 않고 쉽게 변경할 수 있습니다.
- `MessageWriter`의 인스턴스를 만들지 않습니다. 해당 인스턴스는 DI 컨테이너에 의해 만들어집니다.

`IMessageWriter` 인터페이스의 구현을 기본 제공 로깅 API를 사용하여 향상할 수 있습니다.

:::code language="csharp" source="snippets/configuration/dependency-injection/LoggingMessageWriter.cs":::

업데이트된 `ConfigureServices` 메서드는 새 `IMessageWriter` 구현을 등록합니다.

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureServices((_, services) =>
            services.AddHostedService<Worker>()
                    .AddScoped<IMessageWriter, LoggingMessageWriter>());
```

`LoggingMessageWriter`는 생성자에서 요청하는 <xref:Microsoft.Extensions.Logging.ILogger%601>에 종속됩니다. `ILogger<TCategoryName>`은 [프레임워크에서 제공하는 서비스](#framework-provided-services)입니다.

종속성 주입을 연결된 방식으로 사용하는 일은 특별한 경우가 아닙니다. 요청된 각 종속성은 차례로 자체 종속성을 요청합니다. 컨테이너는 그래프의 종속성을 해결하고 완전히 해결된 서비스를 반환합니다. 해결해야 하는 종속성이 모인 집합은 일반적으로 종속성 트리, 종속성 그래프 또는 개체 그래프라고 합니다  .

컨테이너는 [개방형 형식(제네릭)](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types)을 활용하여 `ILogger<TCategoryName>`을 해결하므로 모든 [생성된 형식(제네릭)](/dotnet/csharp/language-reference/language-specification/types#constructed-types)을 등록하지 않아도 됩니다.

종속성 주입 용어에서 서비스는 다음과 같습니다.

- 일반적으로 다른 개체에 `IMessageWriter` 서비스와 같은 서비스를 제공하는 개체입니다.
- 서비스에서 웹 서비스를 사용할 수 있지만 웹 서비스와 관련 있는 것은 아닙니다.

해당 프레임워크는 강력한 로깅 시스템을 제공합니다. 이전 예제에 표시된 `IMessageWriter` 구현은 로깅을 구현하는 것이 아니라 기본 DI를 보여 주기 위해 작성되었습니다. 대부분의 앱에서는 로거를 작성할 필요가 없습니다. 다음 코드에서는 `Worker`를 `ConfigureServices`에서 호스팅된 서비스 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>로 등록해야 하는 기본 로깅을 사용하는 방법을 보여 줍니다.

```csharp
public class Worker : BackgroundService
{
    private readonly ILogger<Worker> _logger;

    public Worker(ILogger<Worker> logger) =>
        _logger = logger;

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogInformation("Worker running at: {time}", DateTimeOffset.Now);
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

위의 코드를 사용하여 프레임워크에서 로깅을 제공하므로 `ConfigureServices`를 업데이트할 필요가 없습니다.

## <a name="register-groups-of-services-with-extension-methods"></a>확장 메서드를 사용하여 서비스 그룹 등록

Microsoft Extensions에서는 관련 서비스 그룹을 등록하는 규칙을 사용합니다. 규칙은 단일 `Add{GROUP_NAME}` 확장 메서드를 사용하여 프레임워크 기능에 필요한 모든 서비스를 등록하는 것입니다. 예를 들어 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> 확장 메서드는 옵션을 사용하는 데 필요한 모든 서비스를 등록합니다.

## <a name="framework-provided-services"></a>프레임워크에서 제공하는 서비스

`ConfigureServices` 메서드는 플랫폼 기능을 비롯해 앱이 사용하는 서비스를 등록합니다. 처음에 `ConfigureServices`에 제공되는 `IServiceCollection`에는 [호스트가 구성된 방법](generic-host.md#host-configuration)에 따라 달라지는 프레임워크에 의해 정의되는 서비스가 있습니다. .NET 템플릿을 기반으로 하는 앱의 경우 프레임워크에서 수백 개의 서비스를 등록합니다.

다음 표에는 프레임워크에서 등록한 서비스들의 작은 샘플이 나열되어 있습니다.

| 서비스 종류                                                                       | 수명  |
|------------------------------------------------------------------------------------|-----------|
| <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime>                       | Singleton |
| <xref:Microsoft.Extensions.Logging.ILogger%601?displayProperty=fullName>           | Singleton |
| <xref:Microsoft.Extensions.Logging.ILoggerFactory?displayProperty=fullName>        | Singleton |
| <xref:Microsoft.Extensions.ObjectPool.ObjectPoolProvider?displayProperty=fullName> | Singleton |
| <xref:Microsoft.Extensions.Options.IConfigureOptions%601?displayProperty=fullName> | Transient |
| <xref:Microsoft.Extensions.Options.IOptions%601?displayProperty=fullName>          | Singleton |
| <xref:System.Diagnostics.DiagnosticListener?displayProperty=fullName>              | Singleton |
| <xref:System.Diagnostics.DiagnosticSource?displayProperty=fullName>                | Singleton |

## <a name="service-lifetimes"></a>서비스 수명

다음 수명 중 하나를 사용하여 서비스를 등록할 수 있습니다.

- Transient
- Scoped
- Singleton

다음 섹션에서는 위의 각 수명에 대해 설명합니다. 등록된 각 서비스의 수명을 적절히 선택합니다.

### <a name="transient"></a>Transient

Transient 수명 서비스는 서비스 컨테이너에서 요청할 때마다 만들어집니다. 이 수명은 간단한 상태 비저장 서비스에 가장 적합합니다. <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>를 사용하여 임시 서비스를 등록합니다.

요청을 처리하는 앱에서 Transient 서비스는 요청이 끝날 때 삭제됩니다.

### <a name="scoped"></a>Scoped

웹 애플리케이션의 경우 범위가 지정된 수명은 클라이언트 요청(연결)마다 한 번씩 서비스가 생성됨을 나타냅니다. <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>를 사용하여 범위 지정된 서비스를 등록합니다.

요청을 처리하는 앱에서 Scoped 서비스는 요청이 끝날 때 삭제됩니다.

Entity Framework Core를 사용하는 경우 <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> 확장 메서드는 기본적으로 범위가 지정된 수명으로 `DbContext` 형식을 등록합니다.

> [!NOTE]
> singleton에서 범위가 지정된 서비스를 해결하지 ***마세요**._ 예를 들어 임시 서비스를 통해 간접적으로 해결하지 않도록 주의해야 합니다. 이 경우 후속 요청을 처리할 때 서비스가 잘못된 상태일 수 있습니다. 다음 작업은 괜찮습니다.
>
> - 범위가 지정된 서비스 또는 임시 서비스에서 싱클톤 서비스를 해결합니다.
> - 다른 범위가 지정된 서비스 또는 임시 서비스에서 범위가 지정된 서비스를 해결합니다.

기본적으로 개발 환경에서 수명이 더 긴 다른 서비스에서 서비스를 해결하면 예외가 throw됩니다. 자세한 내용은 [범위 유효성 검사](#scope-validation)를 참조하세요.

### <a name="singleton"></a>Singleton

싱클톤 수명 서비스는 다음과 같은 경우 생성됩니다.

- 처음 요청되는 경우
- 개발자가 구현 인스턴스를 컨테이너에 직접 제공하는 경우 (이 방법은 거의 필요하지 않습니다.)

종속성 주입 컨테이너로부터 서비스 구현에 대한 모든 후속 요청은 동일한 인스턴스를 사용합니다. 앱에 싱글톤 동작이 필요한 경우 서비스 컨테이너가 서비스 수명을 관리하도록 허용합니다. 싱글톤 디자인 패턴을 구현하지 말고 싱글톤을 삭제하는 코드를 제공합니다. 컨테이너에서 서비스를 해결한 코드에서는 서비스를 삭제하면 안 됩니다. 형식 또는 팩터리가 싱글톤으로 등록된 경우 컨테이너에서 싱글톤을 자동으로 삭제합니다.

<xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>를 사용하여 싱글톤 서비스를 등록합니다. 싱글톤 서비스는 스레드로부터 안전해야 하며 상태 비저장 서비스에서 자주 사용됩니다.

요청을 처리하는 앱에서 싱글톤 서비스는 애플리케이션 종료 시 <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider>가 삭제될 때 삭제됩니다. 앱이 종료될 때까지 메모리가 해제되지 않으므로 싱글톤 서비스에서 메모리 사용을 고려합니다.

> [!WARNING]
> 싱글톤에서 범위가 지정된 서비스를 확인하지 ‘마세요’. 이 경우 후속 요청을 처리할 때 서비스가 잘못된 상태일 수 있습니다. 범위가 지정된 서비스 또는 임시 서비스에서 싱글톤 서비스를 해결하는 것이 좋습니다.

## <a name="service-registration-methods"></a>서비스 등록 메서드

프레임워크는 특정 시나리오에 유용한 서비스 등록 확장 방법을 제공합니다.

| 메서드 | 자동<br>개체<br>삭제 | 여러<br>구현 | 인수 전달 |
|--|:-:|:-:|:-:|
| `Add{LIFETIME}<{SERVICE}, {IMPLEMENTATION}>()`<br><br>예제:<br><br>`services.AddSingleton<IMyDep, MyDep>();` | 예 | 예 | 예 |
| `Add{LIFETIME}<{SERVICE}>(sp => new {IMPLEMENTATION})`<br><br>예제:<br><br>`services.AddSingleton<IMyDep>(sp => new MyDep());`<br>`services.AddSingleton<IMyDep>(sp => new MyDep(99));` | 예 | 예 | 예 |
| `Add{LIFETIME}<{IMPLEMENTATION}>()`<br><br>예제:<br><br>`services.AddSingleton<MyDep>();` | 예 | 예 | 예 |
| `AddSingleton<{SERVICE}>(new {IMPLEMENTATION})`<br><br>예제:<br><br>`services.AddSingleton<IMyDep>(new MyDep());`<br>`services.AddSingleton<IMyDep>(new MyDep(99));` | 예 | 예 | 예 |
| `AddSingleton(new {IMPLEMENTATION})`<br><br>예제:<br><br>`services.AddSingleton(new MyDep());`<br>`services.AddSingleton(new MyDep(99));` | 예 | 예 | 예 |

형식 삭제에 대한 자세한 내용은 [서비스의 삭제](dependency-injection-guidelines.md#disposal-of-services) 섹션을 참조하세요.

구현 형식만으로 서비스를 등록하는 것은 동일한 구현 및 서비스 형식으로 해당 서비스를 등록하는 것과 같습니다. 따라서 명시적 서비스 형식을 사용하지 않는 메서드를 사용하여 서비스의 여러 구현을 등록할 수 없습니다. 이러한 메서드는 서비스의 여러 ‘인스턴스’를 등록할 수 있지만 모두 동일한 ‘구현’ 형식을 사용합니다.

위의 서비스 등록 메서드 중 하나를 사용하여 동일한 서비스 형식의 여러 서비스 인스턴스를 등록할 수 있습니다. 다음 예제에서는 `IMessageWriter`를 서비스 형식으로 사용하여 `AddSingleton`을 두 번 호출합니다. 두 번째 `AddSingleton` 호출은 `IMessageWriter`로 확인되면 이전 호출을 재정의하고 `IEnumerable<IMessageWriter>`를 통해 여러 서비스가 확인되면 이전 호출에 추가됩니다. 서비스는 `IEnumerable<{SERVICE}>`를 통해 해결될 때 등록된 순서로 나타납니다.

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/Program.cs" highlight="19-24":::

위의 샘플 소스 코드는 `IMessageWriter`의 두 가지 구현을 등록합니다.

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/ExampleService.cs" highlight="9-18":::

`ExampleService`는 두 가지 생성자 매개 변수인 단일 `IMessageWriter` 및 `IEnumerable<IMessageWriter>`를 정의합니다. 단일 `IMessageWriter`는 등록된 마지막 구현이고, `IEnumerable<IMessageWriter>`는 등록된 모든 구현을 나타냅니다.

또한 프레임워크에서는 아직 등록된 구현이 없는 경우에만 서비스를 등록하는 `TryAdd{LIFETIME}` 확장 메서드를 제공합니다.

다음 예제에서 `AddSingleton`을 호출하면 `ConsoleMessageWriter`가 `IMessageWriter`에 대한 구현으로 등록됩니다. `TryAddSingleton`에 대한 호출은 `IMessageWriter`에 이미 등록된 구현이 있으므로 아무런 효과가 없습니다.

```csharp
services.AddSingleton<IMessageWriter, ConsoleMessageWriter>();
services.TryAddSingleton<IMessageWriter, LoggingMessageWriter>();
```

`TryAddSingleton`은 이미 추가되었기 때문에 ‘시도’가 실패하므로 아무런 효과가 없습니다. `ExampleService`는 다음을 어설션합니다.

```csharp
public class ExampleService
{
    public ExampleService(
        IMessageWriter messageWriter,
        IEnumerable<IMessageWriter> messageWriters)
    {
        Trace.Assert(messageWriter is ConsoleMessageWriter);
        Trace.Assert(messageWriters.Single() is ConsoleMessageWriter);
    }
}
```

자세한 내용은 다음을 참조하세요.

- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAdd%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddTransient%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddScoped%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddSingleton%2A>

[TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) 메서드는 ‘동일한 형식’의 구현이 아직 없는 경우에만 서비스를 등록합니다. 여러 서비스가 `IEnumerable<{SERVICE}>`를 통해 해결됩니다. 서비스를 등록할 때 동일한 형식 중 하나가 아직 추가되지 않은 경우 인스턴스를 추가합니다. 라이브러리 작성자는 컨테이너에 있는 특정 구현의 여러 복사본이 등록되지 않도록 `TryAddEnumerable`을 사용합니다.

다음 예제에서 `TryAddEnumerable`을 처음 호출하면 `MessageWriter`가 `IMessageWriter1`에 대한 구현으로 등록됩니다. 두 번째 호출에서는 `IMessageWriter2`에 대한 `MessageWriter`를 등록합니다. 세 번째 호출은 `IMessageWriter1`에 `MessageWriter`의 등록된 구현이 이미 있으므로 아무런 효과가 없습니다.

```csharp
public interface IMessageWriter1 { }
public interface IMessageWriter2 { }

public class MessageWriter : IMessageWriter1, IMessageWriter2
{
}

services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter2, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
```

서비스 등록은 동일한 형식의 여러 구현을 등록하는 경우를 제외하고 일반적으로 순서와 상관이 없습니다.

`IServiceCollection`은 <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> 개체의 컬렉션입니다. 다음 예에서는 `ServiceDescriptor`을 만든 후 추가하여 서비스를 등록하는 방법을 보여 줍니다.

```csharp
string secretKey = Configuration["SecretKey"];
var descriptor = new ServiceDescriptor(
    typeof(IMessageWriter),
    _ => new DefaultMessageWriter(secretKey),
    ServiceLifetime.Transient);

services.Add(descriptor);
```

기본 제공 `Add{LIFETIME}` 메서드는 같은 방법을 사용합니다. 예를 들어 [AddScoped 소스 코드](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237)를 참조하세요.

### <a name="constructor-injection-behavior"></a>생성자 주입 동작

다음을 사용하여 서비스를 확인할 수 있습니다.

- <xref:System.IServiceProvider>
- <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:
  - 컨테이너에 등록되지 않은 개체를 만듭니다.
  - 일부 프레임워크 기능과 함께 사용됩니다.

생성자에는 종속성 주입으로 제공되지 않는 인수를 사용할 수 있지만, 인수에 기본값을 할당해야 합니다.

`IServiceProvider` 또는 `ActivatorUtilities`로 서비스를 해결하는 경우 생성자 주입에 *public* 생성자가 필요합니다.

`ActivatorUtilities`로 서비스를 해결하는 경우 생성자 주입을 위해서는 적합한 생성자가 하나만 있어야 합니다. 생성자 오버로드가 지원되지만, 해당 인수가 모두 종속성 주입으로 처리될 수 있는 하나의 오버로드만 존재할 수 있습니다.

## <a name="scope-validation"></a>범위 유효성 검사

앱이 `Development` 환경에서 실행되고 호스트를 빌드하기 위해 [CreateDefaultBuilder](generic-host.md#default-builder-settings)를 호출하는 경우 기본 서비스 공급자가 다음을 확인하는 검사를 수행합니다.

- 범위가 지정된 서비스는 루트 서비스 공급자에서 확인되지 않습니다.
- 범위가 지정된 서비스는 싱글톤에 삽입되지 않습니다.

루트 서비스 공급자는 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>를 호출할 때 만들어집니다. 루트 서비스 공급자의 수명은 공급자가 앱과 함께 시작되고 앱이 종료될 때 삭제되는 앱의 수명에 해당합니다.

범위가 지정된 서비스는 서비스를 만든 컨테이너에 의해 삭제됩니다. 범위가 지정된 서비스가 루트 컨테이너에서 만들어지는 경우 서비스의 수명은 사실상 싱글톤으로 승격됩니다. 해당 서비스는 앱이 종료될 때 루트 컨테이너에 의해서만 삭제되기 때문입니다. 서비스 범위의 유효성 검사는 `BuildServiceProvider`가 호출될 경우 이러한 상황을 감지합니다.

## <a name="see-also"></a>참고 항목

- [.NET에서 종속성 주입 사용](dependency-injection-usage.md)
- [종속성 주입 지침](dependency-injection-guidelines.md)
- [ASP.NET Core에서 종속성 주입](/aspnet/core/fundamentals/dependency-injection)
- [DI 앱 개발을 위한 NDC 컨퍼런스 패턴](https://www.youtube.com/watch?v=x-C-CNBVTaY)
- [명시적 종속성 원칙](../../architecture/modern-web-apps-azure/architectural-principles.md#explicit-dependencies)
- [Inversion of Control 컨테이너 및 종속성 주입 패턴(Martin Fowler)](https://www.martinfowler.com/articles/injection.html)
- DI 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.
