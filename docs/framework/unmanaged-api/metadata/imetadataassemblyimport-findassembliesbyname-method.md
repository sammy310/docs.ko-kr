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
ms.openlocfilehash: 05902436c09d082f90af01f48c7e918650317ce7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009420"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName 메서드
`szAssemblyName`참조를 확인 하기 위해 CLR (공용 언어 런타임)에서 사용 하는 표준 규칙을 사용 하 여 지정 된 매개 변수를 가진 어셈블리의 배열을 가져옵니다.  
  
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
 진행 지정 된 어셈블리를 검색할 루트 디렉터리입니다. 이 값이로 설정 된 `null` 경우 `FindAssembliesByName` 는 어셈블리에 대 한 전역 어셈블리 캐시에만 표시 됩니다.  
  
 `szPrivateBin`  
 진행 루트 디렉터리 아래에서 어셈블리를 검색할 세미콜론으로 구분 된 하위 디렉터리 (예: "bin; bin2")의 목록입니다. 이러한 디렉터리는 기본 검색 규칙에 지정 된 디렉터리 외에도 검색 됩니다.  
  
 `szAssemblyName`  
 진행 찾을 어셈블리의 이름입니다. 이 문자열의 형식은의 클래스 참조 페이지에서 정의 됩니다 <xref:System.Reflection.AssemblyName> .  
  
 `ppIUnk`  
 진행 인터페이스 포인터를 넣을 [IUnknown](/cpp/atl/iunknown) 형식의 배열입니다 `IMetadataAssemblyImport` .  
  
 `cMax`  
 제한이 에 배치할 수 있는 인터페이스 포인터의 최대 개수입니다 `ppIUnk` .  
  
 `pcAssemblies`  
 제한이 반환 된 인터페이스 포인터의 수입니다. 즉, 실제로 배치 된 인터페이스 포인터의 수입니다 `ppIUnk` .  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`성공적으로 반환 되었습니다.|  
|`S_FALSE`|어셈블리가 없습니다.|  
  
## <a name="remarks"></a>설명  
 어셈블리 이름이 지정 된 경우 `FindAssembliesByName` 메서드는 어셈블리 참조를 확인 하는 표준 규칙에 따라 어셈블리를 찾습니다. (자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../deployment/how-the-runtime-locates-assemblies.md)을 참조 하세요.) `FindAssembliesByName`호출자가 응용 프로그램 기본 및 개인 검색 경로와 같은 어셈블리 확인 프로그램 컨텍스트의 다양 한 측면을 구성할 수 있도록 합니다.  
  
 `FindAssembliesByName`메서드를 사용 하려면 어셈블리 확인 논리를 호출 하기 위해 프로세스에서 CLR을 초기화 해야 합니다. 따라서를 호출 하기 전에 [Coinitializeee](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT 전달)를 호출한 `FindAssembliesByName` 다음 [CoUninitializeCor](../hosting/couninitializecor-function.md)에 대 한 호출을 수행 해야 합니다.  
  
 `FindAssembliesByName`전달 된 어셈블리 이름에 대 한 어셈블리 매니페스트가 포함 된 파일에 대 한 [IMetaDataImport](imetadataimport-interface.md) 포인터를 반환 합니다. 지정 된 어셈블리 이름이 완전히 지정 되지 않은 경우 (예: 버전을 포함 하지 않는 경우) 여러 어셈블리가 반환 될 수 있습니다.  
  
 `FindAssembliesByName`는 컴파일 시간에 참조 된 어셈블리를 찾으려고 시도 하는 컴파일러에서 일반적으로 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [런타임에서 어셈블리를 찾는 방법](../../deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
