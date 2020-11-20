---
ms.openlocfilehash: 4ab2fc0645f76870dead99b5f45eef763643fb27
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506903"
---

[<span data-ttu-id="a3402-101">.NET Core는 Snap 스토어에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="a3402-102">Snap은 다양한 Linux 배포판에서 수정하지 않고도 작동하는 앱의 번들이자 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="a3402-103">Snap은 Snap 스토어에서 검색해서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="a3402-104">Snap에 대한 자세한 내용은 [Snap 시작하기](https://snapcraft.io/docs/getting-started)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3402-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="a3402-105">지원되는 버전의 .NET Core만 Snap을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="a3402-106">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="a3402-106">Install the SDK</span></span>

<span data-ttu-id="a3402-107">.NET SDK용 스냅 패키지는 모두 동일한 식별자 `dotnet-sdk`로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-107">Snap packages for .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="a3402-108">특정 버전의 SDK는 채널을 지정하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="a3402-109">SDK에는 해당 런타임이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="a3402-110">다음 표에는 채널이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-110">The following table list the channels:</span></span>

| <span data-ttu-id="a3402-111">.NET 버전</span><span class="sxs-lookup"><span data-stu-id="a3402-111">.NET version</span></span> | <span data-ttu-id="a3402-112">맞춤 패키지</span><span class="sxs-lookup"><span data-stu-id="a3402-112">Snap package</span></span>             |
|--------------|--------------------------|
| <span data-ttu-id="a3402-113">5.0</span><span class="sxs-lookup"><span data-stu-id="a3402-113">5.0</span></span>          | <span data-ttu-id="a3402-114">`5.0` 또는 `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="a3402-114">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="a3402-115">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="a3402-115">3.1 (LTS)</span></span>    | <span data-ttu-id="a3402-116">`3.1` 또는 `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="a3402-116">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="a3402-117">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="a3402-117">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="a3402-118">`snap install` 명령을 사용하여 .NET SDK 스냅 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-118">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="a3402-119">`--channel` 매개 변수를 사용하여 설치할 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-119">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="a3402-120">이 매개 변수를 생략하면 `latest/stable`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-120">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="a3402-121">이 예에서는 `5.0`이 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-121">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="a3402-122">다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-122">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="a3402-123">이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-123">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="a3402-124">원하는 `{alias}` 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-124">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="a3402-125">예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-sdk.dotnet dotnet50`).</span><span class="sxs-lookup"><span data-stu-id="a3402-125">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="a3402-126">`dotnet50` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-126">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="a3402-127">그러나, 이는 `dotnet` 명령에서 기대하는 바와 같이 대부분의 자습서와 예시에서는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-127">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="a3402-128">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="a3402-128">Install the runtime</span></span>

<span data-ttu-id="a3402-129">.NET Core 런타임에 대한 맞춤 패키지는 각각 자체 패키지 식별자에 따라 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-129">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="a3402-130">다음 표에는 패키지 식별자가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-130">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="a3402-131">.NET 버전</span><span class="sxs-lookup"><span data-stu-id="a3402-131">.NET version</span></span>      | <span data-ttu-id="a3402-132">맞춤 패키지</span><span class="sxs-lookup"><span data-stu-id="a3402-132">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="a3402-133">5.0</span><span class="sxs-lookup"><span data-stu-id="a3402-133">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="a3402-134">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="a3402-134">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="a3402-135">3.0</span><span class="sxs-lookup"><span data-stu-id="a3402-135">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="a3402-136">2.2</span><span class="sxs-lookup"><span data-stu-id="a3402-136">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="a3402-137">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="a3402-137">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="a3402-138">`snap install` 명령을 사용하여 .NET 런타임 스냅 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-138">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="a3402-139">이 예제에서는 .NET 5.0이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-139">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="a3402-140">다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-140">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="a3402-141">이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-141">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="a3402-142">원하는 `{alias}` 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-142">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="a3402-143">예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`).</span><span class="sxs-lookup"><span data-stu-id="a3402-143">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="a3402-144">`dotnet50` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-144">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="a3402-145">그러나, 이는 `dotnet` 명령에서 기대하는 바와 같이 대부분의 자습서와 예시에서는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-145">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="a3402-146">SSL 인증서 오류</span><span class="sxs-lookup"><span data-stu-id="a3402-146">SSL Certificate errors</span></span>

<span data-ttu-id="a3402-147">Snap을 통해 .NET가 설치될 경우, 일부 배포판에서는 .NET SSL 인증서를 찾을 수 없고 `restore` 도중에 다음과 유사한 오류를 받게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-147">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="a3402-148">이 문제를 해결하려면 다음과 같은 몇 가지 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-148">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="a3402-149">인증서 위치는 배포판에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-149">The certificate location will vary by distro.</span></span> <span data-ttu-id="a3402-150">문제가 발생한 배포판의 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3402-150">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="a3402-151">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="a3402-151">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="a3402-152">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="a3402-152">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="a3402-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="a3402-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
