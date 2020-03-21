---
title: IMetaDataDispenser::OpenScopeOnMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175930"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory 메서드
기존 메타데이터가 포함된 메모리 영역을 엽니다. 즉, 이 메서드는 기존 데이터가 메타데이터로 처리되는 지정된 메모리 영역을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pData`  
 【인】 메모리 영역의 시작 주소를 지정하는 포인터입니다.  
  
 `cbData`  
 【인】 메모리 영역의 크기(바이트)입니다.  
  
 `dwOpenFlags`  
 【인】 열기모드(읽기, 쓰기 등)를 지정하는 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열거형값입니다.  
  
 `riid`  
 【인】 반송할 원하는 메타데이터 인터페이스의 IID; 호출자는 인터페이스를 사용하여 메타데이터를 가져오거나(쓰기) 내보를 내보올 것입니다.  
  
 값은 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 또는 IID_IMetaDataImport2.  
  
 `ppIUnk`  
 【아웃】 반환된 인터페이스에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 메타데이터의 메모리 내 복사본은 "가져오기" 인터페이스 중 하나의 메서드를 사용하여 쿼리하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용하여 추가할 수 있습니다.  
  
 이 `OpenScopeOnMemory` 메서드는 [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 메서드와 유사하지만 관심 있는 메타데이터가 디스크의 파일이 아니라 메모리에 이미 존재한다는 점을 제외하면  
  
 메모리의 대상 영역에 공통 언어 런타임(CLR) 메타데이터가 `OpenScopeOnMemory` 없는 경우 메서드가 실패합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
