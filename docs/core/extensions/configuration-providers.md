---
title: .NET의 구성 공급자
description: 구성 공급자 API를 사용하여 .NET 애플리케이션을 구성하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 03/08/2021
ms.openlocfilehash: 5f248c93de1773a8bbe8209f002806fb196bb260
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605011"
---
# <a name="configuration-providers-in-net"></a><span data-ttu-id="1932c-103">.NET의 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-103">Configuration providers in .NET</span></span>

<span data-ttu-id="1932c-104">.NET에서 구성은 구성 공급자를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-104">Configuration in .NET is possible with configuration providers.</span></span> <span data-ttu-id="1932c-105">다양한 구성 소스를 사용하는 여러 유형의 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-105">There are several types of providers that rely on various configuration sources.</span></span> <span data-ttu-id="1932c-106">이 문서에서는 모든 다양한 구성 공급자와 해당 소스를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-106">This article details all of the different configuration providers and their corresponding sources.</span></span>

- [<span data-ttu-id="1932c-107">파일 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-107">File configuration provider</span></span>](#file-configuration-provider)
- [<span data-ttu-id="1932c-108">환경 변수 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-108">Environment variable configuration provider</span></span>](#environment-variable-configuration-provider)
- [<span data-ttu-id="1932c-109">명령줄 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-109">Command-line configuration provider</span></span>](#command-line-configuration-provider)
- [<span data-ttu-id="1932c-110">파일별 키 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-110">Key-per-file configuration provider</span></span>](#key-per-file-configuration-provider)
- [<span data-ttu-id="1932c-111">메모리 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-111">Memory configuration provider</span></span>](#memory-configuration-provider)

## <a name="file-configuration-provider"></a><span data-ttu-id="1932c-112">파일 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-112">File configuration provider</span></span>

<span data-ttu-id="1932c-113"><xref:Microsoft.Extensions.Configuration.FileConfigurationProvider>는 파일 시스템에서 구성을 로드하기 위한 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-113"><xref:Microsoft.Extensions.Configuration.FileConfigurationProvider> is the base class for loading configuration from the file system.</span></span> <span data-ttu-id="1932c-114">다음 구성 공급자는 `FileConfigurationProvider`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-114">The following configuration providers derive from `FileConfigurationProvider`:</span></span>

- [<span data-ttu-id="1932c-115">JSON 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-115">JSON configuration provider</span></span>](#json-configuration-provider)
- [<span data-ttu-id="1932c-116">XML 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-116">XML configuration provider</span></span>](#xml-configuration-provider)
- [<span data-ttu-id="1932c-117">INI 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-117">INI configuration provider</span></span>](#ini-configuration-provider)

### <a name="json-configuration-provider"></a><span data-ttu-id="1932c-118">JSON 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-118">JSON configuration provider</span></span>

<span data-ttu-id="1932c-119"><xref:Microsoft.Extensions.Configuration.Json.JsonConfigurationProvider> 클래스는 JSON 파일에서 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-119">The <xref:Microsoft.Extensions.Configuration.Json.JsonConfigurationProvider> class loads configuration from a JSON file.</span></span> <span data-ttu-id="1932c-120">[`Microsoft.Extensions.Configuration.Json`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Json) NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-120">Install the [`Microsoft.Extensions.Configuration.Json`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Json) NuGet package.</span></span>

<span data-ttu-id="1932c-121">오버로드는 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-121">Overloads can specify:</span></span>

- <span data-ttu-id="1932c-122">파일이 선택 사항인지 여부</span><span class="sxs-lookup"><span data-stu-id="1932c-122">Whether the file is optional</span></span>
- <span data-ttu-id="1932c-123">파일을 변경하는 경우 구성이 다시 로드되는지 여부</span><span class="sxs-lookup"><span data-stu-id="1932c-123">Whether the configuration is reloaded if the file changes</span></span>

<span data-ttu-id="1932c-124">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="1932c-124">Consider the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="1-39,43-44" highlight="23-29":::

<span data-ttu-id="1932c-125">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="1932c-125">The preceding code:</span></span>

- <span data-ttu-id="1932c-126"><xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> 메서드에 기본적으로 추가된 기존 구성 공급자를 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-126">Clears all existing configuration providers that were added by default in the <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> method.</span></span>
- <span data-ttu-id="1932c-127">다음 옵션을 사용하여 *appsettings.json* 및 *appsettings*.`Environment`.*json* 파일을 로드하도록 JSON 구성 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-127">Configures the JSON configuration provider to load the *appsettings.json* and  *appsettings*.`Environment`.*json* files with the following options:</span></span>
  - <span data-ttu-id="1932c-128">`optional: true`: 파일은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-128">`optional: true`: The file is optional.</span></span>
  - <span data-ttu-id="1932c-129">`reloadOnChange: true`은: 변경 내용이 저장되면 파일이 다시 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-129">`reloadOnChange: true` : The file is reloaded when changes are saved.</span></span>

<span data-ttu-id="1932c-130">JSON 설정은 [환경 변수 구성 공급자](#environment-variable-configuration-provider) 및 [명령줄 구성 공급자](#command-line-configuration-provider)의 설정에 따라 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-130">The JSON settings are overridden by settings in the [Environment variables configuration provider](#environment-variable-configuration-provider) and the [Command-line configuration provider](#command-line-configuration-provider).</span></span>

<span data-ttu-id="1932c-131">다양한 구성 설정을 사용하는 예제 *appsettings.json* 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-131">An example *appsettings.json* file with various configuration settings follows:</span></span>

:::code language="json" source="snippets/configuration/console-json/appsettings.json":::

<span data-ttu-id="1932c-132">구성 공급자가 추가된 후 <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> 인스턴스에서 <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder.Build?displayProperty=nameWithType>를 호출하여 <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-132">From the <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> instance, after configuration providers have been added you can call <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder.Build?displayProperty=nameWithType> to get the <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> object.</span></span> <span data-ttu-id="1932c-133">구성 루트는 구성 계층 구조의 루트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-133">The configuration root represents the root of a configuration hierarchy.</span></span> <span data-ttu-id="1932c-134">구성의 섹션은 .NET 개체의 인스턴스에 바인딩되고 나중에 <xref:Microsoft.Extensions.Options.IOptions%601> 종속성 주입을 통해 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-134">Sections from the configuration can be bound to instances of .NET objects, and later provided as <xref:Microsoft.Extensions.Options.IOptions%601> through dependency injection.</span></span>

<span data-ttu-id="1932c-135">다음과 같이 정의된 `TransientFaultHandlingOptions` 클래스를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="1932c-135">Consider the `TransientFaultHandlingOptions` class defined as follows:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs":::

<span data-ttu-id="1932c-136">다음 코드는 구성 루트를 빌드하고, 섹션을 `TransientFaultHandlingOptions` 클래스 형식에 바인딩하고, 바인딩된 값을 콘솔 창에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-136">The following code builds the configuration root, binds a section to the `TransientFaultHandlingOptions` class type, and prints the bound values to the console window:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

<span data-ttu-id="1932c-137">애플리케이션은 다음 샘플 출력을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-137">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="40-42":::

### <a name="xml-configuration-provider"></a><span data-ttu-id="1932c-138">XML 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-138">XML configuration provider</span></span>

<span data-ttu-id="1932c-139"><xref:Microsoft.Extensions.Configuration.Xml.XmlConfigurationProvider> 클래스는 런타임에 XML 파일에서 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-139">The <xref:Microsoft.Extensions.Configuration.Xml.XmlConfigurationProvider> class loads configuration from an XML file at runtime.</span></span> <span data-ttu-id="1932c-140">[`Microsoft.Extensions.Configuration.Xml`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Xml) NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-140">Install the [`Microsoft.Extensions.Configuration.Xml`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Xml) NuGet package.</span></span>

<span data-ttu-id="1932c-141">다음 코드에서는 XML 구성 공급자를 사용한 XML 파일의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-141">The following code demonstrates configuration of XML files using the XML configuration provider.</span></span>

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="1-34,52,58-59" highlight="23-34":::

<span data-ttu-id="1932c-142">앞의 코드가 하는 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-142">The preceding code:</span></span>

- <span data-ttu-id="1932c-143"><xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> 메서드에 기본적으로 추가된 기존 구성 공급자를 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-143">Clears all existing configuration providers that were added by default in the <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])> method.</span></span>
- <span data-ttu-id="1932c-144">다음 옵션을 사용하여 *appsettings.xml* 및 *repeating-example.xml* 파일을 로드하도록 XML 구성 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-144">Configures the XML configuration provider to load the *appsettings.xml* and *repeating-example.xml* files with the following options:</span></span>
  - <span data-ttu-id="1932c-145">`optional: true`: 파일은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-145">`optional: true`: The file is optional.</span></span>
  - <span data-ttu-id="1932c-146">`reloadOnChange: true`은: 변경 내용이 저장되면 파일이 다시 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-146">`reloadOnChange: true` : The file is reloaded when changes are saved.</span></span>
- <span data-ttu-id="1932c-147">환경 변수 구성 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-147">Configures the environment variables configuration provider.</span></span>
- <span data-ttu-id="1932c-148">지정된 `args`에 인수가 포함된 경우 명령줄 구성 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-148">Configures the command-line configuration provider if the given `args` contains arguments.</span></span>

<span data-ttu-id="1932c-149">XML 설정은 [환경 변수 구성 공급자](#environment-variable-configuration-provider) 및 [명령줄 구성 공급자](#command-line-configuration-provider)의 설정에 따라 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-149">The XML settings are overridden by settings in the [Environment variables configuration provider](#environment-variable-configuration-provider) and the [Command-line configuration provider](#command-line-configuration-provider).</span></span>

<span data-ttu-id="1932c-150">다양한 구성 설정을 사용하는 예제 *appsettings.xml* 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-150">An example *appsettings.xml* file with various configuration settings follows:</span></span>

:::code language="xml" source="snippets/configuration/console-xml/appsettings.xml":::

<span data-ttu-id="1932c-151">같은 요소 이름을 사용하는 반복 요소는 다음과 같이 `name` 특성을 사용하여 요소를 구분하면 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-151">Repeating elements that use the same element name work if the `name` attribute is used to distinguish the elements:</span></span>

:::code language="xml" source="snippets/configuration/console-xml/repeating-example.xml":::

<span data-ttu-id="1932c-152">다음 코드는 이전 구성 파일을 읽고 키 및 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-152">The following code reads the previous configuration file and displays the keys and values:</span></span>

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="36-51":::

<span data-ttu-id="1932c-153">애플리케이션은 다음 샘플 출력을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-153">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/console-xml/Program.cs" range="53-57":::

<span data-ttu-id="1932c-154">특성을 사용하여 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-154">Attributes can be used to supply values:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <key attribute="value" />
  <section>
    <key attribute="value" />
  </section>
</configuration>
```

<span data-ttu-id="1932c-155">이전 구성 파일은 `value`와 함께 다음 키를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-155">The previous configuration file loads the following keys with `value`:</span></span>

- `key:attribute`
- `section:key:attribute`

### <a name="ini-configuration-provider"></a><span data-ttu-id="1932c-156">INI 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-156">INI configuration provider</span></span>

<span data-ttu-id="1932c-157"><xref:Microsoft.Extensions.Configuration.Ini.IniConfigurationProvider> 클래스는 런타임에 INI 파일에서 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-157">The <xref:Microsoft.Extensions.Configuration.Ini.IniConfigurationProvider> class loads configuration from an INI file at runtime.</span></span> <span data-ttu-id="1932c-158">[`Microsoft.Extensions.Configuration.Ini`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Ini) NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-158">Install the [`Microsoft.Extensions.Configuration.Ini`](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.Ini)  NuGet package.</span></span>

<span data-ttu-id="1932c-159">다음 코드는 모든 구성 공급자를 지우고 두 개의 INI 파일을 소스로 사용하여 `IniConfigurationProvider`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-159">The following code clears all the configuration providers and adds the `IniConfigurationProvider` with two INI files as the source:</span></span>

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="1-37,44-45" highlight="24-30":::

<span data-ttu-id="1932c-160">다양한 구성 설정을 사용하는 예제 *appsettings.ini* 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-160">An example *appsettings.ini* file with various configuration settings follows:</span></span>

:::code language="ini" source="snippets/configuration/console-ini/appsettings.ini":::

<span data-ttu-id="1932c-161">다음 코드는 이전 구성 설정을 콘솔 창에 기록하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-161">The following code displays the preceding configuration settings by writing them to the console window:</span></span>

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="32-36":::

<span data-ttu-id="1932c-162">애플리케이션은 다음 샘플 출력을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-162">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/console-ini/Program.cs" range="38-43":::

## <a name="environment-variable-configuration-provider"></a><span data-ttu-id="1932c-163">환경 변수 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-163">Environment variable configuration provider</span></span>

<span data-ttu-id="1932c-164">기본 구성을 사용하여 <xref:Microsoft.Extensions.Configuration.EnvironmentVariables.EnvironmentVariablesConfigurationProvider>는 *appsettings.json*, *appsettings.* `Environment` *.json*, 비밀 관리자를 읽은 후 환경 변수 키-값 쌍에서 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-164">Using the default configuration, the <xref:Microsoft.Extensions.Configuration.EnvironmentVariables.EnvironmentVariablesConfigurationProvider> loads configuration from environment variable key-value pairs after reading *appsettings.json*, *appsettings.*`Environment`*.json*, and Secret manager.</span></span> <span data-ttu-id="1932c-165">따라서 환경에서 읽은 키 값이 *appsettings.json*, *appsettings.* `Environment` *.json* 및 비밀 관리자에서 읽은 값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-165">Therefore, key values read from the environment override values read from *appsettings.json*, *appsettings.*`Environment`*.json*, and Secret manager.</span></span>

<span data-ttu-id="1932c-166">`:` 구분 기호는 모든 플랫폼의 환경 변수 계층적 키에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-166">The `:` separator doesn't work with environment variable hierarchical keys on all platforms.</span></span> <span data-ttu-id="1932c-167">이중 밑줄(`__`)은 자동으로 `:`으로 바뀌며 모든 플랫폼에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-167">The double underscore (`__`) is automatically replaced by a `:` and is supported by all platforms.</span></span> <span data-ttu-id="1932c-168">예를 들어 `:` 구분 기호는 [Bash](https://linuxhint.com/bash-environment-variables)에서 지원되지 않지만 `__`은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-168">For example, the `:` separator is not supported by [Bash](https://linuxhint.com/bash-environment-variables), but `__` is.</span></span>

<span data-ttu-id="1932c-169">다음 `set` 명령은,</span><span class="sxs-lookup"><span data-stu-id="1932c-169">The following `set` commands:</span></span>

- <span data-ttu-id="1932c-170">Windows에서 위의 예제에 나오는 환경 키 및 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-170">Set the environment keys and values of the preceding example on Windows.</span></span>
- <span data-ttu-id="1932c-171">기본값에서 설정을 변경하여 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-171">Test the settings by changing them from their default values.</span></span> <span data-ttu-id="1932c-172">`dotnet run` 명령은 프로젝트 디렉터리에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-172">The `dotnet run` command must be run in the project directory.</span></span>

```dotnetcli
set SecretKey="Secret key from environment"
set TransientFaultHandlingOptions__Enabled="true"
set TransientFaultHandlingOptions__AutoRetryDelay="00:00:13"

dotnet run
```

<span data-ttu-id="1932c-173">위의 환경 설정은,</span><span class="sxs-lookup"><span data-stu-id="1932c-173">The preceding environment settings:</span></span>

- <span data-ttu-id="1932c-174">설정된 명령 창에서 시작된 프로세스에서만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-174">Are only set in processes launched from the command window they were set in.</span></span>
- <span data-ttu-id="1932c-175">Visual Studio에서 시작된 웹앱에서는 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-175">Won't be read by web apps launched with Visual Studio.</span></span>

<span data-ttu-id="1932c-176">다음 [setx](/windows-server/administration/windows-commands/setx) 명령을 사용하여 Windows에서 환경 키 및 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-176">The following [setx](/windows-server/administration/windows-commands/setx) commands can be used to set the environment keys and values on Windows.</span></span> <span data-ttu-id="1932c-177">`set`와 달리, `setx` 설정은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-177">Unlike `set`, `setx` settings are persisted.</span></span> <span data-ttu-id="1932c-178">`/M`은 시스템 환경에서 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-178">`/M` sets the variable in the system environment.</span></span> <span data-ttu-id="1932c-179">`/M` 스위치를 사용하지 않으면 사용자 환경 변수가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-179">If the `/M` switch isn't used, a user environment variable is set.</span></span>

```dotnetcli
setx SecretKey "Secret key from setx environment" /M
setx TransientFaultHandlingOptions__Enabled "true" /M
setx TransientFaultHandlingOptions__AutoRetryDelay "00:00:05" /M

dotnet run
```

<span data-ttu-id="1932c-180">위의 명령이 *apsettings.json* 및 *appsettings.* `Environment` *.json* 을 재정의하는지 테스트하려면:</span><span class="sxs-lookup"><span data-stu-id="1932c-180">To test that the preceding commands override *appsettings.json* and *appsettings.*`Environment`*.json*:</span></span>

- <span data-ttu-id="1932c-181">Visual Studio를 사용하는 경우: Visual Studio를 종료했다가 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-181">With Visual Studio: Exit and restart Visual Studio.</span></span>
- <span data-ttu-id="1932c-182">CLI를 사용하는 경우: 새 명령 창을 시작하고 `dotnet run`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-182">With the CLI: Start a new command window and enter `dotnet run`.</span></span>

<span data-ttu-id="1932c-183">환경 변수의 접두사를 지정하는 문자열을 사용하여 <xref:Microsoft.Extensions.Configuration.EnvironmentVariablesExtensions.AddEnvironmentVariables%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-183">Call <xref:Microsoft.Extensions.Configuration.EnvironmentVariablesExtensions.AddEnvironmentVariables%2A> with a string to specify a prefix for environment variables:</span></span>

:::code language="csharp" source="snippets/configuration/console-env/Program.cs" highlight="21-22":::

<span data-ttu-id="1932c-184">위의 코드에서</span><span class="sxs-lookup"><span data-stu-id="1932c-184">In the preceding code:</span></span>

- <span data-ttu-id="1932c-185">`config.AddEnvironmentVariables(prefix: "CustomPrefix_")`는 기본 구성 공급자 뒤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-185">`config.AddEnvironmentVariables(prefix: "CustomPrefix_")` is added after the default configuration providers.</span></span> <span data-ttu-id="1932c-186">구성 공급자 순서 지정 예제는 [XML 구성 공급자](#xml-configuration-provider)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1932c-186">For an example of ordering the configuration providers, see [XML configuration provider](#xml-configuration-provider).</span></span>
- <span data-ttu-id="1932c-187">`CustomPrefix_` 접두사를 사용하여 설정된 환경 변수는 기본 구성 공급자를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-187">Environment variables set with the `CustomPrefix_` prefix override the default configuration providers.</span></span> <span data-ttu-id="1932c-188">여기에는 접두사 없는 환경 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-188">This includes environment variables without the prefix.</span></span>

<span data-ttu-id="1932c-189">구성 키-값 쌍을 읽으면 접두사는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-189">The prefix is stripped off when the configuration key-value pairs are read.</span></span>

<span data-ttu-id="1932c-190">다음 명령은 사용자 지정 접두사를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-190">The following commands test the custom prefix:</span></span>

```dotnetcli
set CustomPrefix__SecretKey="Secret key with CustomPrefix_ environment"
set CustomPrefix__TransientFaultHandlingOptions__Enabled=true
set CustomPrefix__TransientFaultHandlingOptions__AutoRetryDelay=00:00:21

dotnet run
```

<span data-ttu-id="1932c-191">기본 구성은 `DOTNET_` 접두사가 붙은 환경 변수 및 명령줄 인수를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-191">The default configuration loads environment variables and command-line arguments prefixed with `DOTNET_`.</span></span> <span data-ttu-id="1932c-192">`DOTNET_` 접두사는 .NET에서 [호스트](generic-host.md#host-configuration) 및 [앱 구성](generic-host.md#app-configuration)에 사용되지만 사용자 구성에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-192">The `DOTNET_` prefix is used by .NET for [host](generic-host.md#host-configuration) and [app configuration](generic-host.md#app-configuration), but not for user configuration.</span></span>

<span data-ttu-id="1932c-193">호스트 및 앱 구성에 대한 자세한 내용은 [.NET 제네릭 호스트](generic-host.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1932c-193">For more information on host and app configuration, see [.NET Generic Host](generic-host.md).</span></span>

<span data-ttu-id="1932c-194">[Azure App Service](https://azure.microsoft.com/services/app-service)의 **설정 > 구성** 페이지에서 **새 애플리케이션 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-194">On [Azure App Service](https://azure.microsoft.com/services/app-service), select **New application setting** on the **Settings > Configuration** page.</span></span> <span data-ttu-id="1932c-195">Azure App Service 애플리케이션 설정은,</span><span class="sxs-lookup"><span data-stu-id="1932c-195">Azure App Service application settings are:</span></span>

- <span data-ttu-id="1932c-196">미사용 시 암호화되고 암호화된 채널을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-196">Encrypted at rest and transmitted over an encrypted channel.</span></span>
- <span data-ttu-id="1932c-197">환경 변수로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-197">Exposed as environment variables.</span></span>

### <a name="connection-string-prefixes"></a><span data-ttu-id="1932c-198">연결 문자열 접두사</span><span class="sxs-lookup"><span data-stu-id="1932c-198">Connection string prefixes</span></span>

<span data-ttu-id="1932c-199">구성 API에는 네 개의 연결 문자열 환경 변수에 대한 특별한 처리 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-199">The Configuration API has special processing rules for four connection string environment variables.</span></span> <span data-ttu-id="1932c-200">해당 연결 문자열은 앱 환경의 Azure 연결 문자열을 구성하는 데 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-200">These connection strings are involved in configuring Azure connection strings for the app environment.</span></span> <span data-ttu-id="1932c-201">기본 구성을 사용하거나 `AddEnvironmentVariables`에 제공된 접두사가 없는 경우 표에 표시된 접두사가 붙은 환경 변수가 앱에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-201">Environment variables with the prefixes shown in the table are loaded into the app with the default configuration or when no prefix is supplied to `AddEnvironmentVariables`.</span></span>

| <span data-ttu-id="1932c-202">연결 문자열 접두사</span><span class="sxs-lookup"><span data-stu-id="1932c-202">Connection string prefix</span></span> | <span data-ttu-id="1932c-203">공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-203">Provider</span></span>                                                                |
|--------------------------|-------------------------------------------------------------------------|
| `CUSTOMCONNSTR_`         | <span data-ttu-id="1932c-204">사용자 지정 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-204">Custom provider</span></span>                                                         |
| `MYSQLCONNSTR_`          | [<span data-ttu-id="1932c-205">MySQL</span><span class="sxs-lookup"><span data-stu-id="1932c-205">MySQL</span></span>](https://www.mysql.com)                                          |
| `SQLAZURECONNSTR_`       | [<span data-ttu-id="1932c-206">Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="1932c-206">Azure SQL Database</span></span>](https://azure.microsoft.com/services/sql-database) |
| `SQLCONNSTR_`            | [<span data-ttu-id="1932c-207">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1932c-207">SQL Server</span></span>](https://www.microsoft.com/sql-server)                      |

<span data-ttu-id="1932c-208">표에 표시된 네 개 접두사 중 하나가 붙은 환경 변수가 검색되어 구성으로 로드되면 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-208">When an environment variable is discovered and loaded into configuration with any of the four prefixes shown in the table:</span></span>

- <span data-ttu-id="1932c-209">환경 변수 접두사를 제거하고 구성 키 섹션(`ConnectionStrings`)을 추가하여 구성 키가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-209">The configuration key is created by removing the environment variable prefix and adding a configuration key section (`ConnectionStrings`).</span></span>
- <span data-ttu-id="1932c-210">데이터베이스 연결 제공자(지정된 공급자가 없는 `CUSTOMCONNSTR_` 제외)를 나타내는 새 구성 키-값 쌍이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-210">A new configuration key-value pair is created that represents the database connection provider (except for `CUSTOMCONNSTR_`, which has no stated provider).</span></span>

| <span data-ttu-id="1932c-211">환경 변수 키</span><span class="sxs-lookup"><span data-stu-id="1932c-211">Environment variable key</span></span> | <span data-ttu-id="1932c-212">변환된 구성 키</span><span class="sxs-lookup"><span data-stu-id="1932c-212">Converted configuration key</span></span> | <span data-ttu-id="1932c-213">공급자 구성 항목</span><span class="sxs-lookup"><span data-stu-id="1932c-213">Provider configuration entry</span></span>                                                    |
|--------------------------|-----------------------------|---------------------------------------------------------------------------------|
| `CUSTOMCONNSTR_{KEY}`    | `ConnectionStrings:{KEY}`   | <span data-ttu-id="1932c-214">구성 항목이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-214">Configuration entry not created.</span></span>                                                |
| `MYSQLCONNSTR_{KEY}`     | `ConnectionStrings:{KEY}`   | <span data-ttu-id="1932c-215">키: `ConnectionStrings:{KEY}_ProviderName`:</span><span class="sxs-lookup"><span data-stu-id="1932c-215">Key: `ConnectionStrings:{KEY}_ProviderName`:</span></span><br><span data-ttu-id="1932c-216">값: `MySql.Data.MySqlClient`</span><span class="sxs-lookup"><span data-stu-id="1932c-216">Value: `MySql.Data.MySqlClient`</span></span> |
| `SQLAZURECONNSTR_{KEY}`  | `ConnectionStrings:{KEY}`   | <span data-ttu-id="1932c-217">키: `ConnectionStrings:{KEY}_ProviderName`:</span><span class="sxs-lookup"><span data-stu-id="1932c-217">Key: `ConnectionStrings:{KEY}_ProviderName`:</span></span><br><span data-ttu-id="1932c-218">값: `System.Data.SqlClient`</span><span class="sxs-lookup"><span data-stu-id="1932c-218">Value: `System.Data.SqlClient`</span></span>  |
| `SQLCONNSTR_{KEY}`       | `ConnectionStrings:{KEY}`   | <span data-ttu-id="1932c-219">키: `ConnectionStrings:{KEY}_ProviderName`:</span><span class="sxs-lookup"><span data-stu-id="1932c-219">Key: `ConnectionStrings:{KEY}_ProviderName`:</span></span><br><span data-ttu-id="1932c-220">값: `System.Data.SqlClient`</span><span class="sxs-lookup"><span data-stu-id="1932c-220">Value: `System.Data.SqlClient`</span></span>  |

### <a name="environment-variables-set-in-launchsettingsjson"></a><span data-ttu-id="1932c-221">launchSettings.json에 설정된 환경 변수</span><span class="sxs-lookup"><span data-stu-id="1932c-221">Environment variables set in launchSettings.json</span></span>

<span data-ttu-id="1932c-222">*launchSettings.json* 에 설정된 환경 변수는 시스템 환경에 설정된 변수를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-222">Environment variables set in *launchSettings.json* override those set in the system environment.</span></span>

## <a name="command-line-configuration-provider"></a><span data-ttu-id="1932c-223">명령줄 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-223">Command-line configuration provider</span></span>

<span data-ttu-id="1932c-224">기본 구성을 사용하여 <xref:Microsoft.Extensions.Configuration.CommandLine.CommandLineConfigurationProvider>는 다음 구성 소스 뒤에 명령줄 인수 키-값 쌍에서 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-224">Using the default configuration, the <xref:Microsoft.Extensions.Configuration.CommandLine.CommandLineConfigurationProvider> loads configuration from command-line argument key-value pairs after the following configuration sources:</span></span>

- <span data-ttu-id="1932c-225">*appsettings.json* 및 *appsettings*.`Environment`.*json* 파일</span><span class="sxs-lookup"><span data-stu-id="1932c-225">*appsettings.json* and *appsettings*.`Environment`.*json* files.</span></span>
- <span data-ttu-id="1932c-226">`Development` 발 환경의 앱 비밀(비밀 관리자)</span><span class="sxs-lookup"><span data-stu-id="1932c-226">App secrets (Secret Manager) in the `Development` environment.</span></span>
- <span data-ttu-id="1932c-227">환경 변수.</span><span class="sxs-lookup"><span data-stu-id="1932c-227">Environment variables.</span></span>

<span data-ttu-id="1932c-228">기본적으로 명령줄에 설정된 구성 값은 다른 모든 구성 공급자를 사용하여 설정된 구성 값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-228">By default, configuration values set on the command line override configuration values set with all the other configuration providers.</span></span>

### <a name="command-line-arguments"></a><span data-ttu-id="1932c-229">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="1932c-229">Command-line arguments</span></span>

<span data-ttu-id="1932c-230">다음 명령은 `=`을 사용하여 키 및 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-230">The following command sets keys and values using `=`:</span></span>

```dotnetcli
dotnet run SecretKey="Secret key from command line"
```

<span data-ttu-id="1932c-231">다음 명령은 `/`를 사용하여 키 및 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-231">The following command sets keys and values using `/`:</span></span>

```dotnetcli
dotnet run /SecretKey "Secret key set from forward slash"
```

<span data-ttu-id="1932c-232">다음 명령은 `--`를 사용하여 키 및 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-232">The following command sets keys and values using `--`:</span></span>

```dotnetcli
dotnet run --SecretKey "Secret key set from double hyphen"
```

<span data-ttu-id="1932c-233">키 값은,</span><span class="sxs-lookup"><span data-stu-id="1932c-233">The key value:</span></span>

- <span data-ttu-id="1932c-234">`=` 다음에 와야 합니다. 또는 값이 공백에 다음에 오는 경우 키에 `--` 또는 `/` 접두사가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-234">Must follow `=`, or the key must have a prefix of `--` or `/` when the value follows a space.</span></span>
- <span data-ttu-id="1932c-235">`=`이 사용된 경우 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-235">Isn't required if `=` is used.</span></span> <span data-ttu-id="1932c-236">예: `SomeKey=`.</span><span class="sxs-lookup"><span data-stu-id="1932c-236">For example, `SomeKey=`.</span></span>

<span data-ttu-id="1932c-237">같은 명령 내에서 `=`을 사용하는 명령줄 인수 키-값 쌍을 공백을 사용하는 키-값 쌍과 함께 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1932c-237">Within the same command, don't mix command-line argument key-value pairs that use `=` with key-value pairs that use a space.</span></span>

## <a name="key-per-file-configuration-provider"></a><span data-ttu-id="1932c-238">파일별 키 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-238">Key-per-file configuration provider</span></span>

<span data-ttu-id="1932c-239"><xref:Microsoft.Extensions.Configuration.KeyPerFile.KeyPerFileConfigurationProvider>는 디렉터리의 파일을 구성 키-값 쌍으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-239">The <xref:Microsoft.Extensions.Configuration.KeyPerFile.KeyPerFileConfigurationProvider> uses a directory's files as configuration key-value pairs.</span></span> <span data-ttu-id="1932c-240">키는 파일 이름이고,</span><span class="sxs-lookup"><span data-stu-id="1932c-240">The key is the file name.</span></span> <span data-ttu-id="1932c-241">값은 파일의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-241">The value is the file's contents.</span></span> <span data-ttu-id="1932c-242">파일별 키 구성 공급자는 Docker 호스팅 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-242">The Key-per-file configuration provider is used in Docker hosting scenarios.</span></span>

<span data-ttu-id="1932c-243">파일별 키 구성을 활성화하려면 <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder> 인스턴스에서 <xref:Microsoft.Extensions.Configuration.KeyPerFileConfigurationBuilderExtensions.AddKeyPerFile%2A> 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-243">To activate key-per-file configuration, call the <xref:Microsoft.Extensions.Configuration.KeyPerFileConfigurationBuilderExtensions.AddKeyPerFile%2A> extension method on an instance of <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder>.</span></span> <span data-ttu-id="1932c-244">파일의 `directoryPath`는 절대 경로여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-244">The `directoryPath` to the files must be an absolute path.</span></span>

<span data-ttu-id="1932c-245">오버로드에서는 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-245">Overloads permit specifying:</span></span>

- <span data-ttu-id="1932c-246">소스를 구성하는 `Action<KeyPerFileConfigurationSource>` 대리자</span><span class="sxs-lookup"><span data-stu-id="1932c-246">An `Action<KeyPerFileConfigurationSource>` delegate that configures the source.</span></span>
- <span data-ttu-id="1932c-247">디렉터리가 선택 사항인지 여부와 디렉터리의 경로</span><span class="sxs-lookup"><span data-stu-id="1932c-247">Whether the directory is optional and the path to the directory.</span></span>

<span data-ttu-id="1932c-248">두 개의 밑줄(`__`)은 파일 이름에서 구성 키 구분 기호로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-248">The double-underscore (`__`) is used as a configuration key delimiter in file names.</span></span> <span data-ttu-id="1932c-249">예를 들어, 파일 이름 `Logging__LogLevel__System`은 구성 키 `Logging:LogLevel:System`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-249">For example, the file name `Logging__LogLevel__System` produces the configuration key `Logging:LogLevel:System`.</span></span>

<span data-ttu-id="1932c-250">호스트를 빌드할 때 `ConfigureAppConfiguration`을 호출하여 앱의 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-250">Call `ConfigureAppConfiguration` when building the host to specify the app's configuration:</span></span>

```csharp
.ConfigureAppConfiguration((_, configuration) =>
{
    var path = Path.Combine(
        Directory.GetCurrentDirectory(), "path/to/files");

    configuration.AddKeyPerFile(directoryPath: path, optional: true);
})
```

## <a name="memory-configuration-provider"></a><span data-ttu-id="1932c-251">메모리 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="1932c-251">Memory configuration provider</span></span>

<span data-ttu-id="1932c-252"><xref:Microsoft.Extensions.Configuration.Memory.MemoryConfigurationProvider>는 메모리 내 컬렉션을 구성 키-값 쌍으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-252">The <xref:Microsoft.Extensions.Configuration.Memory.MemoryConfigurationProvider> uses an in-memory collection as configuration key-value pairs.</span></span>

<span data-ttu-id="1932c-253">다음 코드는 구성 시스템에 메모리 컬렉션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-253">The following code adds a memory collection to the configuration system:</span></span>

:::code language="csharp" source="snippets/configuration/console-memory/Program.cs" highlight="22-29":::

<span data-ttu-id="1932c-254">이전 코드에서 <xref:Microsoft.Extensions.Configuration.MemoryConfigurationBuilderExtensions.AddInMemoryCollection(Microsoft.Extensions.Configuration.IConfigurationBuilder,System.Collections.Generic.IEnumerable{System.Collections.Generic.KeyValuePair{System.String,System.String}})?displayProperty=nameWithType>은 기본 구성 공급자 뒤에 메모리 공급자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1932c-254">In the preceding code, <xref:Microsoft.Extensions.Configuration.MemoryConfigurationBuilderExtensions.AddInMemoryCollection(Microsoft.Extensions.Configuration.IConfigurationBuilder,System.Collections.Generic.IEnumerable{System.Collections.Generic.KeyValuePair{System.String,System.String}})?displayProperty=nameWithType> adds the memory provider after the default configuration providers.</span></span> <span data-ttu-id="1932c-255">구성 공급자 순서 지정 예제는 [XML 구성 공급자](#xml-configuration-provider)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1932c-255">For an example of ordering the configuration providers, see [XML configuration provider](#xml-configuration-provider).</span></span>

## <a name="see-also"></a><span data-ttu-id="1932c-256">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1932c-256">See also</span></span>

- [<span data-ttu-id="1932c-257">.NET의 구성</span><span class="sxs-lookup"><span data-stu-id="1932c-257">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="1932c-258">.NET 일반 호스트</span><span class="sxs-lookup"><span data-stu-id="1932c-258">.NET Generic Host</span></span>](generic-host.md)
- [<span data-ttu-id="1932c-259">사용자 지정 구성 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="1932c-259">Implement a custom configuration provider</span></span>](custom-configuration-provider.md)
