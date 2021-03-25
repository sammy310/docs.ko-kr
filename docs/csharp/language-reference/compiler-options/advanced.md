---
description: 고급 C# 컴파일러 옵션. 이러한 옵션은 고급 시나리오에서 사용됩니다.
title: C# 컴파일러 옵션 - 고급 시나리오
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- BaseAddress compiler option [C#]
- ChecksumAlgorithm compiler option [C#]
- CodePage compiler option [C#]
- Utf8Output compiler option [C#]
- MainEntryPoint compiler option [C#]
- GenerateFullPaths compiler option [C#]
- FileAlignment compiler option [C#]
- PathMap compiler option [C#]
- PdbFile compiler option [C#]
- ErrorEndLocation compiler option [C#]
- NoStandardLib compiler option [C#]
- PreferredUILang compiler option [C#]
- SubsystemVersion compiler option [C#]
- AdditionalLibPaths compiler option [C#]
- ApplicationConfiguration compiler option [C#]
- ModuleAssemblyName compiler option [C#]
ms.openlocfilehash: 47c84968682e056acdb73805807d907c6bb7c7ee
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104652765"
---
# <a name="advanced-c-compiler-options"></a>고급 C# 컴파일러 옵션

다음 옵션은 고급 시나리오를 지원합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 `csc.exe` 구문은 `code style`에 표시되어 있습니다.

- **MainEntryPoint**, **StartupObject** / `-main`: 진입점을 포함하는 형식을 지정합니다.
- **PdbFile** / `-pdb`: 디버그 정보 파일 이름을 지정합니다.
- **PathMap** / `-pathmap`: 컴파일러에서 출력되는 소스 경로 이름에 대한 매핑을 지정합니다.
- **ApplicationConfiguration** / `-appconfig`: 어셈블리 바인딩 설정을 포함하는 애플리케이션 구성 파일을 지정합니다.
- **AdditionalLibPaths** / `-lib`: 참조를 검색할 추가 디렉터리를 지정합니다.
- **GenerateFullPaths** / `-fullpath`: 컴파일러는 정규화된 경로를 생성합니다.
- **PreferredUILang** / `-preferreduilang`: 기본 출력 언어 이름을 지정합니다.
- **BaseAddress** / `-baseaddress`: 빌드할 라이브러리의 기준 주소를 지정합니다.
- **ChecksumAlgorithm** / `-checksumalgorithm`: PDB에 저장된 소스 파일 체크섬을 계산하기 위한 알고리즘을 지정합니다.
- **CodePage** / `-codepage`: 소스 파일을 열 때 사용할 코드 페이지를 지정합니다.
- **Utf8Output** / `-utf8output`: 컴파일러 메시지를 UTF-8 인코딩으로 출력합니다.
- **FileAlignment** / `-filealign`: 출력 파일 섹션에 사용되는 맞춤을 지정합니다.
- **ErrorEndLocation** / `-errorendlocation`: 각 오류의 끝 위치에 해당하는 줄과 열을 출력합니다.
- **NoStandardLib** / `-nostdlib`: 표준 라이브러리 *mscorlib.dll* 을 참조하지 않습니다.
- **SubsystemVersion** / `-subsystemversion`: 이 어셈블리의 하위 시스템 버전을 지정합니다.
- **ModuleAssemblyName** / `-moduleassemblyname`: 이 모듈이 속할 어셈블리의 이름입니다.

## <a name="mainentrypoint-or-startupobject"></a>MainEntryPoint 또는 StartupObject

이 옵션은 둘 이상의 클래스에 `Main` 메서드가 포함된 경우 프로그램에 대한 진입점을 포함하는 클래스를 지정합니다.

```xml
<StartupObject>MyNamespace.Program</StartupObject>
```

또는

```xml
<MainEntryPoint>MyNamespace.Program</MainEntryPoint>
```

여기서 `Program`은 `Main` 메서드를 포함하는 형식입니다. 제공된 클래스 이름은 완전히 정규화되어야 하며, 클래스를 포함하는 전체 네임스페이스와 클래스 이름을 포함해야 합니다. 예를 들어 `Main` 메서드가 `MyApplication.Core` 네임스페이스의 `Program` 클래스 내에 있는 경우 컴파일러 옵션은 `-main:MyApplication.Core.Program`이어야 합니다. 컴파일에 [`Main`](../../programming-guide/main-and-command-args/index.md) 메서드가 있는 유형이 두 개 이상 포함된 경우 `Main` 메서드를 포함하는 유형을 지정할 수 있습니다.

> [!NOTE]
> 이 옵션은 프로젝트에 하나 이상의 `Main` 메서드가 포함되어 있더라도 [최상위 문](../../programming-guide/main-and-command-args/top-level-statements.md)을 포함하는 프로젝트에는 사용할 수 없습니다.

## <a name="pdbfile"></a>PdbFile

**PdbFile** 컴파일러 옵션은 디버그 기호 파일의 이름과 위치를 지정합니다.  `filename` 값은 디버그 기호 파일의 이름과 위치를 지정합니다.  

```xml
<PdbFile>filename</PdbFile>
```

[**DebugType**](code-generation.md#debugtype)을 지정하면 컴파일러는 컴파일러가 출력 파일(.exe 또는 .dll)을 만드는 동일한 디렉터리에 *.pdb* 파일을 만듭니다. *.Pdb* 파일은 출력 파일의 이름과 동일한 기본 파일 이름을 갖습니다. **PdbFile** 을 사용하면 .pdb 파일에 대해 기본값이 아닌 파일 이름과 위치를 지정할 수 있습니다. Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  

## <a name="pathmap"></a>PathMap

**PathMap** 컴파일러 옵션은 실제 경로를 컴파일러에서 출력되는 소스 경로 이름에 매핑하는 방법을 지정합니다. 이 옵션은 컴파일러가 실행되는 컴퓨터의 실제 경로 각각을 출력 파일에 써야 하는 해당 경로에 매핑합니다. 다음 예제에서 `path1`은 현재 환경에 있는 원본 파일의 전체 경로이고 `sourcePath1`은 출력 파일에서 `path1`을 대체하는 소스 경로입니다. 매핑되는 소스 경로를 여러 개 지정하려면 각각을 세미콜론으로 구분합니다.

```xml
<PathMap>path1=sourcePath1;path2=sourcePath2</PathMap>
```

컴파일러가 출력에 소스 경로를 쓰는 이유는 다음과 같습니다.

1. 선택적 매개 변수에 <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>를 적용할 때 소스 경로가 인수 대신 사용되는 경우
1. 소스 경로가 PDB 파일에 포함된 경우
1. PDB 파일의 경로가 PE(이식 가능한 실행 파일) 파일에 포함된 경우

## <a name="applicationconfiguration"></a>ApplicationConfiguration

**ApplicationConfiguration** 컴파일러 옵션을 사용하면 C# 애플리케이션이 어셈블리 바인딩 시간에 어셈블리의 애플리케이션 구성(app.config) 파일 위치를 CLR(공용 언어 런타임)에 지정할 수 있습니다.

```xml
<ApplicationConfiguration>file</ApplicationConfiguration>
```

여기서 `file`은 어셈블리 바인딩 설정이 포함된 애플리케이션 구성 파일입니다. **ApplicationConfiguration** 의 한 가지 용도는 어셈블리가 특정 참조 어셈블리의 .NET Framework 버전과 .NET Framework for Silverlight 버전을 동시에 둘 다 참조해야 하는 고급 시나리오입니다. 예를 들어 WPF(Windows Presentation Foundation)로 작성된 XAML 디자이너는 디자이너의 사용자 인터페이스를 위한 WPF 데스크톱 및 Silverlight에 포함된 WPF 하위 집합을 둘 다 참조해야 할 수도 있습니다. 같은 디자이너 어셈블리가 두 어셈블리에 모두 액세스해야 합니다. 기본적으로, 어셈블리 바인딩 시 두 어셈블리가 동등한 것으로 간주되기 때문에 서로 다른 참조를 사용할 경우 컴파일러 오류가 발생합니다. **ApplicationConfiguration** 컴파일러 옵션을 사용하면 다음 예제와 같이 `<supportPortability>` 태그를 사용하여 기본 동작을 비활성화하는 app.config 파일의 위치를 지정할 수 있습니다.

```xml
<supportPortability PKT="7cec85d7bea7798e" enable="false"/>
```

컴파일러는 이 파일 위치를 CLR의 어셈블리 바인딩 논리에 전달합니다.

> [!NOTE]
> 프로젝트에 이미 설정된 app.config 파일을 사용하려면 속성 태그 `<UseAppConfigForCompiler>`를 *.csproj* 파일에 추가하고 해당 값을 `true`로 설정합니다. 다른 app.config 파일을 지정하려면 속성 태그 `<AppConfigForCompiler>`를 추가하고 해당 값을 파일 위치로 설정합니다.

다음 예제에서는 애플리케이션이 두 구현에 모두 있는 .NET Framework 어셈블리의 .NET Framework for Silverlight 구현과 .NET Framework 구현 둘 다에 대한 참조를 사용할 수 있도록 하는 app.config 파일을 보여 줍니다. **ApplicationConfiguration** 컴파일러 옵션은 이 app.config 파일의 위치를 지정합니다.

```xml
<configuration>
  <runtime>
    <assemblyBinding>
      <supportPortability PKT="7cec85d7bea7798e" enable="false"/>
      <supportPortability PKT="31bf3856ad364e35" enable="false"/>
    </assemblyBinding>
  </runtime>
</configuration>
```

## <a name="additionallibpaths"></a>AdditionalLibPaths

**AdditionalLibPaths** 옵션은 [**References**](inputs.md#references) 옵션으로 참조되는 어셈블리의 위치를 지정합니다.

```xml
<AdditionalLibPaths>dir1[,dir2]</AdditionalLibPaths>
```

여기서 `dir1`은 참조된 어셈블리를 현재 작업 디렉터리(컴파일러를 호출하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 컴파일러에서 확인할 디렉터리입니다. `dir2`는 어셈블리 참조를 검색할 하나 이상의 추가 디렉터리입니다. 이름 사이에 공백 없이 디렉터리 이름을 쉼표로 구분합니다. 컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.  

1. 현재 작업 디렉터리입니다.
1. 공용 언어 런타임 시스템 디렉터리입니다.
1. **AdditionalLibPaths** 로 지정된 디렉터리.
1. LIB 환경 변수로 지정된 디렉터리입니다.

**Reference** 를 사용하여 어셈블리 참조를 지정합니다. **AdditionalLibPaths** 는 누적됩니다. 두 번 이상 지정하면 이전 값에 추가됩니다. 종속 어셈블리의 경로가 어셈블리 매니페스트에 지정되지 않았으므로 애플리케이션이 전역 어셈블리 캐시에서 어셈블리를 찾아 사용합니다. 어셈블리를 참조하는 컴파일러는 공용 언어 런타임이 런타임에 어셈블리를 찾아 로드할 수 있음을 의미하지 않습니다. 런타임에서 참조된 어셈블리를 검색하는 방법에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.  

## <a name="generatefullpaths"></a>GenerateFullPaths

**GenerateFullPaths** 옵션을 사용하면 컴파일러에서는 컴파일 오류 및 경고 목록을 만들 때 파일의 전체 경로를 지정합니다.
  
```Xml
<GenerateFullPaths>true</GenerateFullPaths>
```

기본적으로 컴파일 도중 발생하는 오류와 경고에서는 오류가 발견된 파일의 이름을 지정합니다. **GenerateFullPaths** 옵션을 사용하면 컴파일러에서는 파일의 전체 경로를 지정합니다. 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.

## <a name="preferreduilang"></a>PreferredUILang

**PreferredUILang** 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지 등의 출력을 표시하는 언어를 지정할 수 있습니다.

```xml
<PreferredUILang>language</PreferredUILang>
```

여기서 `language`는 컴파일러 출력에 사용할 언어의 [언어 이름](/windows/desktop/Intl/language-names)입니다. **PreferredUILang** 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지와 기타 명령줄 출력에 사용할 언어를 지정할 수 있습니다. 해당 언어의 언어 팩이 설치되지 않은 경우 운영 체제의 언어 설정이 대신 사용됩니다.

## <a name="baseaddress"></a>BaseAddress

**BaseAddress** 옵션을 사용하면 DLL을 로드할 기본 기준 주소를 지정할 수 있습니다. 이 옵션을 사용하는 시기와 이유에 대한 자세한 내용은 [Larry Osterman's WebLog](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system)를 참조하세요.

```xml
<BaseAddress>address</BaseAddress>
```

여기서 `address`는 DLL의 기준 주소입니다. 이 주소는 10진수, 16진수 또는 8진수 숫자로 지정할 수 있습니다. DLL의 기본 기준 주소는 .NET 공용 언어 런타임에서 설정됩니다. 이 주소의 하위 단어는 반올림됩니다. 예를 들어 `0x11110001`을 지정하면 `0x11110000`으로 반올림됩니다. DLL에 대한 서명 프로세스를 완료하려면 SN.EXE에 -R 옵션을 사용합니다.

## <a name="checksumalgorithm"></a>ChecksumAlgorithm

이 옵션은 PDB에서 원본 파일을 인코딩하는 데 사용하는 체크섬 알고리즘을 제어합니다.

```xml
<ChecksumAlgorithm>algorithm</ChecksumAlgorithm>
```

`algorithm`은 `SHA1`(기본값) 또는 `SHA256` 중 하나여야 합니다.

## <a name="codepage"></a>CodePage

이 옵션은 필수 페이지가 시스템에 대한 현재 기본 코드 페이지가 아닌 경우 컴파일 중에 사용할 코드 페이지를 지정합니다.
  
```xml
<CodePage>id</CodePage>
```

여기서 `id`는 컴파일에 있는 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다. 컴파일러는 먼저 모든 소스 파일을 UTF-8로 해석하려고 합니다. 소스 코드 파일이 UTF-8 이외의 인코딩에 있고 7비트 ASCII 문자가 아닌 문자를 사용하는 경우 **CodePage** 옵션을 통해 사용할 코드 페이지를 지정합니다. **CodePage** 는 컴파일에 있는 모든 소스 코드 파일에 적용됩니다. 시스템에서 지원되는 코드 페이지를 찾는 방법에 대한 자세한 내용은 [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo)를 참조하세요.

## <a name="utf8output"></a>Utf8Output

**Utf8Output** 옵션은 UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.

```xml
<Utf8Output>true</Utf8Output>
```

일부 국제 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시되지 않을 수 있습니다. **Utf8Output** 을 사용하고 컴파일러 출력을 파일로 리디렉션합니다.

## <a name="filealignment"></a>FileAlignment

**FileAlignment** 옵션을 사용하면 출력 파일의 섹션 크기를 지정할 수 있습니다. 유효한 값은 512, 1024, 2048, 4096 및 8192입니다. 이러한 값은 바이트 단위입니다.

```xml
<FileAlignment>number</FileAlignment>
```

Visual Studio에서 프로젝트에 대한 **빌드** 속성의 **고급** 페이지에서 **FileAlignment** 옵션을 설정합니다. 각 섹션은 **FileAlignment** 값의 배수인 경계에 맞춰집니다. 고정된 기본값이 없습니다. **FileAlignment** 를 지정하지 않으면 공용언어 런타임에서 컴파일 시간에 기본값을 선택합니다. 섹션 크기를 지정하면 출력 파일의 크기에 영향을 줍니다. 섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다. 출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](/cpp/build/reference/dumpbin-options)을 사용하세요.

## <a name="errorendlocation"></a>ErrorEndLocation

컴파일러에게 각 오류의 끝 위치에 해당하는 줄과 열을 출력하도록 지시합니다.

```xml
<ErrorEndLocation>filename</ErrorEndLocation>
```

기본적으로 컴파일러는 모든 오류 및 경고에 대한 시작 위치를 원본에 기록합니다. 이 옵션을 true로 설정하면 컴파일러는 각 오류 및 경고에 대한 시작 및 끝 위치를 모두 씁니다.

## <a name="nostandardlib"></a>NoStandardLib

**NoStandardLib** 를 사용하면 전체 시스템 네임스페이스를 정의하는 mscorlib.dll을 가져올 수 없습니다.

```xml
<NoStandardLib>true</NoStandardLib>
```

고유한 시스템 네임스페이스와 개체를 정의하거나 만들려면 이 옵션을 사용합니다. **NoStandardLib** 를 지정하지 않으면 mscorlib.dll을 프로그램으로 가져옵니다(`<NoStandardLib>false</NoStandardLib>` 지정과 동일함).

## <a name="subsystemversion"></a>SubsystemVersion

실행 파일이 실행되는 하위 시스템의 최소 버전을 지정합니다. 가장 일반적으로, 이 옵션을 사용하면 실행 파일이 이전 버전의 Windows에서 사용할 수 없는 보안 기능을 사용할 수 있습니다.

> [!NOTE]
> 하위 시스템 자체를 지정하려면 [**TargetType**](./output.md#targettype) 컴파일러 옵션을 사용합니다.

```xml
<SubsystemVersion>major.minor</SubsystemVersion>
```

`major.minor`는 주 버전과 부 버전의 점 표기법으로 표현된 하위 시스템의 필수 최소 버전을 지정됩니다. 예를 들어 Windows 7 이전 버전의 운영 체제에서는 애플리케이션을 실행할 수 없도록 지정할 수 있습니다. 이 문서의 뒷부분에 나오는 표에서 설명하는 것처럼 이 옵션의 값을 6.01로 설정합니다. `major` 및 `minor`의 값을 정수로 지정합니다. `minor` 버전에서 선행 0은 버전을 변경하지 않지만 후행 0은 버전을 변경합니다. 예를 들어 6.1과 6.01은 동일한 버전을 가리키지만 6.10은 다른 버전을 가리킵니다. 혼동을 피하기 위해 부 버전을 두 자리로 표현하는 것이 좋습니다.

다음 표에는 Windows의 일반적인 하위 시스템 버전이 나와 있습니다.

|Windows 버전|하위 시스템 버전|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|Windows 8|6.02|

**SubsystemVersion** 컴파일러 옵션의 기본값은 다음 목록의 조건에 따라 달라집니다.

- 다음 목록의 컴파일러 옵션이 설정된 경우 기본값은 6.02입니다.
  - [/target:appcontainerexe](./target-appcontainerexe-compiler-option.md)
  - [/target:winmdobj](./target-winmdobj-compiler-option.md)
  - [-platform:arm](./platform-compiler-option.md)
- MSBuild를 사용하고 .NET Framework 4.5를 대상으로 하며, 이 목록의 앞에서 지정된 컴파일러 옵션 중 하나를 설정하지 않은 경우 기본값은 6.00입니다.
- 앞의 조건 중 어느 것도 true가 아닌 경우 기본값은 4.00입니다.

## <a name="moduleassemblyname"></a>ModuleAssemblyName

*.netmodule* 에서 public이 아닌 형식에 액세스할 수 있는 어셈블리 이름을 지정합니다.

```xml
<ModuleAssemblyName>assembly_name</ModuleAssemblyName>
```

**ModuleAssemblyName** 은 *.netmodule* 을 빌드할 때와 다음 조건이 충족되는 경우 사용해야 합니다.

- *.netmodule* 은 기존 어셈블리의 public이 아닌 형식에 액세스해야 합니다.
- .netmodule을 빌드할 어셈블리의 이름을 알아야 합니다.
- 기존 어셈블리는 friend 어셈블리(friend assembly)에 *.netmodule* 을 빌드할 어셈블리에 대한 액세스를 부여합니다.

.netmodule 빌드 방법에 대한 자세한 내용은 **module** 의 [**TargetType**](output.md#targettype) 옵션을 참조하세요. friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.
