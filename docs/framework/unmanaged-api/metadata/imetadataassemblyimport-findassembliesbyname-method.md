---
title: IMetaDataAssemblyImport::FindAssembliesByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177795"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName 메서드
참조를 해결하기 위해 공통 `szAssemblyName` 언어 런타임(CLR)에서 사용하는 표준 규칙을 사용하여 지정된 매개 변수를 사용하여 어셈블리 배열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szAppBase`  
 【인】 지정된 어셈블리를 검색할 루트 디렉터리입니다. 이 값을 `null`로 `FindAssembliesByName` 설정된 경우 어셈블리에 대한 전역 어셈블리 캐시에서만 표시됩니다.  
  
 `szPrivateBin`  
 【인】 어셈블리를 검색할 루트 디렉터리 아래에 세미콜론으로 구분된 하위 디렉토리(예: "bin;bin2") 목록입니다. 이러한 디렉터리에는 기본 검색 규칙에 지정된 디렉터리 외에 검색됩니다.  
  
 `szAssemblyName`  
 【인】 찾을 어셈블리의 이름입니다. 이 문자열의 형식은 에 대한 <xref:System.Reflection.AssemblyName>클래스 참조 페이지에 정의됩니다.  
  
 `ppIUnk`  
 【인】 인터페이스 포인터를 넣을 [IUnknown](/cpp/atl/iunknown) 형식의 `IMetadataAssemblyImport` 배열입니다.  
  
 `cMax`  
 【아웃】 에 `ppIUnk`배치할 수 있는 최대 인터페이스 포인터 수입니다.  
  
 `pcAssemblies`  
 【아웃】 반환된 인터페이스 포인터 수입니다. 즉, 실제로 에 배치된 인터페이스 `ppIUnk`포인터의 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`성공적으로 반환됩니다.|  
|`S_FALSE`|어셈블리가 없습니다.|  
  
## <a name="remarks"></a>설명  
 어셈블리 이름이 `FindAssembliesByName` 지정되면 메서드는 어셈블리 참조를 해결하기 위한 표준 규칙을 따라 어셈블리를 찾습니다. 자세한 내용은 [런타임이 어셈블리를 찾는 방법을](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)참조하십시오. `FindAssembliesByName` 호출자가 응용 프로그램 기반 및 개인 검색 경로와 같은 어셈블리 확인자 컨텍스트의 다양한 측면을 구성할 수 있습니다.  
  
 이 `FindAssembliesByName` 메서드는 어셈블리 확인 논리를 호출하기 위해 프로세스에서 CLR을 초기화해야 합니다. 따라서 호출하기 `FindAssembliesByName`전에 [CoInitializeEE(COINITEE_DEFAULT](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) 전달)를 호출한 다음 [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)에 대한 호출을 따라야 합니다.  
  
 `FindAssembliesByName`에서는 전달되는 어셈블리 이름에 대한 어셈블리 매니페스트가 포함된 파일에 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 포인터를 반환합니다. 지정된 어셈블리 이름이 완전히 지정되지 않은 경우(예: 버전을 포함하지 않는 경우) 여러 어셈블리가 반환될 수 있습니다.  
  
 `FindAssembliesByName`일반적으로 컴파일타임에 참조된 어셈블리를 찾으려고 시도하는 컴파일러에서 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [런타임에서 어셈블리를 찾는 방법](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
