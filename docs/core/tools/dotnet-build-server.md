---
title: dotnet build-server 명령
description: dotnet build-server 명령은 빌드에서 시작된 서버와 상호 작용합니다.
ms.date: 04/24/2019
ms.openlocfilehash: 491ac37e7f75f930423b3c7e43e3c090ec1ed07d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754283"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="70dfa-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="70dfa-103">dotnet build-server</span></span>

<span data-ttu-id="70dfa-104">**이 문서 적용 대상: ✓** .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="70dfa-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="70dfa-105">name</span><span class="sxs-lookup"><span data-stu-id="70dfa-105">Name</span></span>

<span data-ttu-id="70dfa-106">`dotnet build-server` - 빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="70dfa-107">개요</span><span class="sxs-lookup"><span data-stu-id="70dfa-107">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="70dfa-108">명령</span><span class="sxs-lookup"><span data-stu-id="70dfa-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="70dfa-109">Dotnet에서 시작된 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="70dfa-110">기본적으로 모든 서버가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="70dfa-111">옵션</span><span class="sxs-lookup"><span data-stu-id="70dfa-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="70dfa-112">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="70dfa-113">MSBuild 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="70dfa-114">Razor 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="70dfa-115">VB/C# 컴파일러 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70dfa-115">Shuts down the VB/C# compiler build server.</span></span>