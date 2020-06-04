---
title: 세계화 및 ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: 6ea848d4a60069e6702b9d60fd90a55f572fb043
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842514"
---
# <a name="net-globalization-and-icu"></a>.NET 세계화 및 ICU

과거에 .NET 세계화 API는 플랫폼마다 다른 기본 라이브러리를 사용했습니다. Unix에서는 [ICU(International Components for Unicode)](http://site.icu-project.org/home)를 사용했고, Windows에서는 [NLS(National Language Support)](/windows/win32/intl/national-language-support)를 사용했습니다. 이로 인해 서로 다른 플랫폼에서 애플리케이션을 실행할 때 일부 세계화 API의 동작이 약간 달랐습니다. 다음 영역에서는 동작이 확실히 달랐습니다.

- 문화권 및 문화권 데이터
- 문자열 대/소문자 구분
- 문자열 정렬 및 검색
- 정렬 키
- 문자열 정규화
- IDN(다국어 도메인 이름) 지원
- Linux의 표준 시간대 표시 이름

.NET 5.0부터는 사용되는 기본 라이브러리에 대한 개발자의 제어가 향상되면서 애플리케이션의 플랫폼 간 차이를 방지할 수 있게 되었습니다.

## <a name="icu-on-windows"></a>Windows의 ICU

Windows 10 2019년 5월 업데이트 이상 버전에는 OS의 일부로 [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-)이 포함되어 있으며, .NET 5.0 이상 버전에서는 기본적으로 ICU를 사용합니다. Windows에서 실행하는 경우 .NET 5.0 이상 버전은 `icu.dll`을 로드하려 시도하고 사용 가능하면 세계화 구현에 사용합니다.  이전 버전의 Windows에서 실행하는 경우처럼 해당 라이브러리를 찾을 수 없거나 로드할 수 없다면 .NET 5.0 이상 버전은 NLS 기반 구현으로 대체합니다.

> [!NOTE]
> ICU를 사용하는 경우에도 `CurrentCulture`, `CurrentUICulture`, `CurrentRegion` 멤버는 여전히 Windows 운영 체제 API를 사용하여 사용자 설정을 적용합니다.

### <a name="using-nls-instead-of-icu"></a>ICU 대신 NLS 사용

NLS 대신 ICU를 사용하면 일부 세계화 관련 작업에서 동작 차이가 발생할 수 있습니다. 개발자는 NLS 사용으로 되돌리기 위해 ICU 구현을 옵트아웃할 수 있습니다. 애플리케이션은 다음 방법으로 NLS 모드를 사용하도록 설정할 수 있습니다.

- 프로젝트 파일에서:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
</ItemGroup>
```

- 파일 `runtimeconfig.json`에서:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.UseNls": true
      }
  }
}
```

- 환경 변수 `DOTNET_SYSTEM_GLOBALIZATION_USENLS`를 `true` 또는 `1`로 설정.

> [!NOTE]
> 프로젝트 또는 `runtimeconfig.json` 파일에 설정된 값은 환경 변수보다 우선적으로 적용됩니다.

자세한 내용은 [런타임 구성 설정](../../core/run-time-config/globalization.md#nls)을 참조하세요.

## <a name="app-local-icu"></a>앱 로컬 ICU

각 ICU 릴리스는 버그 수정뿐 아니라 세계 언어를 설명하는 업데이트된 CLDR(Common Locale Data Repository) 데이터를 제공할 수 있습니다. ICU 버전 간 이동은 세계화 관련 작업과 관련하여 앱 동작에 미묘한 영향을 줄 수 있습니다.  애플리케이션 개발자가 모든 배포에서 일관성을 유지할 수 있도록 .NET 5.0 이상 버전에서는 Windows 및 Unix의 앱이 자체 ICU 복사본을 갖고 사용할 수 있습니다.

애플리케이션은 다음 방법으로 앱 로컬 ICU 구현 모드를 옵트인할 수 있습니다.

- 프로젝트 파일에서:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
</ItemGroup>
```

- 파일 `runtimeconfig.json`에서:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
      }
  }
}
```

- 환경 변수 `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU`를 `<suffix>:<version>` 또는 `<version>`으로 설정.

`<suffix>`: 공용 ICU 패키징 규칙에 따라 길이가 36자 미만인 선택적 접미사입니다. 사용자 지정 ICU를 빌드할 때 lib 이름을 생성하고 내보낸 기호 이름이 접미사를 포함하도록(예: `libicuucmyapp`, 여기서 `myapp`은 접미사) 사용자 지정할 수 있습니다.

`<version>`: 유효한 ICU 버전입니다(예: 67.1). 이 버전은 이진 파일을 로드하고 내보낸 기호를 가져오는 데 사용됩니다.

앱 로컬 스위치가 설정된 경우 ICU를 로드하기 위해 .NET은 여러 경로를 검색하는 <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> 메서드를 사용합니다. 메서드는 먼저 `NATIVE_DLL_SEARCH_DIRECTORIES` 속성에서 라이브러리를 찾으려고 시도합니다. 이 라이브러리는 앱의 `deps.json` 파일에 기반한 dotnet 호스트에서 만들어집니다. 자세한 내용은 [기본 검색](../../core/dependency-loading/default-probing.md)을 참조하세요.

자체 포함 앱의 경우 ICU가 앱 디렉터리에 있는지 확인하는 것 외에 특별한 작업이 필요하지 않습니다(자체 포함 앱의 경우 작업 디렉터리의 기본값은 `NATIVE_DLL_SEARCH_DIRECTORIES`).

NuGet 패키지를 통해 사용하는 ICU는 프레임워크 종속 애플리케이션에서 작동합니다. NuGet은 네이티브 자산을 확인하여 `deps.json` 파일 및 `runtimes` 디렉터리 아래에 있는 애플리케이션의 출력 디렉터리에 포함합니다. .NET은 여기에서 로드합니다.

ICU가 로컬 빌드에서 사용되는 프레임워크 종속 앱(자체 포함 앱 아님)의 경우 추가 단계를 수행해야 합니다. .NET SDK에는 "느슨한" 네이티브 이진 파일을 `deps.json`에 통합하는 기능이 아직 없습니다([이 SDK 문제](https://github.com/dotnet/sdk/issues/11373) 참조). 대신 애플리케이션의 프로젝트 파일에 추가 정보를 추가하여 이 기능을 사용하도록 설정할 수 있습니다. 예를 들어:

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

지원되는 런타임의 모든 ICU 이진 파일에 이 작업을 수행해야 합니다. 또한 `RuntimeTargetsCopyLocalItems` 항목 그룹의 `NuGetPackageId` 메타데이터는 프로젝트가 실제로 참조하는 NuGet 패키지와 일치해야 합니다.

### <a name="macos-behavior"></a>macOS 동작

`macOS`에는 Linux 로더와는 다른, `match-o` 파일에 지정된 load 명령에서 종속 동적 라이브러리를 확인하는 동작이 있습니다. Linux 로더에서 .NET은 ICU 종속성 그래프를 충족하기 위해 `libicudata`, `libicuuc`, `libicui18n`을 (이 순서로) 시도할 수 있습니다. 하지만 macOS에서는 이것이 작동하지 않습니다. macOS에서 ICU를 빌드하는 경우 기본적으로 `libicuuc`에서 이러한 load 명령을 사용하여 동적 라이브러리를 가져옵니다. 예를 들어:

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

이러한 명령은 ICU의 다른 구성 요소에 대한 종속 라이브러리의 이름을 참조합니다. 로더는 `dlopen` 규칙에 따라 검색을 수행합니다. 그러려면 시스템 디렉터리에 이러한 라이브러리가 있거나 `LD_LIBRARY_PATH` 환경 변수를 설정하거나 앱 수준 디렉터리에 ICU가 있어야 합니다. `LD_LIBRARY_PATH`를 설정할 수 없거나 ICU 바이너리가 앱 수준 디렉터리에 있는지 확인할 수 없다면 몇 가지 추가 작업을 수행해야 합니다.

`@loader_path`와 같이 해당 load 명령을 사용하여 이진 파일과 동일한 디렉터리에서 해당 종속성을 검색하도록 로더에게 지시하는 로더를 위한 몇 가지 지시문이 있습니다. 두 가지 방법으로 이 작업을 수행할 수 있습니다.

- `install_name_tool -change`

  다음 명령을 실행합니다.

```bash
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
```

- `@loader_path`로 설치 이름을 생성하도록 ICU 패치

  autoconf(`./runConfigureICU`)를 실행하기 전에 [이 줄](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37)을 다음으로 변경합니다.

```
LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
```
