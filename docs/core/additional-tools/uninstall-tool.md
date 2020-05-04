---
title: 제거 도구
description: .NET Core SDK 및 런타임의 제어된 정리를 사용 설정하는 단계별 도구인 .NET Core 제거 도구에 대한 개요입니다.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 45cf0841391d02636770e98666e2897d2598fab4
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595717"
---
# <a name="net-core-uninstall-tool"></a>.NET Core 제거 도구

[.NET Core 제거 도구](https://aka.ms/dotnet-core-uninstall-tool)(`dotnet-core-uninstall`)를 사용하면 시스템에서 .NET Core SDK 및 런타임을 제거할 수 있습니다. 제거하고자 하는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.

도구는 Windows 및 macOS를 지원합니다. Linux는 현재 지원되지 않습니다.

Windows에서 도구는 다음 설치 관리자 중 하나를 사용하여 설치된 SDK 및 런타임만 제거할 수 있습니다.

- .NET Core SDK 및 런타임 설치 관리자.
- Visual Studio 2019 버전 16.3 이전 버전의 Visual studio 설치 관리자.

macOS에서 도구는 */usr/local/share/dotnet* 폴더에 있는 SDK 및 런타임만 제거할 수 있습니다.

이러한 제한 사항으로 인해 도구는 컴퓨터에서 모든 .NET Core SDK 및 런타임을 제거하지 못할 수 있습니다. `dotnet --info` 명령을 사용하여 이 도구에서 제거할 수 없는 SDK 및 런타임을 포함하여 설치된 모든 .NET Core SDK 및 런타임을 찾을 수 있습니다. `dotnet-core-uninstall list` 명령을 사용하면 도구를 사용하여 제거할 수 있는 SDK가 표시됩니다.

## <a name="install-the-tool"></a>도구 설치

.NET Core 제거 도구를 [여기](https://aka.ms/dotnet-core-uninstall-tool)에서 다운로드할 수 있으며 [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub 리포지토리에서 소스 코드를 찾을 수 있습니다.

> [!NOTE]
> 이 도구에는 .NET Core SDK 및 런타임 제거를 위한 권한 상승이 필요합니다. 따라서 Windows의 경우 *C:\Program Files*, 또는 macOS의 경우 */usr/local/bin*과 같이 쓰기 보호된 디렉터리에 설치해야 합니다. [dotnet 명령에 대한 상승된 액세스 권한](../tools/elevated-access.md)을 참조하세요. 자세한 내용은 [자세한 설치 지침](https://aka.ms/dotnet-core-uninstall-tool)을 참조하세요.

## <a name="run-the-tool"></a>도구 실행

다음 단계는 제거 도구 실행을 위한 권장 접근 방식을 보여줍니다.

- [1단계 - 설치된 .NET Core SDK 및 런타임 표시](#step-1---display-installed-net-core-sdks-and-runtimes)
- [2단계- 시험 실행 실시](#step-2---do-a-dry-run)
- [3단계 - .NET Core SDK 및 런타임 제거](#step-3---uninstall-net-core-sdks-and-runtimes)
- [4단계 - NuGet 대체 폴더 삭제(선택 사항)](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a>1단계 - 설치된 .NET Core SDK 및 런타임 표시

`dotnet-core-uninstall list` 명령은 이 도구를 사용하여 제거할 수 있는 설치된 .NET Core SDK 및 런타임을 나열합니다. 일부 SDK 및 런타임은 Visual Studio에 필요할 수 있으며, 제거를 권장하지 않는 이유를 포함하여 표시됩니다.

> [!NOTE]
> 대부분의 경우 `dotnet-core-uninstall list` 명령의 출력이 `dotnet --info`의 출력에서 설치된 버전 목록과 일치하지 않습니다. 특히 이 도구는 zip 파일로 설치되거나 Visual Studio에서 관리하는 버전을 표시하지 않습니다(Visual Studio 2019 16.3 이상에 설치된 모든 버전). Visual Studio에서 버전을 관리하는지 확인하는 한 가지 방법은 Visual Studio 관리되는 버전이 표시 이름에 표시되는 `Add or Remove Programs`에서 확인하는 것입니다.

**dotnet-core-uninstall list**

#### <a name="synopsis"></a>개요

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a>옵션

## <a name="windows"></a>[Windows](#tab/windows)

* **`--aspnet-runtime`**

  이 도구를 사용하여 제거할 수 있는 모든 ASP.NET Core 런타임을 나열합니다.

* **`--hosting-bundle`**

  이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임 및 호스팅 번들을 나열합니다.

* **`--runtime`**

  이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임을 나열합니다.

* **`--sdk`**

  이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK를 나열합니다.

* **`-v, --verbosity <LEVEL>`**

  자세한 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.

* **`--x64`**

  이 도구를 사용하여 제거할 수 있는 모든 x64 .NET Core SDK 및 런타임을 나열합니다.

* **`--x86`**

  이 도구를 사용하여 제거할 수 있는 모든 x86 .NET Core SDK 및 런타임을 나열합니다.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--runtime`**

  이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임을 나열합니다.

* **`--sdk`**

  이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK를 나열합니다.

* **`-v, --verbosity <LEVEL>`**

  자세한 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.
  
---

#### <a name="examples"></a>예

* 이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK 및 런타임 나열:

  ```console
  dotnet-core-uninstall list
  ```

* 모든 x64 .NET Core SDK 및 런타임 나열:

  ```console
  dotnet-core-uninstall list --x64
  ```

* 모든 x86 .NET Core SDK 나열:

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a>2단계- 시험 실행 실시

`dotnet-core-uninstall dry-run` 및 `dotnet-core-uninstall whatif` 명령은 제거를 수행하지 않고 입력한 옵션에 따라 제거할 .NET Core SDK 및 런타임을 표시합니다. 이 명령은 동의어입니다.

**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**

#### <a name="synopsis"></a>개요

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a>인수

* **`VERSION`**

  제거할 지정된 버전입니다. 공백으로 구분하여 여러 버전을 나열할 수 있습니다. 지시 파일도 지원됩니다.

  > [!TIP]
  > 지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.
  > 지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.
  > `VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.

#### <a name="options"></a>옵션

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  모든 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-below <VERSION>`**

  지정된 버전보다 이전 버전의 .NET Core SDK 및 런타임만을 제거합니다. 지정된 버전은 설치된 상태로 유지됩니다.

* **`--all-but <VERSIONS>`**

  지정된 버전을 제외한 모든 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-but-latest`**

  최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-lower-patches`**

  상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다. 이 옵션은 global.json을 보호합니다.

* **`--all-previews`**

  미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-previews-but-latest`**

  최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--aspnet-runtime`**

  ASP.NET Core 런타임만 제거합니다.

* **`--hosting-bundle`**

  .NET Core 런타임 및 호스팅 번들만 제거합니다.

* **`--major-minor <MAJOR_MINOR>`**

  지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.

* **`--runtime`**

  .NET Core 런타임만 제거합니다.

* **`--sdk`**

  .NET Core SDK만 제거합니다.

* **`-v, --verbosity <LEVEL>`**

  자세한 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.

* **`--x64`**

  `--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.

* **`--x86`**

  `--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.

* **`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.

참고:

1. 정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.
3. `--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  모든 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-below <VERSION>`**

  지정된 버전보다 낮은 .NET Core SDK 및 런타임을 제거합니다. 지정된 버전은 그대로 유지됩니다.

* **`--all-but <VERSIONS>`**

  지정된 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-but-latest`**

  최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-lower-patches`**

  상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다. 이 옵션은 global.json을 보호합니다.

* **`--all-previews`**

  미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-previews-but-latest`**

  최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--major-minor <MAJOR_MINOR>`**

  지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.

* **`--runtime`**

  .NET Core 런타임만 제거합니다.

* **`--sdk`**

  .NET Core SDK만 제거합니다.

* **`-v, --verbosity <LEVEL>`**

  자세한 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.
  
* **`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.

참고:

1. 정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.

---

#### <a name="examples"></a>예

> [!NOTE]
> 기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임은 `dotnet-core-uninstall dry-run` 출력에 포함되지 않습니다. 다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 출력에 포함되지 않을 수 있습니다. 모든 SDK 및 런타임을 포함하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.

* 상위 패치로 대체된 모든 .NET Core 런타임 제거를 시험 실행:

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* 버전 `2.2.301` 이하의 모든 .NET Core SDK 제거를 시험 실행:

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a>3단계 - .NET Core SDK 및 런타임 제거

`dotnet-core-uninstall remove`는 옵션 컬렉션에서 지정한 .NET Core SDK 및 런타임을 제거합니다. 이 도구는 버전 5.0 이상의 SDK 및 런타임 제거에 사용할 수 없습니다.

이 도구는 파괴적인 동작을 포함하므로 제거 명령을 실행하기 전에 시험 실행을 실시하는 것을 **적극** 권장합니다. 시험 실행에서 `remove` 명령을 사용하면 어떤 .NET Core SDK 및 런타임이 제거되는지 표시됩니다. 어떤 SDK 및 런타임을 안전하게 제거할 수 있는지 알아보려면 [버전을 제거해야 하나요?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version)를 참조하세요.

> [!CAUTION]
> 다음 사항에 주의하세요.
>
>- 이 도구는 컴퓨터의 `global.json` 파일에 필요한 .NET Core SDK 버전을 제거할 수 있습니다. [.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 .NET Core SDK를 다시 설치할 수 있습니다.
>- 이 도구는 컴퓨터의 프레임워크 종속 애플리케이션에 필요한 .NET Core 런타임 버전을 제거할 수 있습니다. [.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 .NET Core 런타임을 다시 설치할 수 있습니다.
>- 이 도구는 Visual Studio에서 사용하는 .NET Core SDK 및 런타임 버전을 제거할 수 있습니다. Visual Studio 설치를 중단하는 경우 Visual Studio 설치 관리자에서 "복구"를 실행하여 작업 상태로 돌아갑니다.

기본적으로 모든 명령은 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임을 유지합니다. 이러한 SDK 및 런타임은 명시적으로 인수로 나열하거나 `--force` 옵션을 사용하여 제거할 수 있습니다.

이 도구에는 .NET Core SDK 및 런타임 제거를 위한 권한 상승이 필요합니다. Windows의 관리자 명령 프롬프트에서 및 macOS의 `sudo`를 사용하여 도구를 실행합니다. `dry-run` 및 `whatif` 명령에는 권한 상승이 필요하지 않습니다.

**dotnet-core-uninstall remove**

#### <a name="synopsis"></a>개요

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a>인수

* **`VERSION`**

  제거할 지정된 버전입니다. 공백으로 구분하여 여러 버전을 나열할 수 있습니다. 지시 파일도 지원됩니다.

  > [!TIP]
  > 지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.
  > 지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.
  > `VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.

#### <a name="options"></a>옵션

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  모든 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-below <VERSION>`**

  지정된 버전보다 이전 버전의 .NET Core SDK 및 런타임만을 제거합니다. 지정된 버전은 설치된 상태로 유지됩니다.

* **`--all-but <VERSIONS>`**

  지정된 버전을 제외한 모든 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-but-latest`**

  최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-lower-patches`**

  상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다. 이 옵션은 global.json을 보호합니다.

* **`--all-previews`**

  미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-previews-but-latest`**

  최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--aspnet-runtime`**

  ASP.NET Core 런타임만 제거합니다.

* **`--hosting-bundle`**

  .NET Core 런타임 및 호스팅 번들만 제거합니다.

* **`--major-minor <MAJOR_MINOR>`**

  지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.

* **`--runtime`**

  .NET Core 런타임만 제거합니다.

* **`--sdk`**

  .NET Core SDK만 제거합니다.

* **`-v, --verbosity <LEVEL>`**

  자세한 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.

* **`--x64`**

  `--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.

* **`--x86`**

  `--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.

* **`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.

* **`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.

참고:

1. 정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.
3. `--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  모든 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-below <VERSION>`**

  지정된 버전보다 낮은 .NET Core SDK 및 런타임을 제거합니다. 지정된 버전은 그대로 유지됩니다.

* **`--all-but <VERSIONS>`**

  지정된 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-but-latest`**

  최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-lower-patches`**

  상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다. 이 옵션은 global.json을 보호합니다.

* **`--all-previews`**

  미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--all-previews-but-latest`**

  최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.

* **`--major-minor <MAJOR_MINOR>`**

  지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.

* **`--runtime`**

  .NET Core 런타임만 제거합니다.

* **`--sdk`**

  .NET Core SDK만 제거합니다.

* **`-v, --verbosity <LEVEL>`**

  자세한 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.

* **`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.
  
* **`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.

참고:

1. 정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.

---

#### <a name="examples"></a>예

> [!NOTE]
> 기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임은 유지됩니다. 다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 그대로 유지될 수 있습니다. 모든 SDK 및 런타임을 제거하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.

* `3.0.0-preview6-27804-01` 버전을 제외한 모든 .NET Core 런타임을 예 또는 아니요 확인 없이 제거:

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* 모든 .NET Core 1.1 SDK를 예 또는 아니요 확인 없이 제거:

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* 콘솔 출력이 없는 .NET Core 1.1.11 SDK 제거:

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* 이 도구로 안전하게 제거할 수 있는 모든 .NET Core SDK 제거:

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* Visual Studio에서 필요할 수 있는 SDK를 포함하여 이 도구로 제거할 수 있는 모든 .NET Core SDK 제거(권장하지 않음):

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* 지시 파일 `versions.rsp`에 지정된 모든 .NET Core SDK 제거

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  *versions.rsp*의 내용은 다음과 같습니다.
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a>4단계 - NuGet 대체 폴더 삭제(선택 사항)

경우에 따라 더 이상 `NuGetFallbackFolder`가 필요하지 않아 이를 삭제하고자 할 수 있습니다. 이 폴더를 삭제하는 방법에 대한 자세한 내용은 [NuGetFallbackFolder 제거](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)를 참조하세요.

## <a name="uninstall-the-tool"></a>도구 제거

## <a name="windows"></a>[Windows](#tab/windows)

1. **프로그램 추가/제거**를 엽니다.
2. `Microsoft .NET Core SDK Uninstall Tool`을 검색합니다.
3. **제거**를 선택합니다.

## <a name="macos"></a>[macOS](#tab/macos)

설치된 디렉터리에서 다운로드한 *dotnet-core-uninstall.tar.gz* 파일을 삭제합니다. 이 파일의 압축을 다른 디렉터리에 푼 경우 파일 내용 또한 삭제해야 합니다.

---
