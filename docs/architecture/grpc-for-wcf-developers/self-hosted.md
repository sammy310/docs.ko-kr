---
title: 자체 호스팅 gRPC 응용 프로그램-WCF 개발자를 위한 gRPC
description: ASP.NET Core gRPC 응용 프로그램을 자체 호스팅 서비스로 배포 합니다.
ms.date: 12/15/2020
ms.openlocfilehash: a5e2316b8d76593f4eb53760d2609b5bbbc9d2c5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938535"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="24d6b-103">자체 호스팅 gRPC 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="24d6b-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="24d6b-104">ASP.NET Core 5.0 응용 프로그램은 Windows Server의 IIS에서 호스팅될 수 있지만 현재는 HTTP/2 기능이 지원 되지 않기 때문에 IIS에서 gRPC 응용 프로그램을 호스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-104">Although ASP.NET Core 5.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="24d6b-105">이 기능은 향후 Windows Server 업데이트에 대 한 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="24d6b-106">Windows 서비스로 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="24d6b-107">또는 .NET 5.0 호스팅 확장의 새로운 기능으로 인해 [systemd](https://en.wikipedia.org/wiki/Systemd)로 제어 되는 Linux 서비스로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET 5.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="24d6b-108">Windows 서비스로 앱 실행</span><span class="sxs-lookup"><span data-stu-id="24d6b-108">Run your app as a Windows service</span></span>

<span data-ttu-id="24d6b-109">ASP.NET Core 응용 프로그램을 Windows 서비스로 실행 하도록 구성 하려면 NuGet에서 [Microsoft.](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) i n s o r e r. r e r. r e r. r e r. r e s</span><span class="sxs-lookup"><span data-stu-id="24d6b-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="24d6b-110">그런 다음에 대 한 호출을 `UseWindowsService` `CreateHostBuilder` 의 메서드에 추가 `Program.cs` 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="24d6b-111">응용 프로그램이 Windows 서비스로 실행 되지 않는 경우 `UseWindowsService` 메서드는 아무것도 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="24d6b-112">이제 다음 방법 중 하나를 사용 하 여 응용 프로그램을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="24d6b-113">Visual Studio에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **게시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="24d6b-114">.NET CLI에서.</span><span class="sxs-lookup"><span data-stu-id="24d6b-114">From the .NET CLI.</span></span>

