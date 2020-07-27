---
title: 참조 어셈블리
description: 라이브러리의 공용 API 화면만 포함하는 .NET에서 특수한 형식의 어셈블리인 참조 어셈블리에 대해 알아봅니다.
author: MSDN-WhiteKnight
ms.date: 09/12/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 43a9dab037f4d0f1926ff67f8f38eaa6734a6d67
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164525"
---
# <a name="reference-assemblies"></a>참조 어셈블리

*참조 어셈블리*는 라이브러리의 공용 API 화면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다. 빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다. 반면 일반 어셈블리는 *구현 어셈블리*라고 합니다.

참조 어셈블리는 실행을 위해 로드할 수 없지만 구현 어셈블리와 동일한 방식으로 컴파일러 입력으로 전달될 수 있습니다. 참조 어셈블리는 일반적으로 특정 플랫폼 또는 라이브러리의 SDK(소프트웨어 개발 키트)를 사용하여 배포됩니다.

참조 어셈블리를 사용하면 개발자는 해당 버전에 대한 전체 구현 어셈블리 없이도 특정 라이브러리 버전을 대상으로 하는 프로그램을 빌드할 수 있습니다. 컴퓨터에 최신 버전의 라이브러리만 있지만 해당 라이브러리의 이전 버전을 대상으로 하는 프로그램을 빌드하려고 한다고 가정해 봅니다. 구현 어셈블리에 대해 직접 컴파일하는 경우 이전 버전에서 사용할 수 없는 API 멤버를 예기치 않게 사용할 수 있습니다. 대상 컴퓨터에서 프로그램을 테스트하는 경우에만 이 오류를 찾을 수 있습니다. 이전 버전의 참조 어셈블리에 대해 컴파일하는 경우 컴파일 시간 오류가 즉시 발생합니다.

또한, 참조 어셈블리는 계약, 즉 구체적인 구현 어셈블리에 해당하지 않는 API 집합을 나타낼 수 있습니다. *계약 어셈블리*라고 하는 이러한 참조 어셈블리는 동일한 API 집합을 지원하는 여러 플랫폼을 대상으로 지정하는 데 사용될 수 있습니다. 예를 들어 .NET Standard는 서로 다른 .NET 플랫폼 간에 공유되는 공통 API 집합을 나타내는 계약 어셈블리 *netstandard.dll*을 제공합니다. 이러한 API의 구현은 .NET Framework의 *mscorlib.dll* 또는 .NET Core의 *System.Private.CoreLib.dll*과 같이 다른 플랫폼의 다른 어셈블리에 포함되어 있습니다. .NET Standard를 대상으로 하는 라이브러리는 .NET Standard를 지원하는 모든 플랫폼에서 실행될 수 있습니다.

## <a name="using-reference-assemblies"></a>참조 어셈블리 사용

프로젝트에서 특정 API를 사용하려면 해당 어셈블리에 대한 참조를 추가해야 합니다. 구현 어셈블리 또는 참조 어셈블리에 참조를 추가할 수 있습니다. 참조 어셈블리를 사용할 수 있을 때마다 이 어셈블리를 사용하는 것이 좋습니다. 이렇게 하면 API 디자이너가 사용하도록 지정된 대상 버전에서 지원되는 API 멤버만 사용하게 됩니다. 참조 어셈블리를 사용하면 구현 세부 정보에 대한 종속성을 사용하지 않게 됩니다.

