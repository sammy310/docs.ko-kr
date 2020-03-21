---
title: IMetaDataDispenser::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175943"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope 메서드
기존 디스크 파일을 열고 메타데이터를 메모리에 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szScope`  
 【인】 열 파일의 이름입니다. 파일에는 공통 언어 런타임(CLR) 메타데이터가 포함되어야 합니다.  
  
 `dwOpenFlags`  
 【인】 열기모드(읽기, 쓰기 등)를 지정하는 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열거형값입니다.  
  
 `riid`  
 【인】 반송할 원하는 메타데이터 인터페이스의 IID; 호출자는 인터페이스를 사용하여 메타데이터를 가져오거나(쓰기) 내보를 내보올 것입니다.  
  
 값은 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 또는 IID_IMetaDataImport2.  
  
 `ppIUnk`  
 【아웃】 반환된 인터페이스에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 메타데이터의 메모리 내 복사본은 "가져오기" 인터페이스 중 하나의 메서드를 사용하여 쿼리하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용하여 추가할 수 있습니다.  
  
 대상 파일에 CLR 메타데이터가 없는 `OpenScope` 경우 메서드가 실패합니다.  
  
 .NET Framework 버전 1.0 및 버전 1.1에서 범위를 `dwOpenFlags` ofRead로 설정하여 열면 공유할 수 있습니다. 즉, 이전에 열린 `OpenScope` 파일의 이름으로 전달하는 후속 호출이 기존 범위를 다시 사용하고 새 데이터 구조 집합이 만들어지지 않는 경우입니다. 그러나 이 공유로 인해 문제가 발생할 수 있습니다.  
  
 .NET Framework 버전 2.0에서는 ofRead로 설정된 로 `dwOpenFlags` 열린 범위는 더 이상 공유되지 않습니다. 범위를 공유할 수 있도록 ofReadOnly 값을 사용합니다. 범위가 공유되면 "읽기/쓰기" 메타데이터 인터페이스를 사용하는 쿼리가 실패합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
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
