---
description: 컴파일을 위한 입력 파일을 제어하는 C# 컴파일러 옵션입니다. 이러한 옵션은 컴파일러가 종속 어셈블리 및 모듈에서 메타데이터를 읽는 방법을 지정합니다.
title: C# 컴파일러 옵션 - 입력 파일 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- References compiler option [C#]
- AddModules compiler option [C#]
- EmbedInteropTypes compiler option [C#]
ms.openlocfilehash: 819e2322720782b94bd744e00c602221f023c0d8
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482503"
---
# <a name="c-compiler-options-that-specify-inputs"></a>입력을 지정하는 C# 컴파일러 옵션

다음 옵션은 컴파일러 입력을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **References** / `-reference` 또는 `-references`: 지정한 어셈블리 파일에서 메타데이터를 참조합니다.
- **AddModules** / `-addmodule`: 모듈을 추가합니다(이 어셈블리에 `target:module`로 생성됨)
- **EmbedInteropTypes** / `-link`: 지정된 interop 어셈블리 파일에서 메타데이터를 포함합니다.

## <a name="references"></a>참조

**References** 옵션을 사용하면 컴파일러가 지정된 파일의 [public](../keywords/public.md) 형식 정보를 현재 프로젝트로 가져와 지정된 어셈블리 파일에서 메타데이터를 참조할 수 있습니다.

```xml
<Reference Include="filename" />
```

 `filename`은 어셈블리 매니페스트를 포함하는 파일의 이름입니다. 둘 이상의 파일을 가져오기 위해 각 파일에 대해 별도의 **Reference** 요소를 포함합니다. 별칭을 **Reference** 요소의 자식 요소로 정의할 수 있습니다.

```xml
<Reference Include="filename.dll">
  <Aliases>LS</Aliases>
</Reference>
```

이전 예제에서 `LS`는 어셈블리 *filename.dll* 의 모든 네임스페이스를 포함하는 루트 네임스페이스를 나타내는 유효한 C# 식별자입니다. 가져오는 파일에는 매니페스트가 포함되어 있어야 합니다. [**AdditionalLibPaths**](advanced.md#additionallibpaths)를 사용하여 하나 이상의 어셈블리 참조가 있는 디렉터리를 지정합니다. [**AdditionalLibPaths**](advanced.md#additionallibpaths) 항목에서는 컴파일러가 어셈블리를 검색하는 디렉터리에 대해서도 설명합니다. 컴파일러가 모듈이 아니라 어셈블리의 형식을 인식하려면 강제로 형식을 확인하도록 해야 하며, 이 작업을 위해 형식의 인스턴스를 정의할 수 있습니다. 컴파일러를 위해 어셈블리의 형식 이름을 확인하는 다른 방법이 있습니다. 예를 들어 어셈블리의 형식에서 상속하는 경우 컴파일러가 형식 이름을 인식합니다. 때로는 하나의 어셈블리 내에서 동일한 구성 요소의 두 가지 버전을 참조해야 합니다. 이렇게 하려면 각 파일에 대한 **References** 요소에 있는 **Aliases** 요소를 사용하여 두 파일을 구분합니다. 이 별칭은 구성 요소 이름에 대한 한정자로 사용되며, 파일 중 하나의 구성 요소로 확인됩니다.

> [!NOTE]
> Visual Studio에서 **참조 추가** 명령을 사용합니다. 자세한 내용은 [방법: 참조 관리자를 사용하여 참조 추가 또는 제거](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)를 참조하세요.

## <a name="addmodules"></a>AddModules

이 옵션은 `<TargetType>module</TargetType>` 스위치로 만들어진 모듈을 현재 컴파일에 추가합니다.

```xml
<AddModule Include=file1 />
<AddModule Include=file2 />
```

여기서 `file`, `file2`는 메타데이터를 포함하는 출력 파일입니다. 파일에 어셈블리 매니페스트를 포함할 수 없습니다. 둘 이상의 파일을 가져오려면 파일 이름을 쉼표 또는 세미콜론으로 구분합니다. **AddModules** 를 사용하여 추가된 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다. 즉, 컴파일 시간에 임의 디렉터리에 있는 모듈을 지정할 수 있지만 런타임에 모듈이 애플리케이션 디렉터리에 있어야 합니다. 모듈이 런타임에 애플리케이션 디렉터리에 없는 경우 <xref:System.TypeLoadException>을 가져옵니다. `file`에 어셈블리를 포함할 수 없습니다. 예를 들어, **module** 의 [**TargetType**](output.md#targettype)을 사용하여 출력 파일이 만들어진 경우 해당 메타데이터를 **AddModules** 를 사용하여 가져올 수 있습니다.

출력 파일이 **module** 이외의 [**TargetType**](output.md#targettype) 옵션으로 생성된 경우 해당 메타데이터를 **AddModules** 로 가져올 수 없지만 [**References**](#references) 옵션으로 가져올수 있습니다.

## <a name="embedinteroptypes"></a>EmbedInteropTypes

컴파일러에서 지정된 어셈블리의 COM 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.

```xml
<References>
  <EmbedInteropTypes>file1;file2;file3</EmbedInteropTypes>
</References>
```

여기서 `file1;file2;file3`은 세미콜론으로 구분된 어셈블리 파일 이름 목록입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다. **EmbedInteropTypes** 옵션을 사용하면 포함된 형식 정보가 있는 애플리케이션을 배포할 수 있습니다. 그러면 애플리케이션은 런타임 어셈블리에 대한 참조를 요구하지 않고 포함된 형식 정보를 구현하는 형식을 런타임 어셈블리에서 사용할 수 있습니다. 다양한 버전의 런타임 어셈블리가 게시된 경우 포함된 형식 정보를 포함하는 애플리케이션은 다시 컴파일하지 않아도 다양한 버전에서 사용할 수 있습니다. 예제를 보려면 [연습: 관리되는 어셈블리의 형식 포함](../../../standard/assembly/embed-types-visual-studio.md)을 참조하세요.

**EmbedInteropTypes** 옵션을 사용하면 COM interop으로 작업할 때 특히 유용합니다. 애플리케이션에 대상 컴퓨터의 PIA(주 interop 어셈블리)가 더 이상 필요하지 않도록 COM 형식을 포함할 수 있습니다. **EmbedInteropTypes** 옵션은 참조된 interop 어셈블리의 COM 형식 정보를 컴파일된 결과 코드에 포함하도록 컴파일러에 지시합니다. COM 형식은 CLSID(GUID) 값으로 식별됩니다. 따라서 동일한 CLSID 값을 갖는 동일한 COM 형식이 설치된 대상 컴퓨터에서 애플리케이션을 실행할 수 있습니다. Microsoft Office를 자동화하는 애플리케이션이 좋은 예입니다. Office와 같은 애플리케이션은 일반적으로 여러 버전에서 동일한 CLSID 값을 유지하지 때문에 .NET Framework 4 이상이 대상 컴퓨터에 설치되어 있고 애플리케이션이 참조된 COM 형식에 포함된 메서드, 속성 또는 이벤트를 사용하는 한 애플리케이션에서 참조된 COM 형식을 사용할 수 있습니다. **EmbedInteropTypes** 옵션은 인터페이스, 구조체 및 대리자만 포함합니다. COM 클래스 포함은 지원되지 않습니다.

> [!NOTE]
> 코드에서 포함된 COM 형식의 인스턴스를 만드는 경우 적절한 인터페이스를 사용하여 인스턴스를 만들어야 합니다. CoClass를 사용하여 포함된 COM 형식의 인스턴스를 만들려고 하면 오류가 발생합니다.

[**References**](#references) 컴파일러 옵션과 마찬가지로, **EmbedInteropTypes** 컴파일러 옵션은 자주 사용되는 .NET 어셈블리를 참조하는 Csc.rsp 지시 파일을 사용합니다. 컴파일러가 Csc.rsp 파일을 사용하지 않도록 하려면 [**NoConfig**](miscellaneous.md#noconfig) 컴파일러 옵션을 사용하세요.

[!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]

형식이 interop 어셈블리에서 포함된 제네릭 매개 변수가 있는 형식은 해당 형식이 외부 어셈블리에서 제공된 경우 사용할 수 없습니다. 인터스페이스에는 이 제한이 적용되지 않습니다. 예를 들어 <xref:Microsoft.Office.Interop.Excel> 어셈블리에 정의된 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스를 살펴보세요. 다음 코드 예제와 같이 라이브러리가 <xref:Microsoft.Office.Interop.Excel> 어셈블리의 interop 형식을 포함하고 형식이 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스인 매개 변수가 있는 제네릭 형식을 반환하는 메서드를 노출하는 경우 해당 메서드는 제네릭 인터페이스를 반환해야 합니다.

[!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs)]

다음 예제에서 클라이언트 코드는 <xref:System.Collections.IList> 제네릭 인터페이스를 반환하는 메서드를 오류 없이 호출할 수 있습니다.

[!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]
