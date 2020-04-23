---
title: 'C# 예약된 특성: 전역 특성'
ms.date: 04/09/2020
description: 특성은 컴파일러가 프로그램의 더 많은 의미 체계를 이해하는 데 사용하는 메타데이터를 제공합니다.
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389807"
---
# <a name="reserved-attributes-assembly-level-attributes"></a>예약된 특성: 어셈블리 수준 특성

대부분의 특성은 클래스나 메서드와 같은 특정 언어 요소에 적용되지만 일부 특성은 전체 어셈블리나 모듈에 적용되는 전역 특성입니다. 예를 들어 다음과 같이 <xref:System.Reflection.AssemblyVersionAttribute> 특성을 사용하여 버전 정보를 어셈블리에 포함할 수 있습니다.

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

전역 특성은 소스 코드에서 최상위 `using` 지시문 뒤 그리고 형식, 모듈 또는 네임스페이스 선언 앞에 나타납니다. 전역 특성은 여러 소스 파일에 나타날 수 있지만 파일은 하나의 컴파일 패스에서 컴파일되어야 합니다. Visual Studio는 .NET Framework 프로젝트의 AssemblyInfo.cs 파일에 전역 특성을 추가합니다. 해당 특성은 .NET Core 프로젝트에 추가되지 않습니다.

어셈블리 특성은 어셈블리에 대한 정보를 제공하는 값입니다. 어셈블리 특성은 다음 범주로 구분됩니다.

- 어셈블리 ID 특성
- 정보 특성
- 어셈블리 매니페스트 특성

## <a name="assembly-identity-attributes"></a>어셈블리 ID 특성

name, version 및 culture의 세 가지 특성(해당하는 경우 강력한 이름 포함)이 어셈블리의 ID를 결정합니다. 이러한 특성은 어셈블리의 전체 이름을 구성하며 코드에서 어셈블리를 참조할 때 필요합니다. 특성을 사용하여 어셈블리의 버전 및 문화권을 설정할 수 있습니다. 그러나 이름 값은 어셈블리가 만들어질 때 컴파일러, [어셈블리 정보 대화 상자](/visualstudio/ide/reference/assembly-information-dialog-box)의 Visual Studio IDE 또는 어셈블리 링커(Al.exe)에서 설정됩니다. 어셈블리 이름은 어셈블리 매니페스트를 기반으로 합니다. <xref:System.Reflection.AssemblyFlagsAttribute> 특성은 어셈블리의 여러 복사본이 공존할 수 있는지 여부를 지정합니다.

다음 표에서는 ID 특성들을 보여 줍니다.

|특성|용도|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|어셈블리의 버전을 지정합니다.|
|<xref:System.Reflection.AssemblyCultureAttribute>|어셈블리에서 지원하는 문화권을 지정합니다.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|어셈블리가 같은 컴퓨터, 같은 프로세스 또는 같은 애플리케이션 도메인에서 Side-by-side 실행을 지원하는지 지정합니다.|

## <a name="informational-attributes"></a>정보 특성

정보 특성을 사용하여 어셈블리와 연관된 회사 또는 제품에 대한 추가적인 정보를 제공합니다. 다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 정보 특성을 보여 줍니다.

|특성|용도|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|어셈블리 매니페스트의 제품 이름을 지정합니다.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|어셈블리 매니페스트의 상표를 지정합니다.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|어셈블리 매니페스트의 정보 버전을 지정합니다.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|어셈블리 매니페스트의 회사 이름을 지정합니다.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|어셈블리 매니페스트에 대한 저작권을 지정하는 사용자 지정 특성을 정의합니다.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Win32 파일 버전 리소스의 특정 버전 번호를 설정합니다.|
|<xref:System.CLSCompliantAttribute>|어셈블리가 CLS(공용 언어 사양)을 준수하는지 여부를 나타냅니다.|

## <a name="assembly-manifest-attributes"></a>어셈블리 매니페스트 특성

어셈블리 매니페스트 특성을 사용하여 어셈블리 매니페스트의 정보를 제공할 수 있습니다. 특성에는 제목, 설명, 기본 별칭 및 구성이 포함됩니다. 다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 어셈블리 매니페스트 특성을 보여 줍니다.

|특성|용도|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|어셈블리 매니페스트의 어셈블리 제목을 지정합니다.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|어셈블리 매니페스트의 어셈블리 설명을 지정합니다.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|어셈블리 매니페스트의 어셈블리 구성(예: 정품 또는 디버그)을 지정합니다.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|어셈블리 매니페스트에 대한 친숙한 기본 별칭을 정의합니다.|
