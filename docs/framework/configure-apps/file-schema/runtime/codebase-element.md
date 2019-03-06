---
title: <codeBase> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356613"
---
# <a name="codebase-element"></a>\<코드 베이스 > 요소

공용 언어 런타임에서 어셈블리를 찾는 위치를 지정 합니다.

\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase>

## <a name="syntax"></a>구문

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|`href`|필수 특성입니다.<br /><br /> 런타임에서 어셈블리의 지정된 된 버전을 찾을 수 있는 URL을 지정 합니다.|
|`version`|필수 특성입니다.<br /><br /> 코드 베이스에 적용 하는 어셈블리의 버전을 지정 합니다. 어셈블리 버전 번호의 형식은 *major.minor.build.revision*합니다.|

## <a name="version-attribute"></a>버전 특성

|값|설명|
|-----------|-----------------|
|버전 번호의 각 부분에 대 한 유효한 값은 0부터 65535 까지입니다.|해당 사항 없음.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`buildproviders`|사용자 지정 리소스 파일의 컴파일에 사용되는 빌드 공급자의 컬렉션을 정의합니다. 빌드 공급자 수에는 제한이 없습니다.|
|`compilation`|ASP.NET을 사용 하는 모든 컴파일 설정을 구성 합니다.|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`System.web`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|

## <a name="remarks"></a>설명

사용에 런타임에 대 한 합니다  **\<codeBase >** 컴퓨터 구성 파일 또는 게시자 정책 파일에서 설정 파일을 리디렉션해야 어셈블리 버전입니다. 응용 프로그램 구성 파일에는 어셈블리 버전 리디렉션 없이 코드 베이스 설정이 있을 수 있습니다. 사용 하는 어셈블리 버전을 결정 한 후 런타임 버전을 결정 하는 파일의 코드 베이스 설정을 적용 합니다. 없는 코드 베이스를 지정 하는 경우 런타임은 일반적인 방법으로 어셈블리를 검색 합니다.

어셈블리에 강력한 이름을 하는 경우 코드 베이스 설정을 로컬 인트라넷 또는 인터넷에서 아무 곳 이나 수 있습니다. 전용 어셈블리를 어셈블리가 있는 경우 코드 베이스 설정을 응용 프로그램의 디렉터리에 상대적인 경로 여야 합니다.

강력한 이름이 없는 어셈블리의 경우 버전이 무시 되 고 로더는 첫 번째 모양의 \<codebase > 내에서 \<dependentAssembly >. 다른 어셈블리 바인딩을 리디렉션하는 응용 프로그램 구성 파일에 항목이 있으면 리디렉션 어셈블리 버전 바인딩 요청과 일치 하지 않습니다 하는 경우에 우선을 적용 됩니다.

## <a name="example"></a>예제

다음 예제에서는 런타임에 어셈블리를 찾을 수 있습니다 위치를 지정 하는 방법을 보여 줍니다.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [어셈블리 위치 지정](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
