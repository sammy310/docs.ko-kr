---
title: 탭 완성 기능 사용
description: 이 문서에서는 PowerShell, Bash, zsh 및 fish용 .NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법을 설명합니다.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: b5b63166faa1762d9fa82a93aa70aebb33167630
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585561"
---
# <a name="how-to-enable-tab-completion-for-the-net-cli"></a>.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

이 문서에서는 네 개의 셸 PowerShell, Bash, zsh 및 fish에 대한 탭 완성 기능을 구성하는 방법을 설명합니다. 그 밖의 셸은 해당 셸의 설명서에서 탭 완성 기능을 구현하는 방법을 확인하세요.

설정되면 셸에 `dotnet` 명령을 입력하고 Tab 키를 누르면 .NET CLI의 탭 완성 기능이 트리거됩니다. 현재 명령줄은 `dotnet complete` 명령으로 전송되고, 결과는 셸에 의해 처리됩니다. `dotnet complete` 명령으로 직접 전송하여 탭 완성 기능을 사용하지 않고 결과를 테스트할 수 있습니다. 예를 들어:

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

해당 명령이 작동하지 않는 경우 .NET Core 2.0 SDK 이상이 설치되었는지 확인합니다. 설치되었지만 해당 명령이 여전히 작동하지 않는 경우 `dotnet` 명령이 .NET Core 2.0 SDK 이상 버전으로 확인되는지 확인합니다. `dotnet --version` 명령을 사용하여 현재 경로가 확인되는 `dotnet`의 버전을 확인합니다. 자세한 내용은 [사용할 .NET 버전 선택](../versions/selection.md)을 참조하세요.

### <a name="examples"></a>예

탭 완성 기능에서 제공하는 몇 가지 예제는 다음과 같습니다.

입력                                | 다음이 됩니다.                                                                     | 이유
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | `add`는 사전순으로 첫 번째 하위 명령입니다.
`dotnet add p⇥`                      | `dotnet add --help`                                                          | 탭 완성 기능은 부분 문자열과 일치하고 `--help`가 사전순으로 먼저 제공됩니다.
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | 탭 키를 두 번째로 누르면 다음 제안이 나타납니다.
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | 결과는 사전순으로 반환됩니다.
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | 탭 완성 기능은 프로젝트 파일 인식입니다.

## <a name="powershell"></a>PowerShell

.NET CLI용 **PowerShell** 에 탭 완성 기능을 추가하려면 `$PROFILE` 변수에 저장된 프로필을 만들거나 편집합니다. 자세한 내용은 [프로필을 만드는 방법](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) 및 [프로필 및 실행 정책](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy)을 참조하세요.

프로필에 다음 코드를 추가합니다.

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a>bash

.NET CLI용 **bash** 셸에 탭 완성 기능을 추가하려면 `.bashrc` 파일에 다음 코드를 추가합니다.

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a>zsh

.NET CLI용 **zsh** 셸에 탭 완성 기능을 추가하려면 `.zshrc` 파일에 다음 코드를 추가합니다.

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```

## <a name="fish"></a>fish

.NET CLI용 **fish** 셸에 탭 완성 기능을 추가하려면 `config.fish` 파일에 다음 코드를 추가합니다.

```fish
complete -f -c dotnet -a "(dotnet complete)"
```