<span data-ttu-id="24d6b-115">.NET 응용 프로그램을 게시할 때 *프레임 워크 종속* 배포 또는 *자체 포함* 배포를 만들도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-115">When you publish a .NET application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="24d6b-116">프레임 워크 종속 배포에는 .NET 공유 런타임이 실행 되는 호스트에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-116">Framework-dependent deployments require the .NET Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="24d6b-117">자체 포함 배포는 전체 .NET 런타임 및 프레임 워크 복사본으로 게시 되며 모든 호스트에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-117">Self-contained deployments are published with a complete copy of the .NET runtime and framework and can be run on any host.</span></span> <span data-ttu-id="24d6b-118">각 방법의 장점과 단점을 비롯 한 자세한 내용은 [.net 응용 프로그램 배포](../../core/deploying/index.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24d6b-118">For more information, including the advantages and disadvantages of each approach, see the [.NET application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="24d6b-119">호스트에 .NET 5.0 런타임을 설치 하지 않아도 되는 자체 포함 된 응용 프로그램 빌드를 게시 하려면 응용 프로그램에 포함 될 런타임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-119">To publish a self-contained build of the application that does not require the .NET 5.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="24d6b-120">`-r`(또는 `--runtime` ) 플래그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="24d6b-121">프레임 워크 종속 빌드를 게시 하려면 플래그를 생략 `-r` 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="24d6b-122">`publish`설치 폴더에 디렉터리의 전체 내용을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="24d6b-123">그런 다음 [sc 도구](/windows/desktop/services/controlling-a-service-using-sc) 를 사용 하 여 실행 파일에 대 한 Windows 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="24d6b-124">Windows 이벤트 로그에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-124">Log to the Windows event log</span></span>

<span data-ttu-id="24d6b-125">`UseWindowsService`메서드는 로그 메시지를 Windows 이벤트 로그에 기록 하는 [로깅](/aspnet/core/fundamentals/logging/) 공급자를 자동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="24d6b-126">`EventLog` `Logging` 또는 다른 구성 소스 섹션에 항목을 추가 하 여이 공급자에 대 한 로깅을 구성할 수 있습니다 `appsettings.json` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="24d6b-127">이러한 설정에서 속성을 설정 하 여 이벤트 로그에 사용 되는 소스 이름을 재정의할 수 있습니다 `SourceName` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="24d6b-128">이름을 지정 하지 않으면 기본 응용 프로그램 이름 (일반적으로 실행 가능한 어셈블리 이름)이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="24d6b-129">로깅에 대 한 자세한 내용은이 챕터의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="24d6b-130">Systemd를 사용 하 여 앱을 Linux 서비스로 실행</span><span class="sxs-lookup"><span data-stu-id="24d6b-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="24d6b-131">ASP.NET Core 응용 프로그램이 Linux 서비스 (또는 Linux 용어의 *디먼* )로 실행 되도록 구성 하려면 NuGet에서 [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="24d6b-132">그런 다음에 대 한 호출을 `UseSystemd` `CreateHostBuilder` 의 메서드에 추가 `Program.cs` 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="24d6b-133">응용 프로그램이 Linux 서비스로 실행 되지 않는 경우 `UseSystemd` 메서드는 아무것도 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="24d6b-134">이제 응용 프로그램을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-134">Now publish your application.</span></span> <span data-ttu-id="24d6b-135">응용 프로그램은 프레임 워크에 종속 되어 있거나 관련 Linux 런타임에 자체 포함 될 수 있습니다 (예: `linux-x64` ).</span><span class="sxs-lookup"><span data-stu-id="24d6b-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="24d6b-136">다음 방법 중 하나를 사용 하 여 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="24d6b-137">Visual Studio에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **게시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="24d6b-138">.NET CLI에서 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-138">From the .NET CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="24d6b-139">디렉터리의 전체 내용을 `publish` Linux 호스트의 설치 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="24d6b-140">서비스를 등록 하려면 디렉터리에 추가할 *단위 파일* 이라는 특수 파일이 필요 합니다 `/etc/systemd/system` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="24d6b-141">이 폴더에 파일을 만들려면 루트 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="24d6b-142">사용할 식별자와 확장명을 사용 하 여 파일의 이름을로 바꿉니다 `systemd` `.service` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="24d6b-143">예를 들면 `/etc/systemd/system/myapp.service`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="24d6b-144">이 예에 표시 된 것 처럼 서비스 파일에는 INI 형식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="24d6b-145">`Type=notify`속성은 `systemd` 응용 프로그램에서 시작 및 종료 시 알리도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="24d6b-146">이 `WantedBy=multi-user.target` 설정은 Linux 시스템이 "실행 수준 2"에 도달 하면 서비스가 시작 되도록 합니다. 즉, 그래픽이 아닌 다중 사용자 셸이 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical, multi-user shell is active.</span></span>

<span data-ttu-id="24d6b-147">에서 `systemd` 서비스를 인식 하기 전에 구성을 다시 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="24d6b-148">`systemd`명령을 사용 하 여를 제어 `systemctl` 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="24d6b-149">다시 로드 한 후에는 `status` 하위 명령을 사용 하 여 응용 프로그램이 성공적으로 등록 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="24d6b-150">서비스를 올바르게 구성한 경우 다음과 같은 출력을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="24d6b-151">명령을 사용 `start` 하 여 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="24d6b-152">을 `.service` 사용 하는 경우 확장은 선택 사항입니다 `systemctl start` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="24d6b-153">`systemd`시스템 시작 시 자동으로 서비스를 시작 하도록 지시 하려면 명령을 사용 `enable` 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="24d6b-154">Journald에 로그</span><span class="sxs-lookup"><span data-stu-id="24d6b-154">Log to journald</span></span>

<span data-ttu-id="24d6b-155">Windows 이벤트 로그에 해당 하는 Linux는 `journald` 의 일부인 구조적 로깅 시스템 서비스입니다 `systemd` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="24d6b-156">Linux 데몬에 의해 표준 출력에 기록 된 로그 메시지는 자동으로에 기록 됩니다 `journald` .</span><span class="sxs-lookup"><span data-stu-id="24d6b-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="24d6b-157">로깅 수준을 구성 하려면 `Console` 로깅 구성의 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="24d6b-158">`UseSystemd`호스트 빌더 메서드는 저널에 맞게 콘솔 출력 형식을 자동으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="24d6b-159">`journald`는 Linux 로그의 표준 이기 때문에 다양 한 도구를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="24d6b-160">에서 `journald` 외부 로깅 시스템으로 로그를 쉽게 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="24d6b-161">호스트에서 로컬로 작업 하는 경우 명령을 사용 하 여 명령줄 `journalctl` 에서 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="24d6b-162">호스트에서 사용할 수 있는 GUI 환경이 있는 경우 *QJournalctl* 및 *gnome* 와 같은 몇 가지 그래픽 로그 뷰어를 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="24d6b-163">를 사용 하 여 명령줄에서 저널을 쿼리 하는 방법에 대 한 자세한 내용은 `systemd` `journalctl` 참조 [페이지](https://manpages.debian.org/buster/systemd/journalctl.1)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24d6b-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="24d6b-164">자체 호스팅 응용 프로그램에 대 한 HTTPS 인증서</span><span class="sxs-lookup"><span data-stu-id="24d6b-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="24d6b-165">프로덕션 환경에서 gRPC 응용 프로그램을 실행 하는 경우 신뢰할 수 있는 CA (인증 기관)의 TLS 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="24d6b-166">이 CA는 공용 CA 또는 조직에 대 한 내부 ca 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="24d6b-167">Windows 호스트에서는 클래스를 사용 하 여 보안 [인증서 저장소](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) 에서 인증서를 로드할 수 있습니다 <xref:System.Security.Cryptography.X509Certificates.X509Store> .</span><span class="sxs-lookup"><span data-stu-id="24d6b-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="24d6b-168">또한 `X509Store` 일부 Linux 호스트에서 OpenSSL 키 저장소와 함께 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="24d6b-169">[X509Certificate2 생성자](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)중 하나를 사용 하 여 다음과 같은 방법으로 인증서를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="24d6b-170">파일 (예: `.pfx` 강력한 암호로 보호 되는 파일)</span><span class="sxs-lookup"><span data-stu-id="24d6b-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="24d6b-171">[Azure Key Vault](https://azure.microsoft.com/services/key-vault/) 와 같은 보안 저장소 서비스에서 검색 된 이진 데이터</span><span class="sxs-lookup"><span data-stu-id="24d6b-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="24d6b-172">구성 또는 코드에서와 같은 두 가지 방법으로 인증서를 사용 하도록 Kestrel을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="24d6b-173">구성을 사용 하 여 HTTPS 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="24d6b-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="24d6b-174">구성 방법에서는 `.pfx` Kestrel 구성 섹션에서 인증서 파일의 경로와 암호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="24d6b-175">에서 `appsettings.json` 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="24d6b-176">Azure Key Vault 또는 Hashicorp Vault와 같은 보안 구성 원본을 사용 하 여 암호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24d6b-177">암호화 되지 않은 암호를 구성 파일에 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="24d6b-178">코드에서 HTTPS 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="24d6b-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="24d6b-179">코드에서 Kestrel에 HTTPS를 구성 하려면 `ConfigureKestrel` 클래스의에서 메서드를 사용 `IWebHostBuilder` `Program` 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="24d6b-180">다시, 보안 구성 원본에서 파일의 암호를 저장 하 `.pfx` 고 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24d6b-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="24d6b-181">[이전](grpc-in-production.md)
>[다음](docker.md)</span><span class="sxs-lookup"><span data-stu-id="24d6b-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
