---
title: IMetaDataInfo::GetFileMapping 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175267"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping 메서드
매핑된 파일의 메모리 영역과 매핑 유형을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppvData`  
 【아웃】 매핑된 파일의 시작 부분에 대한 포인터입니다.  
  
 `pcbData`  
 【아웃】 매핑된 영역의 크기입니다. `fmFlat`이 경우 `pdwMappingType` 파일의 크기입니다.  
  
 `pdwMappingType`  
 【아웃】 매핑 유형을 나타내는 [CorFile매핑](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) 값입니다. 공통 언어 런타임(CLR)의 현재 구현은 항상 반환됩니다. `fmFlat` 다른 값은 나중에 사용할 수 있도록 예약되어 있습니다. 그러나 이후 버전 이나 서비스 릴리스에서 다른 값을 사용할 수 있으므로 항상 반환 된 값을 확인 해야 합니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|모든 출력이 채워져 있습니다.|  
|`E_INVALIDARG`|NULL이 인수 값으로 전달되었습니다.|  
|`COR_E_NOTSUPPORTED`|CLR 구현은 메모리 영역에 대한 정보를 제공할 수 없습니다. 이 문제는 다음과 같은 이유로 발생할 수 있습니다.<br /><br /> - `ofWrite` 또는 `ofCopyMemory` 플래그로 메타데이터 범위가 열렸습니다.<br />- `ofReadOnly` 메타데이터 범위가 플래그 없이 열렸습니다.<br />- [IMetaData디스펜서::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타데이터 부분만 여는 데 사용되었습니다.<br />- 파일이 휴대용 실행 파일 (PE) 파일이 아닙니다. **참고:**  이러한 조건은 CLR 구현에 따라 다르며 이후 버전의 CLR에서 약화될 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 `ppvData` 가리키는 메모리는 기본 메타데이터 범위가 열려 있는 경우에만 유효합니다.  
  
 이 메서드가 작동하려면 [IMetaDataScopeer::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 메서드를 호출하여 디스크 온 파일의 메타데이터를 메모리에 매핑할 `ofReadOnly` 때 플래그를 지정해야 `ofCopyMemory` 하며 또는 플래그를 `ofWrite` 지정해서는 안 됩니다.  
  
 각 범위에 대한 파일 매핑 형식의 선택은 CLR의 지정된 구현에 따라 다릅니다. 사용자가 설정할 수 없습니다. CLR의 현재 구현은 `fmFlat` 항상 `pdwMappingType`에서 반환되지만 CLR의 이후 버전 또는 지정된 버전의 이후 서비스 릴리스에서 변경될 수 있습니다. 다른 형식마다 레이아웃과 `pdwMappingType`오프셋이 다르므로 항상 에서 반환된 값을 확인해야 합니다.  
  
 세 매개 변수 중 어느 것에 대해서도 NULL을 전달하는 것은 지원되지 않습니다. 메서드가 `E_INVALIDARG`반환되고 출력이 채워지지 않습니다. 매핑 유형이나 영역 크기를 무시하면 비정상적인 프로그램 종료가 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataInfo 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping 열거형](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
