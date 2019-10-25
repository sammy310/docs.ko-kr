---
title: 기본 검색 - .NET Core
description: 종속성을 찾기 위한 .NET Core의 System.Runtime.Loader.AssemblyLoadContext.Default 검색 논리 개요입니다.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2019
ms.locfileid: "72303685"
---
# <a name="default-probing"></a>기본 검색

<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스는 어셈블리의 종속성을 찾는 역할을 합니다. 이 문서에서는 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스의 검색 논리를 설명합니다.

## <a name="host-configured-probing-properties"></a>호스트 구성 검색 속성

런타임이 시작되면 런타임 호스트는 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 프로브 경로를 구성하는 명명된 검색 속성 세트를 제공합니다.

각 검색 속성은 선택 사항입니다. 있는 경우 각 속성은 구분 기호로 분리된 절대 경로 목록을 포함하는 문자열 값입니다. 구분 기호는 Windows의 경우 ';'이고 다른 모든 플랫폼의 경우 ':'입니다.

|속성 이름                 |설명  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | 플랫폼 및 애플리케이션 어셈블리 파일 경로의 목록입니다. |
|`PLATFORM_RESOURCE_ROOTS`       | 위성 리소스 어셈블리를 검색할 디렉터리 경로 목록입니다. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | 관리되지 않는(네이티브) 라이브러리를 검색할 디렉터리 경로 목록입니다.        |
|`APP_PATHS`                     | 관리 어셈블리를 검색할 디렉터리 경로 목록입니다. |
|`APP_NI_PATHS`                  | 관리 어셈블리의 네이티브 이미지를 검색할 디렉터리 경로 목록입니다. |

### <a name="how-are-the-properties-populated"></a>속성이 채워지는 방법

*\<myapp>.deps.json* 파일의 존재 여부에 따라 속성을 채우는 두 가지 주요 시나리오가 있습니다.

- *\*.deps.json* 파일이 있으면 검색 속성을 채우도록 구문 분석됩니다.
- *\*.deps.json* 파일이 없으면 애플리케이션의 디렉터리에 모든 종속성이 포함된 것으로 가정합니다. 디렉터리의 콘텐츠는 검색 속성을 채우는 데 사용됩니다.

또한 참조된 프레임워크의 *\*.deps.json* 파일도 유사하게 구문 분석됩니다.

마지막으로 `ADDITIONAL_DEPS` 환경 변수를 사용하여 추가 종속성을 추가할 수 있습니다.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>관리 코드에서 검색 속성을 확인하는 방법

각 속성은 위의 표에서 속성 이름으로 <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> 함수를 호출하여 사용할 수 있습니다.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>검색 속성 생성의 구성을 디버깅하는 방법

특정 환경 변수가 활성화되면 .NET Core 런타임 호스트가 유용한 추적 메시지를 출력합니다.

|환경 변수        |설명  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |추적을 활성화합니다.|
|`COREHOST_TRACEFILE=<path>` |기본 `stderr` 대신 파일 경로를 추적합니다.|
|`COREHOST_TRACE_VERBOSITY`  |자세한 정도를 1(가장 낮음)에서 4(가장 높음)로 설정합니다.|

## <a name="managed-assembly-default-probing"></a>관리 어셈블리 기본 검색

관리 어셈블리를 찾기 위해 검색할 때 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>은 다음을 순서대로 검색합니다.

- 파일 확장명을 제거한 후 `TRUSTED_PLATFORM_ASSEMBLIES`에서 <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>과 일치하는 파일입니다.
- 일반 파일 확장자가 있는 `APP_NI_PATHS`의 네이티브 이미지 어셈블리 파일입니다.
- 일반 파일 확장자가 있는 `APP_PATHS`의 어셈블리 파일입니다.

## <a name="satellite-resource-assembly-probing"></a>위성(리소스) 어셈블리 검색

특정 문화권에 대한 위성 어셈블리를 찾으려면 파일 경로 세트를 구성합니다.

`PLATFORM_RESOURCE_ROOTS` 및 `APP_PATHS`의 각 경로에 대해 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 문자열, 디렉터리 구분 기호, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> 문자열 및 확장명 '.dll'을 추가합니다.

일치하는 파일이 있는 경우 로드하고 반환합니다.

## <a name="unmanaged-native-library-probing"></a>관리되지 않는(네이티브) 라이브러리 검색

관리되지 않는 라이브러리를 찾기 위해 검색할 때 `NATIVE_DLL_SEARCH_DIRECTORIES`에서 일치하는 라이브러리를 찾아 검색됩니다.
