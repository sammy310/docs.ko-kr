---
description: 코드 생성을 제어하는 C# 컴파일러 옵션입니다. 옵션은 지정된 컴파일에 대해 컴파일러가 생성한 코드에 영향을 줍니다.
title: C# 컴파일러 옵션 - 코드 생성 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- DebugType compiler option [C#]
- Optimize compiler option [C#]
- Deterministic compiler option [C#]
- ProduceOnlyReferenceAssembly compiler option [C#]
ms.openlocfilehash: 6b66c50b408f9615bc3c63ab4dd46dbc4215c62f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482491"
---
# <a name="c-compiler-options-that-control-code-generation"></a>코드 생성을 제어하는 C# 컴파일러 옵션

다음 옵션은 컴파일러에 의한 코드 생성을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **DebugType** / `-debug`: 디버깅 정보를 내보내거나 내보내지 않습니다.
- **최적화** / `-optimize`: 최적화를 활성화합니다.
- **결정적** / `-deterministic`: 동일한 입력 소스에서 바이트 단위에 해당하는 출력을 생성합니다.
- **ProduceOnlyReferenceAssembly** / `-refonly`: 전체 어셈블리 대신 참조 어셈블리를 기본 출력으로 생성합니다.

## <a name="debugtype"></a>DebugType

**DebugType** 옵션을 사용하면 컴파일러에서 디버깅 정보를 생성하여 출력 파일에 넣습니다. 디버깅 정보는 기본적으로 *디버그* 빌드 구성에 추가됩니다. *릴리스* 빌드 구성의 경우 기본적으로 해제되어 있습니다.

```xml
<DebugType>pdbonly</DebugType>
```

C# 6.0부터 모든 컴파일러 버전은 *pdbonly* 와 *full* 간에 차이가 없습니다. *pdbonly* 를 선택합니다. *.pdb 파일* 의 위치를 변경하려면 [**PdbFile**](./advanced.md#pdbfile)을 참조하세요.

> [!IMPORTANT]
> 이 섹션은 C# 6.0 이전 버전의 컴파일러에만 적용됩니다.
> 이 요소의 값은 `full` 또는 `pdbonly`일 수 있습니다. *pdbonly* 를 지정하지 않은 경우 적용되는 *full* 인수를 통해 실행 중인 프로그램에 디버거를 연결할 수 있습니다. *pdbonly* 를 지정하면 디버거에서 프로그램이 시작되는 경우 소스 코드 디버깅이 허용되지만, 실행 중인 프로그램이 디버거에 연결되어 있을 때만 어셈블러가 표시됩니다. 디버그 빌드를 만들려면 이 옵션을 사용합니다. *Full* 을 사용하는 경우 JIT 최적화 코드의 속도와 크기에 영향을 미치며 *full* 을 사용하면 코드 품질에 약간의 영향을 미칩니다. 릴리스 코드를 생성하는 경우 *pdbonly* 를 사용하거나 PDB를 사용하지 않는 것이 좋습니다. *pdbonly* 및 *full* 간의 차이점 중 하나는 *full* 을 사용하는 경우 컴파일러가 <xref:System.Diagnostics.DebuggableAttribute>를 내보낸다는 것입니다. 이 특성은 JIT 컴파일러에 디버그 정보를 사용할 수 있음을 알리는 데 사용됩니다. 따라서 *full* 을 사용하는 경우 false로 설정된 <xref:System.Diagnostics.DebuggableAttribute>가 코드에 포함되어 있으면 오류가 발생합니다. 애플리케이션의 디버그 성능을 구성하는 방법에 대한 자세한 내용은 [쉽게 디버그할 수 있도록 이미지 만들기](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md)를 참조하세요.

## <a name="optimize"></a>최적화

**Optimize** 옵션은 컴파일러에서 더 작지만 빠르고 효율적인 출력 파일을 만들기 위해 수행하는 최적화 기능을 사용하거나 사용하지 않도록 설정합니다. *Optimize* 옵션은 *릴리스* 빌드 구성에 대해 기본적으로 사용하도록 설정되어 있습니다. *디버그* 빌드 구성의 경우 기본적으로 해제되어 있습니다.

```xml
<Optimize>true</Optimize>
```

Visual Studio의 프로젝트에 대한 **빌드** 속성 페이지에서 **Optimize** 옵션을 설정합니다.

또한 **Optimize** 는 런타임 시 코드를 최적화하도록 공용 언어 런타임에 지시합니다. 최적화는 기본적으로 사용되지 않습니다. 최적화를 사용하려면 **Optimize+** 를 지정합니다. 어셈블리에서 사용할 모듈을 빌드하는 경우 어셈블리에서 사용하는 것과 동일한 **Optimize** 설정을 사용합니다. **Optimize** 및 [**Debug**](#debugtype) 옵션을 결합할 수 있습니다.

## <a name="deterministic"></a>결정적

컴파일러에서 동일한 입력에 대한 컴파일 간에 바이트 단위(byte-for-byte) 출력이 동일한 어셈블리를 생성합니다.

```xml
<Deterministic></Deterministic>
```

기본적으로 컴파일러는 타임스탬프 및 난수에서 생성된 MVID를 추가하기 때문에 지정된 입력 세트의 컴파일러 출력은 고유합니다. `<Deterministic>` 옵션을 사용하여 *결정적 어셈블리* 를 생성하고, 입력이 동일하게 유지되는 한 해당 이진 콘텐츠가 컴파일 간에 동일합니다. 해당 빌드에서 타임스탬프 및 MVID 필드는 모든 컴파일 입력의 해시에서 파생된 값으로 대체됩니다. 컴파일러는 결정성에 영향을 주는 다음 입력을 고려합니다.

- 명령줄 매개 변수의 순서
- 컴파일러의 .rsp 지시 파일의 내용
- 사용된 컴파일러의 정확한 버전 및 참조되는 어셈블리
- 현재 디렉터리 경로
- 다음을 포함하여 직접 또는 간접적으로 컴파일러에 명시적으로 전달된 모든 파일의 이진 콘텐츠
  - 소스 파일
  - 참조된 어셈블리
  - 참조된 모듈
  - 리소스
  - 강력한 이름 키 파일
  - @ 지시 파일
  - 분석기
  - 규칙 집합
  - 분석기에서 사용할 수 있는 기타 파일
- 현재 문화권(진단 및 예외 메시지가 생성되는 언어)
- 인코딩이 지정되지 않은 경우 기본 인코딩(또는 현재 코드 페이지).
- 컴파일러의 검색 경로(예: `-lib` 또는 `-recurse`로 지정)에 있는 파일의 존재 여부 및 내용
- 컴파일러가 실행되는 CLR(공용 언어 런타임) 플랫폼입니다.
- `%LIBPATH%` 값(분석기 종속성 로드에 영향을 줄 수 있음)

결정적 컴파일을 사용하여 이진 파일이 신뢰할 수 있는 원본에서 컴파일되는지 여부를 설정할 수 있습니다. 결정적 출력은 원본을 공개적으로 사용할 수 있을 때 유용할 수 있습니다. 빌드 프로세스에서 사용되는 이진 파일의 변경 내용에 종속되는 빌드 단계를 결정할 수도 있습니다.

## <a name="produceonlyreferenceassembly"></a>ProduceOnlyReferenceAssembly

**ProduceOnlyReferenceAssembly** 옵션은 구현 어셈블리 대신 참조 어셈블리가 기본 출력으로 출력되어야 함을 나타냅니다. **ProduceOnlyReferenceAssembly** 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.

```xml
<ProduceOnlyReferenceAssembly></ProduceOnlyReferenceAssembly>
```

참조 어셈블리는 특수한 유형의 어셈블리입니다. 참조 어셈블리에는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함됩니다. 빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다. 자세한 내용은 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.

**ProduceOnlyReferenceAssembly** 및 [**ProduceReferenceAssembly**](output.md#producereferenceassembly) 옵션은 함께 사용할 수 없습니다.
