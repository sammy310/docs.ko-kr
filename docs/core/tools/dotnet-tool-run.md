---
title: dotnet tool run 명령
description: dotnet tool run 명령은 로컬 도구를 호출합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543829"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="bb848-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="bb848-103">dotnet tool run</span></span>

<span data-ttu-id="bb848-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="bb848-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="bb848-105">이름</span><span class="sxs-lookup"><span data-stu-id="bb848-105">Name</span></span>

<span data-ttu-id="bb848-106">`dotnet tool run` - 로컬 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bb848-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bb848-107">개요</span><span class="sxs-lookup"><span data-stu-id="bb848-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="bb848-108">설명</span><span class="sxs-lookup"><span data-stu-id="bb848-108">Description</span></span>

<span data-ttu-id="bb848-109">`dotnet tool run` 명령은 현재 디렉터리에 대한 범위에 있는 도구 매니페스트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bb848-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="bb848-110">지정된 도구에 대한 참조를 찾으면 해당 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb848-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="bb848-111">자세한 내용은 [로컬 도구 호출](global-tools.md#invoke-a-local-tool)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb848-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="bb848-112">인수</span><span class="sxs-lookup"><span data-stu-id="bb848-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="bb848-113">실행할 도구의 명령 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bb848-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="bb848-114">옵션</span><span class="sxs-lookup"><span data-stu-id="bb848-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="bb848-115">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb848-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="bb848-116">예제</span><span class="sxs-lookup"><span data-stu-id="bb848-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="bb848-117">`dotnetsay` 로컬 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb848-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb848-118">참조</span><span class="sxs-lookup"><span data-stu-id="bb848-118">See also</span></span>

- [<span data-ttu-id="bb848-119">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="bb848-119">.NET Core tools</span></span>](global-tools.md)
