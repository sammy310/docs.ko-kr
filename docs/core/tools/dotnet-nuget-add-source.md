---
title: dotnet nuget add source 명령
description: dotnet nuget add source 명령은 NuGet 구성 파일에 새 패키지 소스를 추가합니다.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148491"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="50e7f-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="50e7f-103">dotnet nuget add source</span></span>

<span data-ttu-id="50e7f-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="50e7f-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="50e7f-105">속성</span><span class="sxs-lookup"><span data-stu-id="50e7f-105">Name</span></span>

<span data-ttu-id="50e7f-106">`dotnet nuget add source` - NuGet 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="50e7f-107">개요</span><span class="sxs-lookup"><span data-stu-id="50e7f-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="50e7f-108">Description</span><span class="sxs-lookup"><span data-stu-id="50e7f-108">Description</span></span>

<span data-ttu-id="50e7f-109">`dotnet nuget add source` 명령은 NuGet 구성 파일에 새 패키지 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="50e7f-110">인수</span><span class="sxs-lookup"><span data-stu-id="50e7f-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="50e7f-111">패키지 소스의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="50e7f-112">옵션</span><span class="sxs-lookup"><span data-stu-id="50e7f-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="50e7f-113">NuGet 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-113">The NuGet configuration file.</span></span> <span data-ttu-id="50e7f-114">지정된 경우 이 파일의 설정만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="50e7f-115">지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="50e7f-116">자세한 내용은 [일반적인 NuGet 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50e7f-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name`**

  <span data-ttu-id="50e7f-117">소스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-117">Name of the source.</span></span>

- **`-p|--password`**

  <span data-ttu-id="50e7f-118">인증된 소스에 연결할 때 사용할 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="50e7f-119">암호 암호화를 사용하지 않도록 설정하여 이식 가능한 패키지 소스 자격 증명을 저장할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="50e7f-120">인증된 소스에 연결할 때 사용할 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="50e7f-121">이 소스에 대한 유효한 인증 형식의 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="50e7f-122">서버에서 NTLM 또는 Negotiate를 보급하고 기본 메커니즘을 사용하여 자격 증명을 전송해야 하는 경우(예를 들어 온-프레미스 Azure DevOps Server에서 PAT를 사용하는 경우) `basic`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="50e7f-123">다른 유효한 값은 `negotiate`, `kerberos`, `ntlm` 및 `digest`이지만 이러한 값은 유용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="50e7f-124">예</span><span class="sxs-lookup"><span data-stu-id="50e7f-124">Examples</span></span>

- <span data-ttu-id="50e7f-125">`nuget.org`를 소스로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="50e7f-126">`c:\packages`를 로컬 소스로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="50e7f-127">인증이 필요한 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="50e7f-128">인증이 필요한 소스를 추가한 다음 자격 증명 공급자를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="50e7f-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="50e7f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50e7f-129">See also</span></span>

- [<span data-ttu-id="50e7f-130">NuGet.config 파일의 패키지 소스 섹션</span><span class="sxs-lookup"><span data-stu-id="50e7f-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="50e7f-131">소스 명령(nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="50e7f-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