.NET Framework 라이브러리의 참조 어셈블리는 대상 팩과 함께 배포됩니다. 독립 실행형 설치 관리자를 다운로드하거나 Visual Studio 설치 관리자에서 구성 요소를 선택하여 가져올 수 있습니다. 자세한 내용은 [개발자용 .NET Framework 설치](../../framework/install/guide-for-developers.md)를 참조하세요. .NET Core 및 .NET Standard의 경우 참조 어셈블리는 필요에 따라(NuGet을 통해) 자동으로 다운로드되고 참조됩니다. .NET Core 3.0 이상의 경우 핵심 프레임워크의 참조 어셈블리는 [Microsoft.NETCore.App.Ref](https://www.nuget.org/packages/Microsoft.NETCore.App.Ref) 패키지에 있습니다([Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) 패키지는 3.0 이전 버전에 대신 사용됨).

**참조 추가** 대화 상자를 사용하여 Visual Studio에서 .NET Framework 어셈블리에 대한 참조를 추가하는 경우 목록에서 어셈블리를 선택하면 Visual Studio는 프로젝트에서 선택한 대상 프레임워크 버전에 해당하는 참조 어셈블리를 자동으로 찾습니다. [참조](/visualstudio/msbuild/common-msbuild-project-items#reference) 프로젝트 항목을 사용하여 MSBuild 프로젝트에 참조를 직접 추가하는 경우에도 동일하게 적용됩니다. 전체 파일 경로가 아닌 어셈블리 이름만 지정하면 됩니다. `-reference` 컴파일러 옵션([C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md) 및 [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md))을 사용하거나 Roslyn API의 <xref:Microsoft.CodeAnalysis.Compilation.AddReferences%2A?displayProperty=nameWithType> 메서드를 사용하여 명령줄에서 이러한 어셈블리에 대한 참조를 추가할 때 올바른 대상 플랫폼 버전에 대한 참조 어셈블리 파일을 수동으로 지정해야 합니다. .NET Framework 참조 어셈블리 파일은 *%ProgramFiles(x86)%\\Reference Assemblies\\Microsoft\\Framework\\.NETFramework* 디렉터리에 있습니다. .NET Core의 경우 `PreserveCompilationContext` 프로젝트 속성을 `true`로 설정하여 게시 작업이 대상 플랫폼의 참조 어셈블리를 출력 디렉터리의 *publish/refs* 하위 디렉터리로 복사하도록 할 수 있습니다. 그런 다음 이러한 참조 어셈블리 파일을 컴파일러에 전달할 수 있습니다. [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/) 패키지에서 `DependencyContext`를 사용하면 해당 경로를 찾을 수 있습니다.

여기에는 구현이 포함되어 있지 않으므로 참조 어셈블리를 로드하여 실행할 수 없습니다. 실행하려고 하면 <xref:System.BadImageFormatException?displayProperty=nameWithType>이 발생합니다. 참조 어셈블리의 내용을 검사하려면 .NET Framework(<xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> 메서드 사용)의 리플렉션 전용 컨텍스트나 .NET Core의 <xref:System.Reflection.MetadataLoadContext>에 로드하면 됩니다.

## <a name="generating-reference-assemblies"></a>참조 어셈블리 생성

라이브러리 사용자가 여러 버전의 라이브러리에 대해 프로그램을 빌드해야 하는 경우 라이브러리의 참조 어셈블리를 생성하는 것이 유용할 수 있습니다. 이러한 모든 버전에 대한 구현 어셈블리를 배포하는 것은 크기가 크기 때문에 실용적이지 않을 수 있습니다. 참조 어셈블리는 크기가 작으므로 라이브러리 SDK의 일부로 배포하면 다운로드 크기가 줄어들고 디스크 공간이 절약됩니다.

여러 클래스 라이브러리로 구성된 대규모 솔루션의 경우 IDE와 빌드 도구는 참조 어셈블리를 활용하여 빌드 시간을 단축할 수 있습니다. 일반적으로 증분 빌드 시나리오에서는 프로젝트가 종속된 어셈블리를 포함하여 입력 파일이 변경될 때 프로젝트가 다시 빌드됩니다. 구현 어셈블리는 프로그래머가 모든 멤버의 구현을 변경할 때마다 변경됩니다. 참조 어셈블리는 공용 API가 영향을 받는 경우에만 변경됩니다. 따라서 구현 어셈블리 대신 참조 어셈블리를 입력 파일로 사용하면 경우에 따라 종속 프로젝트의 빌드를 건너뛸 수 있습니다.

다음과 같이 참조 어셈블리를 생성할 수 있습니다.

- MSBuild 프로젝트에서 [`ProduceReferenceAssembly`프로젝트 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 사용합니다.
- 명령줄에서 프로그램을 컴파일하는 경우 `-refonly` ([C#](../../csharp/language-reference/compiler-options/refonly-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refonly-compiler-option.md)) 또는 `-refout` ([C#](../../csharp/language-reference/compiler-options/refout-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refout-compiler-option.md)) 컴파일러 옵션을 지정합니다.
- Roslyn API를 사용하는 경우 <xref:Microsoft.CodeAnalysis.Compilation.Emit%2A?displayProperty=nameWithType> 메서드에 전달된 개체의 <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.EmitMetadataOnly?displayProperty=nameWithType>를 `true`로 설정하고 <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.IncludePrivateMembers?displayProperty=nameWithType>를 `false`로 설정합니다.

NuGet 패키지와 함께 참조 어셈블리를 배포하려는 경우 구현 어셈블리에 사용된 *lib\\* 하위 디렉터리 대신 패키지 디렉터리 아래의 *ref\\* 하위 디렉터리에 참조 어셈블리를 포함해야 합니다.

## <a name="reference-assemblies-structure"></a>참조 어셈블리 구조

참조 어셈블리는 관련 개념인 *메타데이터 전용 어셈블리*의 확장입니다. 메타데이터 전용 어셈블리에는 단일 `throw null` 본문으로 대체되는 메서드 본문이 있지만 익명 형식을 제외한 모든 멤버가 포함됩니다. 본문이 없는 경우와 대조적으로 `throw null` 본문을 사용하는 이유는 **PEVerify**가 실행 및 전달될 수 있도록 하여 메타데이터의 완전성을 검증하기 위한 것입니다.

참조 어셈블리는 메타데이터 프라이빗 어셈블리에서 메타데이터(전용 멤버)를 추가로 제거합니다.

- 참조 어셈블리에는 API 화면에 있어야 하는 항목에 대한 참조만 포함됩니다. 실제 어셈블리에는 특정 구현에 관련된 추가 참조가 포함될 수 있습니다. 예를 들어, `class C { private void M() { dynamic d = 1; ... } }`에 대한 참조 어셈블리는 `dynamic`에 필요한 형식을 참조하지 않습니다.
- 제거가 컴파일에 눈에 띄는 영향을 미치지 않을 경우 전용 함수-멤버(메서드, 속성 및 이벤트)가 제거됩니다. [InternalsVisibleTo](xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute) 특성이 없으면 내부 함수 멤버도 제거됩니다.

참조 어셈블리의 메타데이터는 다음 정보를 계속 유지합니다.

- 비공개 및 중첩 형식을 포함한 모든 형식.
- 모든 특성(내부 특성인 경우에도 해당).
- 모든 가상 메서드.
- 명시적 인터페이스 구현.
- 명시적으로 구현된 속성 및 이벤트(해당 접근자가 가상이기 때문).
- 구조체의 모든 필드.

참조 어셈블리에는 어셈블리 수준 [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) 특성이 포함됩니다. 이 특성을 소스에서 지정할 수 있습니다. 이렇게 하면 컴파일러가 특성을 합성할 필요가 없습니다. 이 특성으로 인해 런타임은 실행용 참조 어셈블리 로드를 거부합니다. 그러나 리플렉션 전용 모드에서 로드할 수 있습니다.

정확한 참조 어셈블리 구조 정보는 컴파일러 버전에 따라 다릅니다. 최신 버전은 공용 API 화면에 영향을 미치지 않는 것으로 확인되는 경우 더 많은 메타데이터를 제외하도록 선택할 수 있습니다.

> [!NOTE]
> 이 섹션의 정보는 C# 버전 7.1 또는 Visual Basic 버전 15.3부터 Roslyn 컴파일러가 생성한 참조 어셈블리에만 적용됩니다. .NET Framework 및 .NET Core 라이브러리의 참조 어셈블리 구조는 자체적으로 참조 어셈블리를 생성하는 메커니즘을 사용하므로 일부 세부 정보가 다를 수 있습니다. 예를 들어 `throw null` 본문이 아닌 완전히 빈 메서드 본문이 있을 수 있습니다. 그러나 일반적인 원칙은 여전히 적용됩니다. 사용 가능한 메서드 구현이 없고 공개 API 관점에서 관찰 가능한 영향을 미치는 멤버에 대한 메타데이터만 포함합니다.

## <a name="see-also"></a>참조

- [.NET 어셈블리](index.md)
- [Framework 대상 지정 개요](/visualstudio/ide/visual-studio-multi-targeting-overview)
- [방법: 참조 관리자를 사용하여 참조 추가 또는 제거](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)
