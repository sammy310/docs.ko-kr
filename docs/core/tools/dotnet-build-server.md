---
title: dotnet build-server 명령
description: dotnet build-server 명령은 빌드에서 시작된 서버와 상호 작용합니다.
ms.date: 04/24/2019
ms.openlocfilehash: 1c6c6dcdb53d779426daf5daa470d2ad0470a7a1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523018"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="56e0c-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="56e0c-103">dotnet build-server</span></span>

<span data-ttu-id="56e0c-104">**이 문서 적용 대상: ✓** .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="56e0c-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="56e0c-105">name</span><span class="sxs-lookup"><span data-stu-id="56e0c-105">Name</span></span>

<span data-ttu-id="56e0c-106">`dotnet build-server` - 빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="56e0c-107">개요</span><span class="sxs-lookup"><span data-stu-id="56e0c-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="56e0c-108">명령</span><span class="sxs-lookup"><span data-stu-id="56e0c-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="56e0c-109">Dotnet에서 시작된 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="56e0c-110">기본적으로 모든 서버가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="56e0c-111">옵션</span><span class="sxs-lookup"><span data-stu-id="56e0c-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="56e0c-112">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="56e0c-113">MSBuild 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="56e0c-114">Razor 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="56e0c-115">VB/C# 컴파일러 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="56e0c-115">Shuts down the VB/C# compiler build server.</span></span>
