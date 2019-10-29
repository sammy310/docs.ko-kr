---
title: EDM 생성기(EdmGen.exe)
ms.date: 03/30/2017
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
ms.openlocfilehash: e8bf82933d19c6b7e9ec90f70bfa990e0d08847c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040009"
---
# <a name="edm-generator-edmgenexe"></a>EDM 생성기(EdmGen.exe)

Edmgen.exe는 Entity Framework 모델 및 매핑 파일을 사용 하는 데 사용 되는 명령줄 도구입니다. EdmGen.exe 도구를 사용하여 다음을 수행할 수 있습니다.

- 데이터 원본 관련 .NET Framework 데이터 공급자를 사용 하 여 데이터 원본에 연결 하 고 Entity Framework에서 사용 하는 개념적 모델 파일 (csdl), 저장소 모델 (ssdl) 및 매핑 (msl) 파일을 생성 합니다. 자세한 내용은 [방법: edmgen.exe를 사용 하 여 모델 및 매핑 파일 생성](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조 하세요.

- 기존 모델의 유효성을 검사합니다. 자세한 내용은 [방법: edmgen.exe를 사용 하 여 모델 및 매핑 파일 유효성 검사](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)를 참조 하세요.

- 개념적 모델(.csdl) 파일에서 생성된 개체 클래스가 포함되는 C# 또는 Visual Basic 코드 파일을 생성합니다. 자세한 내용은 [방법: edmgen.exe를 사용 하 여 개체 계층 코드 생성](how-to-use-edmgen-exe-to-generate-object-layer-code.md)을 참조 하세요.

- 기존 모델에 대해 미리 생성된 뷰가 들어 있는 C# 또는 Visual Basic 코드 파일을 생성합니다. 자세한 내용은 [방법: 뷰를 미리 생성 하 여 쿼리 성능 향상](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))을 위한 방법을 설명 합니다.

Edmgen.exe 도구는 .NET Framework 디렉터리에 설치 됩니다. 대체로 이 도구는 C:\windows\Microsoft.NET\Framework\v4.0에 있으며 64비트 시스템의 경우 C:\windows\Microsoft.NET\Framework64\v4.0에 있습니다. Visual Studio 명령 프롬프트에서 Edmgen.exe 도구에 액세스할 수도 있습니다. **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Visual Studio 2010**, **Visual Studio Tools**를 차례로 가리킨 다음 **Visual Studio 2010를 클릭 합니다. 명령 프롬프트**).

## <a name="syntax"></a>구문

```console
EdmGen /mode:choice [options]
```

## <a name="mode"></a>모드

EdmGen.exe 도구를 사용하는 경우 다음 모드 중 하나를 지정해야 합니다.

|모드|설명|
|----------|-----------------|
|`/mode:ValidateArtifacts`|.csdl, .ssdl 및 .msl 파일의 유효성을 검사하고 오류 또는 경고를 표시합니다.<br /><br /> 이 옵션을 사용하려면 `/inssdl` 또는 `/incsdl` 인수 중 하나 이상이 필요합니다. `/inmsl`을 지정하면 `/inssdl` 및 `/incsdl` 인수도 필요합니다.|
|`/mode:FullGeneration`|`/connectionstring` 옵션에 지정된 데이터베이스 연결 정보를 사용하고 .csdl, .ssdl, .msl, 개체 계층 및 뷰 파일을 생성합니다.<br /><br /> 이 옵션을 사용하려면 `/connectionstring` 인수와 `/project` 인수 또는 `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` 및 `/entitycontainer` 인수 중 하나가 필요합니다.|
|`/mode:FromSSDLGeneration`|지정한 .ssdl 파일에서 .csdl 및 .msl 파일, 소스 코드 및 뷰를 생성합니다.<br /><br /> 이 옵션을 사용하려면 `/inssdl` 인수와 `/project` 인수 또는 `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` 및 `/entitycontainer` 인수 중 하나가 필요합니다.|
|`/mode:EntityClassGeneration`|.csdl 파일에서 생성된 클래스가 포함되는 소스 코드 파일을 만듭니다.<br /><br /> 이 옵션을 사용하려면 `/incsdl` 인수와 `/project` 인수 또는 `/outobjectlayer` 인수가 필요합니다. `/language` 인수는 선택적 요소입니다.|
|`/mode:ViewGeneration`|.csdl, .ssdl 및 .msl 파일에서 생성된 뷰가 포함되는 소스 코드 파일을 만듭니다.<br /><br /> 이 옵션을 사용하려면 `/inssdl`, `/incsdl`, `/inmsl,` 인수와 `/project` 또는 `/outviews` 인수가 필요합니다. `/language` 인수는 선택적 요소입니다.|

## <a name="options"></a>옵션

