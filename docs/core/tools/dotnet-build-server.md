---
title: dotnet build-server 명령
description: dotnet build-server 명령은 빌드에서 시작된 서버와 상호 작용합니다.
ms.date: 04/24/2019
ms.openlocfilehash: 89d1aba104e2cb07b46766a3768eed68d85a7aa7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117773"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="b338c-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="b338c-103">dotnet build-server</span></span>

<span data-ttu-id="b338c-104">**이 문서 적용 대상: ✓** .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="b338c-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="b338c-105">name</span><span class="sxs-lookup"><span data-stu-id="b338c-105">Name</span></span>

<span data-ttu-id="b338c-106">`dotnet build-server` - 빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b338c-107">개요</span><span class="sxs-lookup"><span data-stu-id="b338c-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="b338c-108">명령</span><span class="sxs-lookup"><span data-stu-id="b338c-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="b338c-109">Dotnet에서 시작된 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="b338c-110">기본적으로 모든 서버가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="b338c-111">옵션</span><span class="sxs-lookup"><span data-stu-id="b338c-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="b338c-112">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="b338c-113">MSBuild 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="b338c-114">Razor 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="b338c-115">VB/C# 컴파일러 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b338c-115">Shuts down the VB/C# compiler build server.</span></span>
