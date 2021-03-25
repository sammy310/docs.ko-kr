---
description: dotnet 애플리케이션에 포함된 Windows 리소스를 제어하는 C# 컴파일러 옵션입니다.
title: C# 컴파일러 옵션 - 리소스 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- Win32Resource compiler option [C#]
- Win32Icon compiler option [C#]
- Win32Manifest compiler option [C#]
- NoWin32Manifest compiler option [C#]
- Resources compiler option [C#]
- LinkResources compiler option [C#]
ms.openlocfilehash: fe2da8cae67bc597d2b84a395861a0e4c32c9d72
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482436"
---
# <a name="c-compiler-options-that-specify-resources"></a>리소스를 지정하는 C# 컴파일러 옵션

다음 옵션은 C# 컴파일러에서 Win32 리소스를 만들거나 가져오는 방법을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **Win32Resource** / `-win32res`: Win32 리소스 파일(.res)을 지정합니다.
- **Win32Icon** / `-win32icon`: 지정한 어셈블리 파일에서 메타데이터를 참조합니다.
- **Win32Manifest** / `-win32manifest`: Win32 매니페스트 파일(.xml)을 지정합니다.
- **NoWin32Manifest** / `-nowin32manifest`: 기본 Win32 매니페스트를 포함하지 마세요.
- **Resources** / `-resource`: 지정된 리소스(약식: /res)를 포함합니다.
- **LinkResources** / `-linkresources`: 지정된 리소스를 이 어셈블리에 연결합니다.

## <a name="win32resource"></a>Win32Resource

**Win32Resource** 옵션은 출력 파일에 Win32 리소스를 삽입합니다.

```xml
<Win32Resource>filename</Win32Resource>
```

`filename`은 출력 파일에 추가할 리소스 파일입니다. Win32 리소스는 파일 탐색기에서 애플리케이션을 식별하는 데 도움이 되는 버전 정보나 비트맵 (아이콘) 정보를 포함할 수 있습니다. 이 옵션을 지정하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 버전 정보를 생성합니다.

## <a name="win32icon"></a>Win32Icon

**Win32Icon** 옵션은 .ico 파일을 출력 파일에 삽입하여 파일 탐색기에서 출력 파일을 원하는 모양으로 표시합니다.
  
```xml
<Win32Icon>filename</Win32Icon>
```

`filename`은 출력 파일에 추가할 *.ico* 파일입니다. *.ico* 파일은 [리소스 컴파일러](/windows/desktop/menurc/resource-compiler)로 만들 수 있습니다. 리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 호출됩니다. *.ico* 파일은 *.rc* 파일에서 만들어집니다.

## <a name="win32manifest"></a>Win32Manifest

**Win32Manifest** 옵션을 사용하여 프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 애플리케이션 매니페스트 파일을 지정합니다.

```xml
<Win32Manifest>filename</Win32Manifest>
```

`filename`은 사용자 지정 매니페스트 파일의 이름과 위치입니다. 기본적으로 C# 컴파일러에는 "asInvoker"의 요청된 실행 수준을 지정하는 애플리케이션 매니페스트가 포함되어 있습니다. 실행 파일이 빌드된 동일한 폴더에 매니페스트를 만듭니다. 예를 들어 "highestAvailable" 또는 "requireAdministrator"의 요청된 실행 수준을 지정하기 위해 사용자 지정 매니페스트를 제공하려면 이 옵션을 사용하여 파일 이름을 지정합니다.

> [!NOTE]
> 이 옵션과 **Win32Resources** 옵션은 함께 사용할 수 없습니다. 같은 명령줄에서 두 옵션을 모두 사용하려고 하면 빌드 오류가 발생합니다.

요청된 실행 수준을 지정하는 애플리케이션 매니페스트가 없는 애플리케이션은 Windows의 사용자 계정 컨트롤 기능에 따라 파일 및 레지스트리 가상화의 적용을 받습니다. 자세한 내용은 [사용자 계정 컨트롤](/windows/access-protection/user-account-control/user-account-control-overview)을 참조하십시오.

다음 조건 중 하나라도 참인 경우 애플리케이션에 가상화가 적용됩니다.
  
- **NoWin32Manifest** 옵션을 사용하고 **Win32Resource** 옵션을 사용하여 이후 빌드 단계 또는 Windows Resource( *.res*) 파일의 일부로 매니페스트를 제공하지 않습니다.
- 요청한 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공합니다.

Visual Studio는 기본 *.manifest* 파일을 만들고 이를 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다. 텍스트 편집기에서 파일을 만들고 프로젝트에 파일을 추가하여 사용자 지정 매니페스트를 추가할 수 있습니다. 또는 **솔루션 탐색기** 에서 **프로젝트** 아이콘을 마우스 오른쪽 단추로 클릭하고 **새 항목 추가** 를 선택한 다음, **애플리케이션 매니페스트 파일** 을 선택할 수 있습니다. 신규 또는 기존 매니페스트 파일을 추가하면 **매니페스트** 드롭다운 목록에 나타납니다. 자세한 내용은 [프로젝트 디자이너, 애플리케이션 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.

**NoWin32Manifest** 옵션을 사용하여 애플리케이션 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다. 애플리케이션이 Windows Vista에서 파일 또는 레지스트리 가상화의 적용을 받도록 하려면 동일한 옵션을 사용합니다.
  
## <a name="nowin32manifest"></a>NoWin32Manifest

**NoWin32Manifest** 옵션을 사용하면 실행 파일에 애플리케이션 매니페스트를 포함하지 않도록 컴파일러에 지시할 수 있습니다.

```xml  
<NoWin32Manifest />
```

이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 애플리케이션 매니페스트를 제공하지 않으면 Windows Vista에서 애플리케이션에 가상화가 적용됩니다.

Visual Studio의 **애플리케이션 속성** 페이지에 있는 **매니페스트** 드롭다운 목록에서 **매니페스트 없이 애플리케이션 만들기** 옵션을 선택하여 이 옵션을 설정합니다. 자세한 내용은 [프로젝트 디자이너, 애플리케이션 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.

## <a name="resources"></a>리소스

출력 파일에 지정된 리소스를 포함합니다.

```xml
<Resources Include=filename>
  <LogicalName>identifier</LogicalName>
  <Access>accessibility-modifier</Access>
</Resources>
```

`filename`은 출력 파일에 포함할 .NET 리소스 파일입니다. `identifier`(선택 사항)는 리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다. 기본값은 파일 이름입니다. `accessibility-modifier`(선택 사항)는 리소스의 접근성(퍼블릭 또는 프라이빗)입니다. 기본값은 public입니다. 기본적으로 리소스는 C# 컴파일러를 사용하여 생성될 때 어셈블리에서 퍼블릭입니다. 리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다. `public` 또는 `private` 이외의 다른 접근성은 허용되지 않습니다. 예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 만들어진 .NET 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다. 자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요. 다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다. 출력 파일에 있는 리소스의 순서는 프로젝트 파일에 지정된 순서에 따라 결정됩니다.  
  
## <a name="linkresources"></a>LinkResources

출력 파일에 .NET 리소스에 대한 링크를 만듭니다. 리소스 파일은 출력 파일에 추가되지 않습니다. **LinkResources** 는 출력 파일에 리소스 파일을 포함하는 **Resource** 옵션과 다릅니다.

```xml
<LinkResources Include=filename>
  <LogicalName>identifier</LogicalName>
  <Access>accessibility-modifier</Access>
</LinkResources>
```

`filename`은 어셈블리에서 연결할 .NET 리소스 파일입니다. `identifier`(선택 사항)는 리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다. 기본값은 파일 이름입니다. `accessibility-modifier`(선택 사항)는 리소스의 접근성(퍼블릭 또는 프라이빗)입니다. 기본값은 public입니다. 기본적으로 연결된 리소스는 C# 컴파일러로 생성될 때 어셈블리에서 퍼블릭입니다. 리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다. `public` 또는 `private` 이외의 다른 한정자는 허용되지 않습니다. 예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 만들어진 .NET 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다. 자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요. 다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다. `filename`에 지정된 파일은 모든 형식일 수 있습니다. 예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다. 어셈블리 링커에서도 동일한 작업을 수행할 수 있습니다. 자세한 내용은 [Al.exe(어셈블리 링커)](../../../framework/tools/al-exe-assembly-linker.md) 및 [어셈블리 및 전역 어셈블리 캐시 사용](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)을 참조하세요.
