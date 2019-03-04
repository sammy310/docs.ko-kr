---
title: .NET 어셈블리
ms.date: 07/10/2018
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
---
# <a name="assemblies-in-net"></a>.NET 어셈블리

어셈블리는 .NET 기반 애플리케이션에 대한 배포, 버전 제어, 재사용, 활성화 범위 및 보안 권한의 기본 단위를 형성합니다. 어셈블리는 실행 파일(.exe) 또는 동적 연결 라이브러리(.dll) 파일의 형태를 가지며 .NET 애플리케이션의 구성 요소입니다. 어셈블리는 형식 구현을 인식하는 데 필요한 정보와 함께 공용 언어 런타임을 제공합니다. 어셈블리를 함께 작동하도록 빌드되고 논리적 기능 단위를 형성하는 리소스 및 형식 컬렉션으로 생각할 수 있습니다.  
  
 .NET Core 및.NET Framework에서 하나 이상의 소스 코드 파일에서 어셈블리를 빌드할 수 있습니다. .NET Framework에서, 어셈블리 모듈을 하나 이상 포함할 수 있습니다. 따라서 여러 개별 개발자가 하나의 어셈블리를 만들기 위해 결합된 별도의 소스 코드 파일이나 모듈에서 작업하는 방식으로 대규모 프로젝트를 계획할 수 있습니다. 모듈에 대한 자세한 내용은 [ 다중 파일 어셈블리 빌드](../../framework/app-domains/how-to-build-a-multifile-assembly.md) 항목을 참조하세요.
  
 어셈블리에는 다음과 같은 속성이 있습니다.  
  
-   어셈블리는 .exe 또는 .dll 파일로 구현됩니다.  
  
-   .NET Framework를 대상으로 하는 라이브러리에 어셈블리를 [전역 어셈블리 캐시](../../framework/app-domains/gac.md)에 저장하면 애플리케이션 간에 공유할 수 있습니다. 어셈블리를 전역 어셈블리 캐시에 넣으려면 강력한 이름이 지정되어야 합니다. 자세한 내용은 [강력한 이름의 어셈블리](../../framework/app-domains/strong-named-assemblies.md)를 참조하세요.  
  
-   어셈블리는 필요한 경우에만 메모리에 로드됩니다. 사용되지 않을 때는 로드되지 않습니다. 즉, 어셈블리는 대규모 프로젝트에서 리소스를 관리하는 효율적인 방법일 수 있습니다.  
  
