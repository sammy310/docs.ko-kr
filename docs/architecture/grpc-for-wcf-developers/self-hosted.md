---
title: 자체 호스팅 gRPC 응용 프로그램 - WCF 개발자를 위한 gRPC
description: ASP.NET 코어 gRPC 애플리케이션을 자체 호스팅 서비스로 배포합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147804"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="1aad0-103">자체 호스팅 gRPC 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1aad0-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="1aad0-104">ASP.NET Core 3.0 응용 프로그램은 Windows Server의 IIS에서 호스팅할 수 있지만 현재 는 일부 HTTP/2 기능이 지원되지 않으므로 IIS에서 gRPC 응용 프로그램을 호스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="1aad0-105">이 기능은 Windows Server에 대한 향후 업데이트의 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="1aad0-106">응용 프로그램을 Windows 서비스로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="1aad0-107">또는 .NET Core 3.0 호스팅 확장의 새로운 기능으로 인해 [systemd에](https://en.wikipedia.org/wiki/Systemd)의해 제어되는 Linux 서비스로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="1aad0-108">Windows 서비스로 앱 실행</span><span class="sxs-lookup"><span data-stu-id="1aad0-108">Run your app as a Windows service</span></span>

<span data-ttu-id="1aad0-109">ASP.NET 핵심 응용 프로그램을 Windows 서비스로 실행하도록 구성하려면 NuGet에서 [Microsoft.Extensions.Hosting.WindowsServices 패키지를 설치합니다.](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)</span><span class="sxs-lookup"><span data-stu-id="1aad0-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="1aad0-110">그런 다음 에서 `UseWindowsService` 메서드에 대한 호출을 `CreateHostBuilder` 추가합니다. `Program.cs`</span><span class="sxs-lookup"><span data-stu-id="1aad0-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="1aad0-111">응용 프로그램이 Windows 서비스로 실행되지 않는 `UseWindowsService` 경우 메서드는 아무 것도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="1aad0-112">이제 다음 방법 중 하나를 사용하여 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="1aad0-113">프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **게시를** 선택하여 Visual Studio에서.</span><span class="sxs-lookup"><span data-stu-id="1aad0-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="1aad0-114">.NET 코어 CLI에서.</span><span class="sxs-lookup"><span data-stu-id="1aad0-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="1aad0-115">.NET Core 응용 프로그램을 게시할 때 *프레임워크 종속* 배포 또는 *독립형* 배포를 만들도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="1aad0-116">프레임워크 종속 배포에서는 .NET Core 공유 런타임을 실행되는 호스트에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="1aad0-117">독립형 배포는 .NET Core 런타임 및 프레임워크의 전체 복사본과 함께 게시되며 모든 호스트에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="1aad0-118">각 접근 방식의 장점과 단점을 포함하여 자세한 내용은 [.NET Core 응용 프로그램 배포](../../core/deploying/index.md) 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1aad0-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="1aad0-119">.NET Core 3.0 런타임을 호스트에 설치할 필요가 없는 독립형 응용 프로그램 빌드를 게시하려면 응용 프로그램에 포함할 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="1aad0-120">(또는) `-r` `--runtime`플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="1aad0-121">프레임워크 종속 빌드를 게시하려면 플래그를 생략합니다. `-r`</span><span class="sxs-lookup"><span data-stu-id="1aad0-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="1aad0-122">`publish` 디렉터리 전체 내용을 설치 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="1aad0-123">그런 다음 [sc 도구를](/windows/desktop/services/controlling-a-service-using-sc) 사용하여 실행 파일에 대한 Windows 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="1aad0-124">Windows 이벤트 로그에 로그</span><span class="sxs-lookup"><span data-stu-id="1aad0-124">Log to the Windows event log</span></span>

<span data-ttu-id="1aad0-125">메서드는 `UseWindowsService` Windows 이벤트 로그에 로그 메시지를 쓰는 [로깅](/aspnet/core/fundamentals/logging/) 공급자를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="1aad0-126">이 공급자의 섹션 `EventLog` `Logging` `appsettings.json` 또는 다른 구성 원본에 항목을 추가하여 이 공급자에 대한 로깅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="1aad0-127">이러한 설정에서 속성을 설정하여 이벤트 로그에 `SourceName` 사용된 소스 이름을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="1aad0-128">이름을 지정하지 않으면 기본 응용 프로그램 이름(일반적으로 실행 가능한 어셈블리 이름)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="1aad0-129">로깅에 대한 자세한 내용은 이 장의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="1aad0-130">systemd를 통해 Linux 서비스로 앱을 실행</span><span class="sxs-lookup"><span data-stu-id="1aad0-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="1aad0-131">리눅스 서비스 (또는 리눅스 용어의 *데몬)로* 실행하도록 ASP.NET 코어 응용 프로그램을 구성하려면 NuGet에서 [Microsoft.Extensions.Hostings.Systemd 패키지를 설치합니다.](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)</span><span class="sxs-lookup"><span data-stu-id="1aad0-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="1aad0-132">그런 다음 에서 `UseSystemd` 메서드에 대한 호출을 `CreateHostBuilder` 추가합니다. `Program.cs`</span><span class="sxs-lookup"><span data-stu-id="1aad0-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="1aad0-133">응용 프로그램이 Linux 서비스로 실행되지 않는 `UseSystemd` 경우 메서드는 아무 것도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="1aad0-134">이제 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-134">Now publish your application.</span></span> <span data-ttu-id="1aad0-135">응용 프로그램은 관련 Linux 런타임(예: `linux-x64`)에 대해 프레임워크에 종속되거나 자체 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="1aad0-136">다음 방법 중 하나를 사용하여 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="1aad0-137">프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **게시를** 선택하여 Visual Studio에서.</span><span class="sxs-lookup"><span data-stu-id="1aad0-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="1aad0-138">.NET 코어 CLI에서 다음 명령을 사용하여 다음 명령을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="1aad0-139">`publish` 디렉터리 전체 내용을 Linux 호스트의 설치 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="1aad0-140">서비스를 등록하려면 디렉터리에 단위 파일이라는 특수 *파일이* `/etc/systemd/system` 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="1aad0-141">이 폴더에서 파일을 만들려면 루트 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="1aad0-142">사용할 식별자와 `systemd` 확장자를 사용하여 파일의 `.service` 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="1aad0-143">예를 들면 `/etc/systemd/system/myapp.service`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="1aad0-144">서비스 파일은 이 예제와 같이 INI 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="1aad0-145">속성은 `Type=notify` `systemd` 응용 프로그램이 시작 및 종료시 이를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="1aad0-146">이 `WantedBy=multi-user.target` 설정은 Linux 시스템이 "런레벨 2"에 도달하면 서비스가 시작되며, 이는 그래픽이 아닌 다중 사용자 셸이 활성화되어 있다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="1aad0-147">서비스를 `systemd` 인식하기 전에 구성을 다시 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="1aad0-148">명령을 `systemd` 사용하여 제어합니다. `systemctl`</span><span class="sxs-lookup"><span data-stu-id="1aad0-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="1aad0-149">다시 로드한 후 `status` 하위 명령을 사용하여 응용 프로그램이 성공적으로 등록되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="1aad0-150">서비스를 올바르게 구성한 경우 다음과 같은 출력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="1aad0-151">`start` 명령을 사용하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="1aad0-152">`.service` 을 사용할 `systemctl start`때 확장은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="1aad0-153">시스템 `systemd` 시작 시 서비스를 자동으로 시작하도록 지시하려면 `enable` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="1aad0-154">저널로 로그</span><span class="sxs-lookup"><span data-stu-id="1aad0-154">Log to journald</span></span>

