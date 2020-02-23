---
title: dotnet help 명령
description: dotnet help 명령은 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.
ms.date: 02/14/2020
ms.openlocfilehash: f5d9221ae18653451a3bf97dc82fae396ae4e288
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503722"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="8679d-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="8679d-103">dotnet help reference</span></span>

<span data-ttu-id="8679d-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="8679d-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8679d-105">이름</span><span class="sxs-lookup"><span data-stu-id="8679d-105">Name</span></span>

<span data-ttu-id="8679d-106">`dotnet help` - 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8679d-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8679d-107">개요</span><span class="sxs-lookup"><span data-stu-id="8679d-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="8679d-108">설명</span><span class="sxs-lookup"><span data-stu-id="8679d-108">Description</span></span>

<span data-ttu-id="8679d-109">`dotnet help` 명령은 docs.microsoft.com에서 지정된 명령에 대한 자세한 정보를 제공하는 참조 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8679d-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="8679d-110">인수</span><span class="sxs-lookup"><span data-stu-id="8679d-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="8679d-111">.NET Core CLI 명령의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8679d-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="8679d-112">유효한 CLI 명령 목록은 [CLI 명령](index.md#cli-commands)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8679d-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="8679d-113">옵션</span><span class="sxs-lookup"><span data-stu-id="8679d-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8679d-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8679d-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8679d-115">예</span><span class="sxs-lookup"><span data-stu-id="8679d-115">Examples</span></span>

- <span data-ttu-id="8679d-116">[dotnet new](dotnet-new.md) 명령에 대한 설명서 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8679d-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
