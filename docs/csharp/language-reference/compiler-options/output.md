---
description: 컴파일러 출력을 제어하는 C# 컴파일러 옵션입니다. 이러한 옵션은 컴파일에서 어셈블리 생성을 제어합니다.
title: 'C # 컴파일러 옵션 - 출력 옵션'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- DocumentationFile compiler option [C#]
- OutputAssembly compiler option [C#]
- PlatformTarget compiler option [C#]
- ProduceReferenceAssembly compiler option [C#]
- TargetType compiler option [C#]
ms.openlocfilehash: 2d8b7edbf970875d7300a394ab75756c1316ac9d
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482444"
---
# <a name="c-compiler-options-that-control-compiler-output"></a>컴파일러 출력을 제어하는 C# 컴파일러 옵션

다음 옵션은 컴파일러 출력 생성을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **DocumentationFile** / `-doc`: `///` 주석에서 XML 문서 파일을 생성합니다.
- **OutputAssembly** / `-out`: 출력 어셈블리 파일을 지정합니다.
- **PlatformTarget** / `-platform`: 대상 플랫폼 CPU를 지정합니다.
- **ProduceReferenceAssembly** / `-refout`: 참조 어셈블리를 생성합니다.
- **TargetType** `-target`: 출력 어셈블리의 유형을 지정합니다.

## <a name="documentationfile"></a>DocumentationFile

**DocumentationFile** 옵션을 사용하면 XML 파일에 문서 주석을 삽입할 수 있습니다. 코드를 문서화하는 방법에 대한 자세한 내용은 [문서 주석에 대한 권장 태그](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)를 참조하세요. 값은 출력 XML 파일의 경로를 지정합니다. XML 파일에는 컴파일의 소스 코드 파일에 주석이 포함되어 있습니다.

```xml
<DocumentationFile>path/to/file.xml</DocumentationFile>
```

주 또는 최상위 문이 포함된 소스 코드 파일이 먼저 XML로 출력됩니다. 생성된 .xml 파일을 [IntelliSense](/visualstudio/ide/using-intellisense)와 함께 사용하는 경우가 많습니다. *.xml* 파일 이름은 어셈블리 이름과 동일해야 합니다. *.xml* 파일은 어셈블리와 동일한 디렉터리에 있어야 합니다. 어셈블리가 Visual Studio 프로젝트에서 참조되면 *.xml* 파일도 검색됩니다. 코드 주석을 생성하는 방법에 대한 자세한 내용은 [코드 주석 제공](/visualstudio/ide/reference/generate-xml-documentation-comments)을 참조하세요. [`<TargetType:Module>`](#targettype)을 사용하여 컴파일하지 않으면 `file`은 파일의 출력 파일에 대한 어셈블리 매니페스트를 포함하는 파일의 이름을 지정하는 `<assembly>` 및 `</assembly>` 태그를 포함합니다. 예제는 [XML 설명서 기능을 사용하는 방법](../../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)을 참조하세요.

> [!NOTE]
> **DocumentationFile** 옵션은 프로젝트의 모든 파일에 적용됩니다. 특정 파일 또는 코드 섹션에 대한 문서 주석 관련 경고를 사용하지 않으려면 [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md)을 사용하세요.

## <a name="outputassembly"></a>OutputAssembly

**OutputAssembly** 옵션은 출력 파일의 이름을 지정합니다. 출력 경로는 컴파일러 출력이 배치되는 폴더를 지정합니다.

```xml
<OutputAssembly>folder</OutputAssembly>
```

만들려는 파일의 전체 이름과 확장명을 지정합니다. 출력 파일의 이름을 지정하지 않으면 MSBuild는 프로젝트 이름을 사용하여 출력 어셈블리의 이름을 지정합니다. 이전 스타일 프로젝트는 다음 규칙을 사용합니다.

- .exe는 `Main` 메서드 또는 최상위 문이 포함된 소스 코드 파일에서 해당 이름을 가져옵니다.  
- .dll 또는 netmodule은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.

컴파일의 일부로 생성된 모든 모듈은 컴파일할 때 함께 생성된 어셈블리와 연결된 파일이 됩니다. 연결된 파일을 보려면 [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리 매니페스트를 확인합니다.

exe가 [friend 어셈블리](../../../standard/assembly/friend.md)의 대상이 되려면 **OutputAssembly** 컴파일러 옵션이 필요합니다.

## <a name="platformtarget"></a>PlatformTarget

어셈블리를 실행할 수 있는 CLR 버전을 지정합니다.

```xml
<PlatformTarget>anycpu</PlatformTarget>
```

- **anycpu**(기본값)는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다. 애플리케이션은 가능할 때마다 64비트로 실행되고 해당 모드를 사용할 수 있을 때만 32비트로 전환됩니다.
- **anycpu32bitpreferred** 는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다. 애플리케이션은 64비트와 32비트 애플리케이션을 모두 지원하는 시스템에서 32비트로 실행됩니다. .NET Framework 4.5 이상을 대상으로 하는 프로젝트에 대해서만 이 옵션을 지정할 수 있습니다.
- **ARM** 은 ARM(고급 RISC 컴퓨터) 프로세서가 있는 컴퓨터에서 실행할 어셈블리를 컴파일합니다.
- **ARM64** 는 A64 명령 집합을 지원하는 ARM(고급 RISC 머신) 프로세서가 있는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.
- **x64** 는 AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.
- **x86** 은 32비트, x86 호환 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.
- **Itanium** 은 Itanium 프로세서 탑재 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.

64비트 Windows 운영 체제:

- **x86** 으로 컴파일된 어셈블리는 WOW64 아래에서 실행되는 32비트 CLR에서 실행됩니다.
- **anycpu** 로 컴파일된 DLL은 해당 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.
- **anycpu** 로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.
- **anycpu32bitpreferred** 로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.

**anycpu32bitpreferred** 설정은 실행 파일(.EXE)에 대해서만 유효하고 .NET Framework 4.5 이상이 필요합니다. Windows 64비트 운영 체제에서 실행할 애플리케이션을 개발하는 방법에 대한 자세한 내용은 [64비트 애플리케이션](../../../framework/64-bit-apps.md)을 참조하세요.

Visual Studio의 프로젝트에 대한 **빌드** 속성 페이지에서 **PlatformTarget** 옵션을 설정합니다.

**anycpu** 의 동작에는 .NET Core 및 .NET 5 이상 릴리스에 대한 몇 가지 추가 뉘앙스가 있습니다. **anycpu** 를 설정할 때 앱을 게시하고 x86 `dotnet.exe` 또는 x64 `dotnet.exe`로 실행합니다. 자체 포함 앱의 경우 `dotnet publish` 단계에서 구성 RID에 대한 실행 파일을 패키징합니다.

## <a name="producereferenceassembly"></a>ProduceReferenceAssembly

**ProduceReferenceAssembly** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다. Emit API에서 `metadataPeStream`으로 전환됩니다. `filepath`는 참조 어셈블리의 경로를 지정합니다. 일반적으로 주 어셈블리의 경로와 일치해야 합니다. 권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리를 기준으로 “ref/” 하위 폴더에 참조 어셈블리를 배치하는 것입니다.

```xml
<ProduceReferenceAssembly>filepath</ProduceReferenceAssembly>
```

참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다. 여기에는 빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언이 포함됩니다. 참조 어셈블리는 모든 멤버 구현 및 프라이빗 멤버 선언을 제외합니다. 이러한 멤버는 해당 API 계약에 뚜렷한 영향을 주지 않습니다. 자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.

**ProduceReferenceAssembly** 및 [**ProduceOnlyReferenceAssembly**](./code-generation.md#produceonlyreferenceassembly) 옵션은 함께 사용할 수 없습니다.

## <a name="targettype"></a>TargetType

**TargetType** 컴파일러 옵션은 다음 양식 중 하나로 지정할 수 있습니다.  
  
- **library**: 코드 라이브러리를 만듭니다. **library** 는 기본값입니다.
- **exe**: .exe 파일을 만듭니다.  
- **module**: 모듈을 만듭니다.  
- **winexe**: Windows 프로그램을 만듭니다.
- **winmdobj**: 중간 *.winmdobj* 파일을 만듭니다.
- **appcontainerexe**: Windows 8.x 스토어 앱용 .exe 파일을 만듭니다.
  
> [!NOTE]
> .NET Framework 대상의 경우 **module** 을 지정하지 않는 한 이 옵션을 사용하면 .NET Framework 어셈블리 매니페스트가 출력 파일에 배치됩니다. 자세한 내용은 [.NET의 어셈블리](../../../standard/assembly/index.md) 및 [공통 특성](../attributes/global.md)을 참조하세요.

```xml
<TargetType>library</TargetType>
```

컴파일러는 컴파일당 하나의 어셈블리 매니페스트만 만듭니다. 컴파일의 모든 파일에 대한 정보가 어셈블리 매니페스트에 배치됩니다. 명령줄에서 여러 출력 파일을 생성하는 경우 하나의 어셈블리 매니페스트만 만들 수 있으며, 명령줄에 지정된 첫 번째 출력 파일로 이동해야 합니다.

어셈블리를 만드는 경우 <xref:System.CLSCompliantAttribute> 특성을 사용하여 코드의 전체 또는 일부를 CLS 규격으로 지정할 수 있습니다.

### <a name="library"></a>라이브러리

**library** 옵션을 사용하면 컴파일러가 실행 파일(EXE) 대신 DLL(동적 연결 라이브러리)을 만듭니다. DLL은 *.dll* 확장명으로 생성됩니다. [**OutputAssembly**](#outputassembly) 옵션을 사용하여 달리 지정되지 않는 한 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다. *.dll* 파일을 빌드하는 경우에는 [`Main`](../../programming-guide/main-and-command-args/index.md) 메서드가 필요하지 않습니다.

### <a name="exe"></a>exe

**exe** 옵션을 사용하면 컴파일러가 콘솔 애플리케이션 실행 파일(EXE)을 만듭니다. 실행 파일은 .exe 확장명으로 생성됩니다. **winexe** 를 사용하여 Windows 프로그램 실행 파일을 만듭니다. [**OutputAssembly**](#outputassembly) 옵션을 사용하여 달리 지정하지 않는 한 출력 파일 이름은 진입점을 포함하는 입력 파일의 이름을 사용합니다([Main](../../programming-guide/main-and-command-args/index.md) 메서드 또는 최상위 문). .exe 파일로 컴파일되는 소스 코드 파일에는 진입점이 하나만 필요합니다. [**StartupObject**](./advanced.md#mainentrypoint-or-startupobject) 컴파일러 옵션을 사용하면 코드에 `Main` 메서드를 포함하는 클래스가 둘 이상 있는 경우 `Main` 메서드를 포함하는 클래스를 지정할 수 있습니다.  

### <a name="module"></a>모듈(module)

이 옵션은 컴파일러에서 어셈블리 매니페스트를 생성하지 않도록 합니다. 기본적으로 이 옵션으로 컴파일하여 생성되는 출력 파일의 확장명은 *.netmodule* 입니다. 어셈블리 매니페스트가 없는 파일은 .NET 런타임에서 로드할 수 없습니다. 그러나 이러한 파일은 [**AddModules**](inputs.md#addmodules)를 사용하여 어셈블리의 어셈블리 매니페스트에 통합할 수 있습니다. 둘 이상의 모듈이 단일 컴파일에서 생성될 경우 한 모듈의 [내부](../keywords/internal.md) 형식을 컴파일에 포함된 다른 모듈에서 사용할 수 있습니다. 한 모듈의 코드가 다른 모듈의 `internal` 형식을 참조하는 경우 [**AddModules**](inputs.md#addmodules)를 통해 두 모듈을 모두 어셈블리 매니페스트에 통합해야 합니다. Visual Studio 개발 환경에서는 모듈을 만들 수 없습니다.

### <a name="winexe"></a>winexe

**winexe** 옵션을 사용하면 컴파일러가 Windows 프로그램 실행 파일(EXE)을 만듭니다. 실행 파일은 .exe 확장명으로 생성됩니다. Windows 프로그램은 .NET 라이브러리나 Windows API를 통해 사용자 인터페이스를 제공하는 프로그램입니다. **exe** 를 사용하여 콘솔 애플리케이션을 만듭니다. [**OutputAssembly**](#outputassembly) 옵션을 사용하여 달리 지정하지 않는 한 [`Main`](../../programming-guide/main-and-command-args/index.md) 메서드가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다. .exe 파일로 컴파일되는 소스 코드 파일에 `Main` 메서드가 하나만 있어야 합니다. [**StartupObject**](./advanced.md#mainentrypoint-or-startupobject) 옵션을 사용하면 코드에 `Main` 메서드를 포함하는 클래스가 둘 이상 있는 경우 `Main` 메서드를 포함하는 클래스를 지정할 수 있습니다.

### <a name="winmdobj"></a>winmdobj

**winmdobj** 옵션을 사용하는 경우 컴파일러는 Windows 런타임 이진( *.winmd*) 파일로 변환할 수 있는 중간 *.winmdobj* 파일을 만듭니다. 그러면 관리형 언어 프로그램뿐만 아니라 JavaScript 및 C++ 프로그램에서도 *.winmd* 파일을 사용할 수 있습니다.

**winmdobj** 설정이 컴파일러에 중간 모듈이 필요하다는 신호를 보냅니다. 그러면 <xref:Microsoft.Build.Tasks.WinMDExp> 내보내기 도구를 통해 *.winmdobj* 파일을 공급하여 Windows 메타데이터( *.winmd*) 파일을 만들 수 있습니다. *.winmd* 파일에는 원본 라이브러리의 코드와 JavaScript 또는 C++ 및 Windows 런타임에서 사용하는 WinMD 메타데이터가 모두 들어 있습니다. **winmdobj** 컴파일러 옵션을 사용하여 컴파일된 파일의 출력은 WimMDExp 내보내기 도구의 입력으로만 사용됩니다. *.winmdobj* 파일 자체는 직접 참조되지 않습니다. [**OutputAssembly**](#outputassembly) 옵션을 사용하지 않으면 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다. [`Main`](../../programming-guide/main-and-command-args/index.md) 메서드는 필요하지 않습니다.

### <a name="appcontainerexe"></a>appcontainerexe

**appcontainerexe** 컴파일러 옵션을 사용하면 컴파일러는 앱 컨테이너에서 실행해야 하는 Windows 실행 파일( *.exe*)을 만듭니다. 이 옵션은 [-target:winexe](./target-winexe-compiler-option.md)와 같지만, Windows 8.x 스토어 앱을 위해 설계되었습니다.

이 옵션은 앱이 앱 컨테이너에서 실행되도록 하기 위해 PE([이식 가능 파일](/windows/desktop/Debug/pe-format))에 비트를 설정합니다. 해당 비트가 설정된 경우 CreateProcess 메서드가 응용 프로그램 밖에서 실행 파일을 실행하려고 시도하면 오류가 발생합니다. [**OutputAssembly**](#outputassembly) 옵션을 사용하지 않으면 [`Main`](../../programming-guide/main-and-command-args/index.md) 메서드가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.