<span data-ttu-id="1aad0-155">Windows 이벤트 로그에 해당하는 `journald`Linux는 `systemd`의 일부인 구조화 된 로깅 시스템 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="1aad0-156">Linux 데몬의 표준 출력에 기록된 로그 `journald`메시지는 에 자동으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="1aad0-157">로깅 수준을 구성하려면 `Console` 로깅 구성의 섹션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="1aad0-158">호스트 `UseSystemd` 빌더 메서드는 저널에 맞게 콘솔 출력 형식을 자동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="1aad0-159">리눅스 로그의 표준이기 때문에 `journald` 다양한 도구가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="1aad0-160">로그를 외부 로깅 `journald` 시스템으로 쉽게 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="1aad0-161">호스트에서 로컬로 작업하면 `journalctl` 명령을 사용하여 명령줄에서 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="1aad0-162">호스트에서 사용할 수 있는 GUI 환경이 있는 경우 *QJournalctl* 및 *그놈 로그와*같은 몇 가지 그래픽 로그 뷰어를 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="1aad0-163">명령줄에서 `systemd` 저널을 쿼리하는 `journalctl`방법에 대해 자세히 알아보려면 man [페이지를](https://manpages.debian.org/buster/systemd/journalctl.1)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1aad0-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="1aad0-164">자체 호스팅 응용 프로그램에 대한 HTTPS 인증서</span><span class="sxs-lookup"><span data-stu-id="1aad0-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="1aad0-165">프로덕션 환경에서 gRPC 응용 프로그램을 실행하는 경우 신뢰할 수 있는 인증 기관(CA)의 TLS 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="1aad0-166">이 CA는 공용 CA이거나 조직의 내부 CA일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="1aad0-167">Windows 호스트에서 클래스를 사용하여 보안 [인증서 저장소에서](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) <xref:System.Security.Cryptography.X509Certificates.X509Store> 인증서를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="1aad0-168">일부 Linux 호스트에서 `X509Store` OpenSSL 키 저장소에서 클래스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="1aad0-169">다음 중 하나에서 [X509Certificate2 생성자](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)중 하나를 사용하여 인증서를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="1aad0-170">강력한 암호로 보호되는 `.pfx` 파일과 같은 파일</span><span class="sxs-lookup"><span data-stu-id="1aad0-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="1aad0-171">[Azure 키 볼트와](https://azure.microsoft.com/services/key-vault/) 같은 보안 저장소 서비스에서 검색된 이진 데이터</span><span class="sxs-lookup"><span data-stu-id="1aad0-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="1aad0-172">Kestrel은 구성 또는 코드의 두 가지 방법으로 인증서를 사용하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="1aad0-173">구성을 사용하여 HTTPS 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="1aad0-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="1aad0-174">구성 접근 방식을 사용하려면 Kestrel 구성 섹션의 인증서 `.pfx` 파일 및 암호에 대한 경로를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="1aad0-175">에서 `appsettings.json`다음과 같이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-175">In `appsettings.json`, that would look like this:</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="1aad0-176">Azure 키 볼트 또는 Hashicorp 볼트와 같은 보안 구성 원본을 사용하여 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1aad0-177">암호화되지 않은 암호를 구성 파일에 저장하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1aad0-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="1aad0-178">코드에서 HTTPS 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="1aad0-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="1aad0-179">코드에서 Kestrel에서 HTTPS를 구성하려면 `ConfigureKestrel` `IWebHostBuilder` `Program` 클래스에서 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="1aad0-180">다시 `.pfx` 말하지만, 파일에 대한 암호를 저장하고 보안 구성 소스에서 검색해야합니다.</span><span class="sxs-lookup"><span data-stu-id="1aad0-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1aad0-181">[이전](grpc-in-production.md)
>[다음](docker.md)</span><span class="sxs-lookup"><span data-stu-id="1aad0-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
