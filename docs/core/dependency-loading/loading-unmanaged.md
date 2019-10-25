---
title: 관리되지 않는 라이브러리 로드 알고리즘 - .NET Core
description: .NET Core에서 관리되지 않는 어셈블리 로드 알고리즘의 세부 정보 설명
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72303697"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>관리되지 않는(네이티브) 라이브러리 로드 알고리즘

관리되지 않는 라이브러리는 다양한 단계를 포함하는 알고리즘으로 배치되고 로드됩니다.

다음 알고리즘에서는 `PInvoke`를 통해 네이티브 라이브러리를 로드하는 방법을 설명합니다.

## <a name="pinvoke-load-library-algorithm"></a>`PInvoke` 로드 라이브러리 알고리즘

`PInvoke`는 관리되지 않는 어셈블리를 로드하려고 할 때 다음 알고리즘을 사용합니다.

1. `active` <xref:System.Runtime.Loader.AssemblyLoadContext>를 확인합니다. 관리되지 않는 로드 라이브러리의 경우 `active` AssemblyLoadContext는 `PInvoke`를 정의하는 어셈블리를 사용합니다.

2. `active` <xref:System.Runtime.Loader.AssemblyLoadContext>의 경우 다음을 통해 우선순위를 기준으로 어셈블리를 찾습니다.
    * 해당 캐시를 확인하는 중입니다.

    * <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> 함수로 설정된 현재 <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> 대리자를 호출하는 중입니다.

    * `active` AssemblyLoadContext에서 <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> 함수를 호출하는 중입니다.

    * <xref:System.AppDomain> 인스턴스의 캐시를 확인하고 [관리되지 않는(네이티브) 라이브러리 검색](default-probing.md#unmanaged-native-library-probing) 논리를 실행합니다.

    * `active` AssemblyLoadContext에 대한 <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> 이벤트를 발생시킵니다.