-   리플렉션을 사용하여 프로그래밍 방식으로 어셈블리에 대한 정보를 얻을 수 있습니다. 자세한 내용은 [리플렉션(C#)](../../csharp/programming-guide/concepts/reflection.md) 또는 [Reflection(Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md)을 참조하세요.   
  
-   어셈블리를 호출하여 메소드 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>을 검사할 수 있습니다.  
  
## <a name="assembly-manifest"></a>어셈블리 매니페스트  
 모든 어셈블리 내에는 *어셈블리 매니페스트*가 있습니다. 목차와 마찬가지로, 어셈블리 매니페스트에는 다음이 포함됩니다.  
  
-   어셈블리의 ID(해당 이름 및 버전).  
  
-   어셈블리를 구성하는 다른 모든 파일을 설명하는 파일 테이블(예: 사용자의 .exe 또는 .dll 파일이 의존하는 사용자가 만든 다른 모든 어셈블리 또는 비트맵이나 추가 정보 파일)  
  
-   *어셈블리 참조 목록*: 누군가가 만들었을 수 있으며 사용자의 애플리케이션에 필요한 .dlls 또는 기타 파일을 비롯한 모든 외부 종속성 목록 어셈블리 참조는 global 및 private 개체에 대한 참조를 포함합니다. 전역 개체는 다른 모든 애플리케이션에서 사용할 수 있습니다. .NET Core에서는 특정 .NET Core 런타임과 결합됩니다. .NET Framework에서는 전역 어셈블리 캐시에 있습니다. <xref:System.IO?displayProperty=nameWithType> 네임스페이스는 전역 어셈블리 캐시의 어셈블리에 대한 예입니다. private 개체는 애플리케이션이 설치된 디렉터리와 같거나 낮은 수준에 있는 디렉터리에 있어야 합니다.  
  
 어셈블리는 콘텐츠, 버전 관리 및 종속성에 대한 정보를 포함하므로 사용한 애플리케이션은 제대로 작동하기 위해 Windows 레지스트리 값에 의존하지 않습니다. 어셈블리는 .dll 충돌을 줄이고 더 안정적이고 배포하기 쉬운 애플리케이션을 구현합니다. 많은 경우에 해당 파일을 대상 컴퓨터에 복사하는 것만으로 .NET 기반 애플리케이션을 설치할 수 있습니다. 자세한 내용은 [어셈블리 매니페스트](../../framework/app-domains/assembly-manifest.md)를 참조하세요.  
  
## <a name="adding-a-reference-to-an-assembly"></a>어셈블리에 대한 참조 추가  
 어셈블리를 사용하려면 해당 참조를 추가해야 합니다. 그런 다음 C#의 [using 지시문](../../csharp/language-reference/keywords/using-directive.md) 또는 Visual Basic의 [Imports 지시문](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 사용하여 사용할 항목의 네임스페이스를 선택할 수 있습니다. 어셈블리를 참조하고 가져오면 해당 코드가 소스 파일에 속해 있는 것처럼 해당 네임스페이스의 액세스 가능한 모든 유형, 속성, 메서드 및 다른 멤버를 애플리케이션에서 사용할 수 있습니다.  
 
> [!NOTE]
> .NET 클래스 라이브러리의 대부분의 어셈블리는 자동으로 참조됩니다. 경우에 따라, 하지만, 시스템 어셈블리를 자동으로 참조할 수 없습니다. .NET Core에서는 Visual Studio에서 NuGet Package Manager를 사용하여 어셈블리가 포함된 NuGet 패키지에 대한 참조를 추가하거나, *.csproj 또는 *.vbproj 프로젝트에 대한 [<PackageReference>](../../core/tools/dependencies.md#the-new-packagereference-element) 요소를 어셈블리로 추가할 수 있습니다. .NET framework에서 Visual Studio의 **참조 추가** 대화 상자를 사용하거나 [C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md)의 `-reference` 명령줄 옵션 또는 [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md) 컴파일러를 사용하여 어셈블리에 대한 참조를 추가할 수 있습니다.
 
 C#에서는 단일 애플리케이션에서 동일한 어셈블리의 두 버전을 사용할 수도 있습니다. 자세한 내용은 [extern alias](../../csharp/language-reference/keywords/extern-alias.md)를 참조하세요.  
  
## <a name="creating-an-assembly"></a>어셈블리 만들기  
 Visual Studio에서 .NET Framework CLI(명령줄 인터페이스) 도구를 사용하여 명령줄에서 빌드하거나 명령줄 컴파일러로 .NET Framework 어셈블리를 빌드하여 애플리케이션을 컴파일하여 애플리케이션을 컴파일합니다. .NET CLI 도구를 사용하여 어셈블리를 빌드하는 방법에 대한 자세한 내용은 [.NET Core CLI(명령줄 인터페이스) 도구](../../core/tools/index.md)를 참조하세요. 명령줄 컴파일러를 사용하여 어셈블리를 빌드하려면 C#의 경우, [csc.exe로 명령줄 빌드](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) Visual Basic의 경우, [명령줄에서 빌드](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)를 참조하세요.  
  
> [!NOTE]
>  Visual Studio에서 어셈블리를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다.  

## <a name="see-also"></a>참고 항목

 - [.NET 어셈블리 파일 형식](file-format.md)
 - [공용 언어 런타임의 어셈블리](../../framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 - [Friend 어셈블리(C#)](../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 - [Friend 어셈블리(Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 - [방법: 어셈블리 로드 및 언로드(C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)  
 - [방법: 어셈블리 로드 및 언로드(Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)  
 - [방법: .NET Core에서 어셈블리 언로드 기능 사용 및 디버그](unloadability-howto.md)
 - [방법: 파일이 어셈블리인지 확인(C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)  
 - [방법: 파일이 어셈블리인지 확인(Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)  
