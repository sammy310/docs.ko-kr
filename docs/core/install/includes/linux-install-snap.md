---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602689"
---

[<span data-ttu-id="c6667-101">.NET Core는 Snap 스토어에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="c6667-102">Snap은 다양한 Linux 배포판에서 수정하지 않고도 작동하는 앱의 번들이자 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="c6667-103">Snap은 Snap 스토어에서 검색해서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="c6667-104">Snap에 대한 자세한 내용은 [Snap 시작하기](https://snapcraft.io/docs/getting-started)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6667-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="c6667-105">지원되는 버전의 .NET Core만 Snap을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="c6667-106">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="c6667-106">Install the SDK</span></span>

<span data-ttu-id="c6667-107">.NET Core SDK에 대한 맞춤 패키지는 모두 동일한 식별자인 `dotnet-sdk`로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-107">Snap packages for .NET Core SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="c6667-108">특정 버전의 SDK는 채널을 지정하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="c6667-109">SDK에는 해당 런타임이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="c6667-110">다음 표에는 채널이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-110">The following table list the channels:</span></span>

| <span data-ttu-id="c6667-111">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="c6667-111">.NET Core version</span></span> | <span data-ttu-id="c6667-112">맞춤 패키지</span><span class="sxs-lookup"><span data-stu-id="c6667-112">Snap package</span></span>             |
|-------------------|--------------------------|
| <span data-ttu-id="c6667-113">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="c6667-113">3.1 (LTS)</span></span>         | <span data-ttu-id="c6667-114">`3.1` 또는 `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="c6667-114">`3.1` or `latest/stable`</span></span> |
| <span data-ttu-id="c6667-115">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="c6667-115">2.1 (LTS)</span></span>         | `2.1`                    |
| <span data-ttu-id="c6667-116">.NET 5.0 미리보기</span><span class="sxs-lookup"><span data-stu-id="c6667-116">.NET 5.0 preview</span></span>  | `5.0/beta`               |

<span data-ttu-id="c6667-117">`snap install` 명령을 사용하여 .NET Core SDK 맞춤 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-117">Use the `snap install` command to install a .NET Core SDK snap package.</span></span> <span data-ttu-id="c6667-118">`--channel` 매개 변수를 사용하여 설치할 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-118">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="c6667-119">이 매개 변수를 생략하면 `latest/stable`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-119">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="c6667-120">이 예에서는 `3.1`이 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-120">In this example, `3.1` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

<span data-ttu-id="c6667-121">다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-121">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="c6667-122">이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-122">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="c6667-123">원하는 `{alias}` 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-123">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="c6667-124">예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-sdk.dotnet dotnet31`).</span><span class="sxs-lookup"><span data-stu-id="c6667-124">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span></span> <span data-ttu-id="c6667-125">`dotnet31` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-125">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="c6667-126">그러나, 이는 `dotnet` 명령에서 기대하는 바와 같이 대부분의 자습서와 예시에서는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-126">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="c6667-127">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="c6667-127">Install the runtime</span></span>

<span data-ttu-id="c6667-128">.NET Core 런타임에 대한 맞춤 패키지는 각각 자체 패키지 식별자에 따라 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-128">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="c6667-129">다음 표에는 패키지 식별자가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-129">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="c6667-130">.NET Core 버전</span><span class="sxs-lookup"><span data-stu-id="c6667-130">.NET Core version</span></span> | <span data-ttu-id="c6667-131">맞춤 패키지</span><span class="sxs-lookup"><span data-stu-id="c6667-131">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="c6667-132">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="c6667-132">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="c6667-133">3.0</span><span class="sxs-lookup"><span data-stu-id="c6667-133">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="c6667-134">2.2</span><span class="sxs-lookup"><span data-stu-id="c6667-134">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="c6667-135">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="c6667-135">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="c6667-136">`snap install` 명령을 사용하여 .NET Core 런타임 맞춤 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-136">Use the `snap install` command to install a .NET Core Runtime snap package.</span></span> <span data-ttu-id="c6667-137">이 예에서는 .NET Core 3.1이 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-137">In this example, .NET Core 3.1 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-31 --classic
```

<span data-ttu-id="c6667-138">다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-138">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

<span data-ttu-id="c6667-139">이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-139">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="c6667-140">원하는 `{alias}` 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-140">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="c6667-141">예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`).</span><span class="sxs-lookup"><span data-stu-id="c6667-141">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span></span> <span data-ttu-id="c6667-142">`dotnet31` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-142">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="c6667-143">그러나, 이는 `dotnet` 명령에서 기대하는 바와 같이 대부분의 자습서와 예시에서는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-143">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="c6667-144">SSL 인증서 오류</span><span class="sxs-lookup"><span data-stu-id="c6667-144">SSL Certificate errors</span></span>

<span data-ttu-id="c6667-145">Snap을 통해 .NET가 설치될 경우, 일부 배포판에서는 .NET SSL 인증서를 찾을 수 없고 `restore` 도중에 다음과 유사한 오류를 받게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-145">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="c6667-146">이 문제를 해결하려면 다음과 같은 몇 가지 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-146">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="c6667-147">인증서 위치는 배포판에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-147">The certificate location will vary by distro.</span></span> <span data-ttu-id="c6667-148">문제가 발생한 배포판의 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6667-148">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="c6667-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="c6667-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="c6667-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="c6667-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="c6667-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="c6667-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