|옵션|설명|
|------------|-----------------|
|`/p[roject]:`\<문자열 >|사용할 프로젝트 이름을 지정합니다. 프로젝트 이름은 네임스페이스 설정, 모델 및 매핑 파일 이름, 개체 소스 파일 이름, 뷰 생성 소스 파일 이름의 기본값으로 사용됩니다. 엔터티 컨테이너 이름이 \<project > Context로 설정 됩니다.|
|`/prov[ider]:`\<문자열 >|저장소 모델(.ssdl) 파일을 생성하는 데 사용할 .NET Framework 데이터 공급자의 이름입니다. 기본 공급자는 .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient?displayProperty=nameWithType>)입니다.|
|\<연결 문자열을 `/c[onnectionstring]:`|데이터 소스에 연결하는 데 사용되는 문자열을 지정합니다.|
|\<파일을 `/incsdl:`|.csdl 파일 또는 .csdl 파일이 있는 디렉터리를 지정합니다. 몇 개의 디렉터리나 .csdl 파일을 지정할 수 있도록 이 인수를 여러 번 지정할 수 있습니다. 여러 디렉터리를 지정하면 개념적 모델이 몇 개의 파일에 분할되어 있을 때 클래스(`/mode:EntityClassGeneration`) 또는 뷰(`/mode:ViewGeneration`)를 생성하는 데 유용할 수 있습니다. 여러 모델(`/mode:ValidateArtifacts`)의 유효성을 검사하려는 경우에도 유용할 수 있습니다.|
|\<파일을 `/refcsdl:`|소스 .csdl 파일의 참조를 확인하는 데 사용되는 추가 .csdl 파일을 지정합니다. 소스 .csdl 파일은 `/incsdl` 옵션으로 지정된 파일입니다. `/refcsdl` 파일에는 소스 .csdl 파일이 종속된 형식이 들어 있습니다. 이 인수를 여러 번 지정할 수 있습니다.|
|\<파일을 `/inmsl:`|.msl 파일 또는 .msl 파일이 있는 디렉터리를 지정합니다. 몇 개의 디렉터리나 .msl 파일을 지정할 수 있도록 이 인수를 여러 번 지정할 수 있습니다. 여러 디렉터리를 지정하면 개념적 모델이 몇 개의 파일에 분할되어 있을 때 뷰(`/mode:ViewGeneration`)를 생성하는 데 유용할 수 있습니다. 여러 모델(`/mode:ValidateArtifacts`)의 유효성을 검사하려는 경우에도 유용할 수 있습니다.|
|\<파일을 `/inssdl:`|.ssdl 파일 또는 .ssdl 파일이 있는 디렉터리를 지정합니다. 몇 개의 디렉터리나 .ssdl 파일을 지정할 수 있도록 이 인수를 여러 번 지정할 수 있습니다. 여러 모델`(/mode:ValidateArtifacts)`의 유효성을 검사하려는 경우에 유용할 수 있습니다.|
|\<파일을 `/outcsdl:`|만들 .csdl 파일의 이름을 지정합니다.|
|\<파일을 `/outmsl:`|만들 .msl 파일의 이름을 지정합니다.|
|\<파일을 `/outssdl:`|만들 .ssdl 파일의 이름을 지정합니다.|
|\<파일을 `/outobjectlayer:`|.csdl 파일에서 생성된 개체가 포함되는 소스 코드 파일의 이름을 지정합니다.|
|\<파일을 `/outviews:`|생성된 뷰가 포함되는 소스 코드 파일의 이름을 지정합니다.|
|`/language:`[VB&#124;CSharp]|생성되는 소스 코드 파일의 언어를 지정합니다. 기본 언어는 C#입니다.|
|`/namespace:`\<문자열 >|사용할 모델 네임스페이스를 지정합니다. 네임스페이스는 `/mode:FullGeneration` 또는 `/mode:FromSSDLGeneration`을 실행할 때 .csdl 파일에서 설정됩니다. `/mode:EntityClassGeneration`을 실행할 때는 네임스페이스가 사용되지 않습니다.|
|`/entitycontainer:`\<문자열 >|생성되는 모델 및 매핑 파일의 `<EntityContainer>` 요소에 적용할 이름을 지정합니다.|
|`/pl[uralize]`|개념적 모델의 `Entity`, `EntitySet` 및 `NavigationProperty` 이름에 영어의 단수 및 복수 규칙을 적용합니다. 이 옵션은 다음 동작을 수행합니다.<br /><br /> -모든 `EntityType` 이름을 단수형으로 설정 합니다.<br />-모든 `EntitySet` 이름을 복수로 설정 합니다.<br />-최대 하나의 엔터티를 반환 하는 각 `NavigationProperty`에 대해 이름을 단수형으로 설정 합니다.<br />-두 개 이상의 엔터티를 반환 하는 각 `NavigationProperty`에 대해 이름을 복수형으로 만듭니다.|
|`/SuppressForeignKeyProperties or /nofk`|외래 키 열이 개념적 모델의 엔터티 형식에 대한 스칼라 속성으로 노출되지 않도록 합니다.|
|`/help` 또는 `?`|이 도구의 명령 구문 및 옵션을 표시합니다.|
|`/nologo`|저작권 메시지가 표시되지 않도록 합니다.|
|`/targetversion:` \<문자열 >|생성된 코드를 컴파일하는 데 사용할 .NET Framework 버전입니다. 지원되는 버전은 4 및 4.5입니다. 기본값은 4입니다.|

## <a name="in-this-section"></a>단원 내용

[방법: EdmGen.exe를 사용하여 모델 생성 및 파일 매핑](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

[방법: EdmGen.exe를 사용하여 개체 계층 코드 생성](how-to-use-edmgen-exe-to-generate-object-layer-code.md)

[방법: EdmGen.exe를 사용하여 모델 유효성 검사 및 파일 매핑](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)

## <a name="see-also"></a>참조

- [ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [엔터티 데이터 모델](../entity-data-model.md)
- [CSDL, SSDL 및 MSL 사양](./language-reference/csdl-ssdl-and-msl-specifications.md)
