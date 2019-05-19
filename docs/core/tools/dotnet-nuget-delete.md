---
title: dotnet nuget delete 명령
description: dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: e1362413aa6458674518d68340634741994b34a3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632052"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="730eb-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="730eb-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="730eb-104">name</span><span class="sxs-lookup"><span data-stu-id="730eb-104">Name</span></span>

<span data-ttu-id="730eb-105">`dotnet nuget delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="730eb-106">개요</span><span class="sxs-lookup"><span data-stu-id="730eb-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="730eb-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="730eb-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="730eb-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="730eb-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="730eb-109">설명</span><span class="sxs-lookup"><span data-stu-id="730eb-109">Description</span></span>

<span data-ttu-id="730eb-110">`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="730eb-111">[nuget.org](https://www.nuget.org/)의 경우 작업을 통해 패키지가 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="730eb-112">인수</span><span class="sxs-lookup"><span data-stu-id="730eb-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="730eb-113">삭제할 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="730eb-114">삭제할 패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="730eb-115">옵션</span><span class="sxs-lookup"><span data-stu-id="730eb-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="730eb-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="730eb-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="730eb-117">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="730eb-118">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="730eb-119">명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="730eb-120">.NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="730eb-121">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="730eb-122">소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="730eb-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="730eb-123">.NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="730eb-124">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="730eb-125">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-125">Specifies the server URL.</span></span> <span data-ttu-id="730eb-126">nuget.org에 대해 지원되는 URL에는 `https://www.nuget.org`, `https://www.nuget.org/api/v3` 및 `https://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="730eb-127">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="730eb-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="730eb-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="730eb-129">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="730eb-130">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="730eb-131">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="730eb-132">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="730eb-133">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-133">Specifies the server URL.</span></span> <span data-ttu-id="730eb-134">nuget.org에 대해 지원되는 URL에는 `https://www.nuget.org`, `https://www.nuget.org/api/v3` 및 `https://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="730eb-135">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="730eb-136">예제</span><span class="sxs-lookup"><span data-stu-id="730eb-136">Examples</span></span>

* <span data-ttu-id="730eb-137">`Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="730eb-138">사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="730eb-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
