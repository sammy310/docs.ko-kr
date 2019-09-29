---
title: 탭 완성 기능 사용
description: 이 문서에서는 PowerShell, Bash 및 zsh용 .NET Core CLI에 대한 탭 완성 기능을 사용하는 방법을 설명합니다.
author: thraka
ms.author: adegeo
ms.date: 12/17/2018
ms.openlocfilehash: 0f29ba2ef1d419339a0e2dc44f67c93b326eb40d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182462"
---
# <a name="how-to-enable-tab-completion-for-net-core-cli"></a><span data-ttu-id="33deb-103">.NET Core CLI에 대한 TAB 완성 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="33deb-103">How to enable TAB completion for .NET Core CLI</span></span>

<span data-ttu-id="33deb-104">.NET Core 2.0 SDK부터 .NET Core CLI는 탭 완성 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-104">Starting with .NET Core 2.0 SDK, the .NET Core CLI supports tab completion.</span></span> <span data-ttu-id="33deb-105">이 문서에서는 세 개의 셸, PowerShell, Bash 및 zsh에 대한 탭 완성 기능을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="33deb-106">다른 셸에는 자동 완성에 대한 지원이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-106">Other shells may have support for auto completion.</span></span> <span data-ttu-id="33deb-107">자동 완성을 구성하는 방법에 대해 해당 설명서를 참조하세요. 단계는 이 문서에 설명된 단계와 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-107">Refer to their documentation on how to configure auto completion, the steps should be similar to the steps described in this article.</span></span>

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

<span data-ttu-id="33deb-108">설정되면 .NET Core CLI에 대한 탭 완성 기능이 셸에서 `dotnet` 명령을 입력한 다음, TAB 키를 눌러서 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-108">Once setup, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="33deb-109">현재 명령줄은 `dotnet complete` 명령으로 전송되고, 결과는 셸에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-109">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="33deb-110">`dotnet complete` 명령으로 직접 전송하여 탭 완성 기능을 사용하지 않고 결과를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-110">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="33deb-111">예:</span><span class="sxs-lookup"><span data-stu-id="33deb-111">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="33deb-112">해당 명령이 작동하지 않는 경우 .NET Core 2.0 SDK 이상이 설치되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-112">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="33deb-113">설치되었지만 해당 명령이 여전히 작동하지 않는 경우 `dotnet` 명령이 .NET Core 2.0 SDK 이상 버전으로 확인되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-113">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="33deb-114">`dotnet --version` 명령을 사용하여 현재 경로가 확인되는 `dotnet`의 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-114">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="33deb-115">자세한 내용은 [사용할 .NET Core 버전 선택](../versions/selection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33deb-115">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="33deb-116">예</span><span class="sxs-lookup"><span data-stu-id="33deb-116">Examples</span></span>

<span data-ttu-id="33deb-117">탭 완성 기능에서 제공하는 몇 가지 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-117">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="33deb-118">입력</span><span class="sxs-lookup"><span data-stu-id="33deb-118">Input</span></span>                                | <span data-ttu-id="33deb-119">다음이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-119">becomes</span></span>                                                                     | <span data-ttu-id="33deb-120">이유</span><span class="sxs-lookup"><span data-stu-id="33deb-120">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="33deb-121">`add`는 사전순으로 첫 번째 하위 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-121">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="33deb-122">탭 완성 기능은 부분 문자열과 일치하고 `--help`가 사전순으로 먼저 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-122">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="33deb-123">탭 키를 두 번째로 누르면 다음 제안이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-123">Pressing tab a second time brings up the next suggestion.</span></span>      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="33deb-124">결과는 사전순으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-124">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="33deb-125">탭 완성 기능은 프로젝트 파일 인식입니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-125">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="33deb-126">PowerShell</span><span class="sxs-lookup"><span data-stu-id="33deb-126">PowerShell</span></span>

<span data-ttu-id="33deb-127">.NET Core CLI에 대한 **PowerShell**에 탭 완성 기능을 추가하려면 변수 `$PROFILE`에 저장된 프로필을 만들거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-127">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="33deb-128">자세한 내용은 [프로필을 만드는 방법](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) 및 [프로필 및 실행 정책](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33deb-128">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span></span> 

<span data-ttu-id="33deb-129">프로필에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-129">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="33deb-130">Bash</span><span class="sxs-lookup"><span data-stu-id="33deb-130">Bash</span></span>

<span data-ttu-id="33deb-131">.NET Core CLI에 대한 **bash** 셸에 탭 완성 기능을 추가하려면 `.bashrc` 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-131">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}")"

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="33deb-132">Zsh</span><span class="sxs-lookup"><span data-stu-id="33deb-132">Zsh</span></span>

<span data-ttu-id="33deb-133">.NET Core CLI에 대한 **zsh** 셸에 탭 완성 기능을 추가하려면 `.zshrc` 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33deb-133">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
